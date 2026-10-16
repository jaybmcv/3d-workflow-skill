# R007 Settle how it moves before building controls

- **Status:** supported (2 project families)
- **Applies when:** Vehicles and anything that moves in a game.
- **Action:** Ask what constrains motion (rails, water, roads, free flight, wearable) and how it differs from existing vehicles before choosing a controller. Don't assume the game's generic vehicle behaviour or tests apply.
- **Evidence:**
  - Passenger train: free A/D steering was built, then "this should only ride on specific rails" forced a rework.
  - Hot-air balloon: generic fleet tests expected it to "reverse after forward motion".
- **Exceptions / counterexamples:** None recorded.
- **Verify by:** The motion model is written in the project log before the controller is built.
