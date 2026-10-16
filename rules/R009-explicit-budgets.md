# R009 Agree a triangle budget; never relax a limit silently

- **Status:** supported (3 project families; the user reports the large spacecraft's size cost many extra hours after the initial 12+)
- **Applies when:** Game assets, or anything that will be placed many times.
- **Action:** Agree a triangle/draw-call budget at intake. If a check fails against a budget or threshold, report it; don't edit the threshold to pass.
- **Evidence:**
  - Walkable cargo spaceship: the internal limit was changed from 1e6 to 1.1e6 during a repair; final 1,030,620 triangles.
  - Large spacecraft: over 1 million triangles with no stated budget.
  - Motorcycle: 226,504 triangles for one vehicle; no whole-game performance check.
- **Exceptions / counterexamples:** Single hero display models.
- **Verify by:** The budget is in the project log and the final count is reported against it.
