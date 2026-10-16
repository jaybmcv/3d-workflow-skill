---
name: 3d-workflow
description: Plan, build and verify procedural Three.js 3D models from concept art or text briefs, from first concept sheet through a walkable, rideable or game-ready asset. Use when the user asks to create, model, recreate, refine or make game-ready anything in 3D, especially vehicles, characters, buildings or scenes in Three.js.
---

# 3D workflow (v0.2)

Built from 14 real projects (Claude and ChatGPT/Codex), all procedural Three.js from concept art, most later made walkable or drivable in a game. Out of scope for now: Blender, CAD/3D printing and image-to-3D services. If asked for those, say this skill doesn't cover them.

Rule IDs (R001…) point to `rules/` in the source repo, where each rule has its evidence. Technical gotchas are in `references/threejs-pitfalls.md`; read it before writing geometry or browser checks.

## 1. Intake: ask before modeling (R004)

In past projects the user had to add these later, at great cost. Ask the ones that apply in **one short message**, offering a sensible default for each so the user can just say "defaults":

1. **Deliverables:** concept sheet, viewable model, exported GLB, walkable/rideable game asset, website/video? List them back (R003).
2. **Art style:** realistic/PBR, stylised, toon/cel, low-poly, or match the reference exactly? Never pick one silently.
3. **Detail level and budget:** hero asset or background prop? Triangle budget for game use (R009).
4. **Interior:** exterior only, or a modeled interior? If modeled, should avatars walk, sit or lie in it? Working doors, hatches, lifts, windows you can see through?
5. **Use and movement:** static, drivable, flyable, wearable? What constrains motion (rails, water, roads, free flight)? (R007)
6. **Scale:** real dimensions or a scale reference; avatar height if walkable (default 2 m tall, 0.6 m wide).
7. **References:** which images are authoritative, in what priority, and which views they show (R002).

Then apply **ask / assume / mark**:
- **Ask** when the answer changes the structure (interior or not, deck count, movement type, export format).
- **Assume and state it** when cheap to change later (colours, minor trim).
- **Mark as inferred** anything the references cannot show (unseen sides, internal depth).

## 2. Lock the references and cameras before modeling (R002, R005, R011, R012)

- **No multi-view reference yet?** If you're starting from text, one photo or one view, first make a single concept sheet showing perspective, front, side, top and key details, generated **in one image from one prompt** so the views agree. Get it approved. It becomes the authoritative reference. If you can't generate images here, say so and ask the user to make the sheet with a tool that can, or render an orthographic greybox of front, side and top views for approval instead.
- **Audit the sheet for coherence before anyone approves it and before modeling (R012).** Follow `references/coherence-audit.md`: count levels, windows, doors, stairs and fixed features in every view; check that each exterior window lines up with something sensible inside; rule out perspective effects with a quick greybox; then list the conflicts and get decisions. Asking the image generator for consistency is not a check.
- Put the authoritative references in priority order. If they contradict each other (for example an exterior with 5 decks and a plan with 6), list the conflicts and get them resolved **before** building.
- Define **canonical comparison cameras** that match each reference view (position, target, field of view, orthographic or perspective) and get the user to confirm them. Every later comparison uses these exact cameras.
- Write the decisions to a project log (`PROJECT_LOG.md` or similar) as you go: references and priority, cameras, answers to the intake questions, budgets. Long threads lose early context; the log keeps it (R010).

## 3. Check capabilities individually

Do not infer one capability from another. Before relying on a step, check you can actually: view the reference images, generate concept images, run code, render and view screenshots, export and reimport a GLB, and run the target game or engine. Only claim checks that actually ran. If something is unavailable, hand over a script or ask for screenshots instead.

## 4. Build order

1. **Blockout gate (R001).** Build plain masses only. Compare at the canonical cameras for silhouette and key proportions, side by side with the references. No trim, materials or detail until this passes or the user accepts the difference.
2. **If walkable or rideable, lay out the interior now (R006):** avatar clearances, doors, aisles, stairs, lifts, seats, collision proxies, from the first layout, not retrofitted after the exterior is polished.
3. **Detail, materials, lighting** in the agreed style.
4. **Export and reimport** the final file after the last edit; validate it (glTF validator if available).
5. **Integration** into the target runtime, using its normal flows (menus, catalogue, placement) rather than custom test panels.

## 5. Verify honestly (R005, R008)

- **Wait for the scene to be fully drawn** before any screenshot or interaction test (see pitfalls). Confirm each capture is fresh and actually changed.
- **Compare against the frozen references at the canonical cameras.** Never score against images generated from your own model; that only measures self-consistency.
- **Don't promise a fidelity percentage** ("99% match") unless a measurement method is agreed. Use a written checklist of silhouette, proportions, landmark features and colours, and report the differences that remain.
- Check clearances with **whole footprints and both ends** of stairs and ramps, from top, low, entrance and player views, not just centre points.

## 6. Done means each track is evidenced separately (R003)

Before saying it's done, map every deliverable from intake to evidence, and report each of these tracks separately:

| Track | Evidence |
|---|---|
| Visual | Side-by-side at canonical cameras, plus the user's verdict |
| Technical | Export valid, reimports, triangle count within budget |
| Runtime | Works in the target app using its normal controls |
| Release | Merged, deployed, served revision checked (only if asked) |

Passing one track never stands in for another: zero export errors does not mean it looks right. Never relax a budget or a test threshold to make a check pass without saying so (R009).
