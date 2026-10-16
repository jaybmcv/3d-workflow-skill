# R008 Don't trust a screenshot or test until the scene is fully drawn

- **Status:** supported (4 project families)
- **Applies when:** Any browser screenshot, visual check or interaction test.
- **Action:** Wait for shader compilation and confirm every part is drawn before capturing or testing; confirm each capture is fresh. See references/threejs-pitfalls.md.
- **Evidence:**
  - Hot-air balloon: envelope missing while riding; at least four diagnostic passes before shader preparation was found.
  - Wearable jetpack: a passing 15-check run, but the observer image had no jetpack ("visible flags alone are insufficient proof").
  - Passenger train: "parts of the cabin were missing" until checks waited for drawable meshes.
  - Humanoid robot cat: stale captures led to a misread correction round.
- **Exceptions / counterexamples:** None recorded.
- **Verify by:** Captures are taken after an explicit readiness wait and differ from the previous capture when expected.
