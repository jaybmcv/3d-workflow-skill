# Concept sheet coherence audit

Run this **before modeling**, and before asking the user to approve a concept sheet. A sheet can look great and still describe an object that can't exist: in one failed project the generation prompt said "SAME boat" and "maintain correspondence", the user approved it, and hours of rework followed because the views didn't agree ("windows cutting off sofas"). Asking for consistency in the prompt is not a check.

Approval of how it **looks** is not approval of how it **fits together**. Do the audit, then ask for approval of both.

## 1. Inventory each view

For every view (perspectives, elevations, plans, details), list what you can count or place:

- Levels or decks, and the overall length : height : width proportions.
- Windows and doors per side, and which bay or room each sits in.
- Stairs, ladders, lifts and hatches: which level they connect and where along the length.
- Distinctive fixed features (hot tub, helipad, mast, engines, wings) and their positions.
- Labels or dimensions printed on the sheet.

## 2. Cross-check the views against each other

- Same number of levels and decks in every view.
- Stairs and lifts at the same position in plans and elevations, landing somewhere sensible on both levels.
- **Every exterior window lines up with something sensible inside.** No window cutting through a sofa, bed, bulkhead or stair. This is the check that failed in the yacht case.
- Plan outlines match the widths and lengths implied by the elevations.
- Fixed features in the same place in every view.
- If anything will be walkable: openings tall and wide enough for the avatar (default 2 m by 0.6 m).

## 3. Rule out perspective tricks cheaply

Perspective views can make things look inconsistent when they aren't. Before calling something a conflict, build a 10-minute **greybox** (plain boxes) from the plan and render it at the reference camera angles. If the greybox lines up, it was perspective. In the yacht case the agent later admitted it had "overstated the certainty" of one conflict for this reason.

## 4. Report conflicts and get decisions before modeling

Make a short conflicts list (or an annotated image), one row per conflict:

| Conflict | View A says | View B says | Options | Recommendation |
|---|---|---|---|---|

Ask the user to choose, or to accept your recommendations. Record the decisions in the project log.

## 5. If there are many conflicts, fix the sheet, not the model

With more than a handful of conflicts, don't model around them. Either regenerate the sheet with the decisions written into the prompt and audit again, or make the greybox the master and render the remaining views from it. From then on, the greybox is the reference, and nothing later should contradict it.
