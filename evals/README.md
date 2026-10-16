# Pilot evaluation protocol (v0)

Goal: check whether skill v0 helps on two briefs under fixed conditions. It cannot show a general reliability improvement.

## Setup
1. Write two **new** briefs. Every past project has been used to write rules, so none can serve as a test:
   - one vehicle or character from a single concept image (exercises R001, R004, R005),
   - one object the user will walk through and sit in, starting from a text brief (exercises R002, R003, R006, R008).
2. Freeze each brief and its checklist **before** any run. Briefs and results usually contain private project material, so keep them in the private case archive (`evals/` there), not in this repo.
3. Fix model, tools, starting assets and budget (time or number of generations) for all runs.

## Runs (4 total)
For each brief, one baseline run without the skill and one run with it, each in a fresh session. Keep every result, including failures and abandoned runs, in the private archive under `evals/results/<brief>/<A|B>/`. Label runs A/B randomly so you don't know which is which when scoring.

## Scoring
- Cost: wall-clock hours, credits or tokens if visible, and the number of user corrections needed to reach the checklist. Past projects took up to 13 hours, so this is the main thing to beat.
- Intake: did the run ask the R004 questions before modeling?
- Required deliverables: pass/fail each.
- Visual criteria: score against written anchors (for example 0 = wrong silhouette, 1 = right silhouette but proportions off, 2 = matches at all checked views), using the same cameras, framing and lighting for both runs.
- Record each judgment and the file that supports it.

## Adoption bar
Clear improvement on one brief, no meaningful regression on the other, no new mandatory failures. Do more testing only for mixed results, unclear differences or a serious regression.

After revising the skill from these results, these two briefs become regression tests. Any later claim that it generalizes needs a fresh brief.
