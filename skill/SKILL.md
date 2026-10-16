---
name: 3d-workflow
description: Plan, build and verify 3D work (concept visuals, editable meshes and game assets, dimensioned or printable parts, interactive Three.js/web scenes) from text, images or video references. Use when the user asks to create, model, recreate or iterate on anything in 3D.
---

# 3D workflow (v0, provisional)

Rules marked *provisional* come from a small, yacht-heavy set of past projects. Follow them, but report when one clearly does not fit the job.

## 1. Intake: route by deliverable

Before choosing tools, identify which deliverable(s) are requested:

| Deliverable | Typical representation | What "done" means |
|---|---|---|
| Visual concept | Images, renders | Matches references or brief at matched views |
| Editable mesh / game asset | Mesh (glTF/FBX/OBJ/.blend) | Opens and reimports cleanly, sensible topology and scale, matches references |
| Dimensioned or printable part | CAD or solid mesh (STEP/STL/3MF) | Dimensions and tolerances correct, manifold, fits mating parts |
| Interactive scene | Three.js or engine scene | Loads, runs, required interactions and routes work |

One request can combine several deliverables (for example, a yacht exterior, deck plans and a walkable Three.js scene). **List every requested deliverable and its acceptance check before starting (R003).** Show that list to the user.

## 2. Missing information: ask, assume or mark

- **Ask** when the gap changes correctness or would cause expensive rework (mating dimensions, deck count, required export format).
- **State an assumption and proceed** when the choice is cheap to reverse (rear-view styling of an exploratory blockout).
- **Mark as inferred** any geometry the references cannot establish, and say so in the delivery.

Useful inputs to request when they matter: orthographic front/side/top views, overall dimensions or a scale reference, the target use (print, render, game engine, web), and the target app or engine version.

## 3. Check capabilities individually

Do not infer one capability from another. Code execution does not mean Blender, a CAD kernel, GPU rendering or the target engine is available. Before relying on each step, check whether you can actually:

- inspect the reference images,
- generate concept images,
- construct geometry,
- render previews,
- export, then reimport the export,
- run it in the target app or engine.

If a step is unavailable, produce the best fallback (a modeling brief, a script for the user to run, specific requests for screenshots back) and **only claim verification for checks that actually ran.**

## 4. Build order

1. **Single source of truth (R002, provisional).** Establish one master layout or model with explicit dimension assumptions. Derive every view, plan and render from it. If image references contradict each other, list the contradictions and resolve them (ask, or assume and mark) before modeling.
2. **Blockout gate (R001, provisional).** Build a blockout. Compare it with the references at matched cameras against silhouette and key proportion criteria. Do not start materials, trim or detail until this gate passes or the user accepts the deviation.
3. Detail, materials, lighting.
4. Export and reimport. Check scale, orientation, manifold/topology as relevant.

Track **visual acceptance** (looks like the reference) and **technical validity** (exports, opens, dimensions, runs) separately. Passing one never substitutes for the other.

## 5. Completion check (R003, provisional)

Before saying the work is done, map every item from the intake list to an artifact that exists, opens, and that you have inspected. Report each item as passed, failed, or not verified (with why). A strong hero render does not cover a missing plan or a missing editable file.
