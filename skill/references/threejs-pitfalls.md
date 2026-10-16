# Three.js pitfalls seen in real projects

Each item cost at least one fix round in a past project. Check the relevant ones before you write the code, not after the render looks wrong.

## Geometry

- **Hand-built surface renders solid black.** Usually inside-out triangles (wrong winding), especially with an inverted-hull outline behind them. Before touching materials or lights, sample a normal at a known point or assert that each face's cross product agrees with its vertex normals. Custom tube builders must walk the ring in the same direction as `THREE.TubeGeometry`.
- **Height or extent tests fail on rotated parts.** `Box3.setFromObject(obj)` is loose for rotated geometry. Use `setFromObject(obj, true)` (precise) or scan vertices.
- **Don't edit a test's expected value to match the model** without an independent check against the reference. Compare feature ratios (head width to leg length), not raw heights measured off a perspective drawing.
- **Windows on curved or layered hulls.** Flat boxes stick out or get hidden. Sample the surrounding surface, recess the frame, move openings off seams, and cut through every cladding layer. Test pane edges, not just centres, from inside and outside. If interior decks are hidden in exterior view, their windows disappear too.
- **Clearance around rotated objects.** Check the whole rotated footprint, not a centre point. A moved object can collide with a neighbour that was clear before.

## Export (GLB / glTF)

- Colour values slightly above 1.0 (for example 1.005) fail validation (`ACCESSOR_NON_CLAMPED`); clamp them.
- Watch for degenerate triangles and missing tangents in validator warnings.
- Re-export and reimport **after the last edit**. A reimport check of an earlier export proves nothing about the final file.

## Rendering and screenshots

- **Meshes missing from screenshots or tests while state says they're present.** Shaders were still compiling. Before capturing or testing, `await renderer.compileAsync(scene, camera)`, render a frame, and check every part is actually drawn. Visibility flags alone are not proof.
- **Stale captures.** Hidden or background browser tabs slow or pause their render loop. Bring the tab to the front, wait, and confirm the image changed before drawing conclusions.
- **Toon or cel shading looks washed out.** Usually the camera is looking at the shadow side. Put the key light on the camera side, as the reference drawing is lit, before tuning colours.
- **Mirrored views.** If any review camera flips the canvas, all modes (review, capture, play) must use the same handedness, or comparisons will mislead.

## Browser automation

- Release pointer lock (`document.exitPointerLock()`) before clicking UI in automated tests.
- Wait on observable conditions (position reached, velocity below a threshold, object drawn) instead of fixed delays.
- Keep failed runs in the record; don't replace them with the passing one.

## Environment

- When a script edits source files on Windows, read and write UTF-8 explicitly and write to a temporary file before renaming. Opening the target for writing first can empty it if the script then fails.
