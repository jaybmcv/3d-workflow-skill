# R011 Generate one consistent multi-view concept sheet before modeling

- **Status:** hypothesis (4 project families, with confounds; necessary but not sufficient, see R012)
- **Applies when:** the starting point is text, a single photo or a single view.
- **Action:** generate one concept sheet with perspective, front, side, top and key detail views, in a single image from a single prompt so the views agree. Get the user's approval, then model from that sheet as the authoritative reference.
- **Evidence:**
  - The four fastest game-integrated projects all started this way: hot-air balloon (about 1 hour), wearable jetpack (1.5 hours, from one photo), passenger train and high-speed train (about 2 hours each).
  - The three slowest (motorcycle about 13 hours, sports car 12+, large spacecraft 12+) matched existing user-supplied art instead.
- **Exceptions / counterexamples:**
  - Six-deck superyacht: concept images were generated, but as two separate prompts (exterior with five levels, plan with six) that disagreed; it still took 4+ hours. Hence "one image, one prompt".
  - Three-deck yacht (failed): the sheet *was* one image from one prompt asking for the "SAME boat" and matching plans, and still didn't cohere. It took about 4 hours, like the six-deck yacht, against 1 to 2 hours for the projects whose sheets cohered. A single sheet helps, but it must also pass the R012 audit.
  - Both robot cats matched user drawings in under an hour, but had no game integration.
  - Confounds: the fast projects came later and reused game integration work from earlier ones, and were simpler objects. Hours are the user's estimates.
- **Verify by:** the pilot evaluation; compare hours and corrections for a brief that starts from text with and without this step.
