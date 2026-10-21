# R013 Measure the fit to reference photos instead of eyeballing it

- **Status:** supported (2 project families, one of them a paired comparison)
- **Applies when:** the model must match photos or artwork.
- **Action:** fit a camera to each reference image from landmark points, overlay the model's edges on the image, and report reprojection error after each pass. Anchor scale on a known-size object in the photos. Trace profiles from near-orthographic photos. Separately, inspect low, high and unscripted angles before declaring the model ready.
- **Evidence:**
  - Roadster from a reveal video and ten press photos, built twice with the same inputs. The Claude build traced profiles on metric grids, solved photo cameras by least squares (reprojection error 48.5 to 31.0 px), anchored scale on the licence plate (body width 1.98 m vs model 2.00 m), and was judged a success ("representations are correct"). The Codex build tuned surfaces by eye at preset angles, declared itself "ready for a materials pass", then the user found a raised shoulder and an empty body from a low angle; it was judged a failure, with the user noting the other build "got the form down better in the same amount of time".
  - Packed spacesuit pilot: the skill run fitted the reference camera numerically to landmarks and scored 6/8 on looks against 3/8 for the run without the skill.
- **Exceptions / counterexamples:** the roadster pair differs in platform as well as method, so platform may explain part of the gap. Measured fit doesn't cover parts seen in only one photo (the roadster's seat backs were still wrong).
- **Verify by:** each pass reports overlay images and a reprojection error at the reference cameras; the ready claim lists the extra angles inspected.
