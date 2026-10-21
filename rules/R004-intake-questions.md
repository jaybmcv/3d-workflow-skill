# R004 Stop and ask about style, detail level, interior and use before modeling

- **Status:** supported (4 project families, from the user's own verdicts)
- **Applies when:** Any new model.
- **Action:** As a hard stop before generating or building anything, in one short message with defaults, ask: art style, detail level/budget, whether an interior is modeled and whether avatars walk/sit in it, working doors/windows, intended use and movement, scale, and reference priority.
- **Evidence:**
  - Both robot cats (user verdict): "would have been great to get asked what art style i wanted"; the agent picked toon silently.
  - Walkable cargo spaceship (user verdict): "would have liked the agent to ask me how detailed... and whether the inside should be modeled and navigatable"; doors and windows had to be added later.
  - Small spacecraft with interior (user verdict): same request, working door and interior added later.
  - Passenger train and high-speed train: "can an avatar sit?" came after the model was built; seating was retrofitted.
  - Pilot (2026-10-20): in Claude the skill run asked 3 intake questions and needed 0 corrections; in Codex the skill run skipped intake, chose "no bathroom, no canopy, exterior stairs" itself, and needed a correction round. The soft wording ("ask the ones that apply") was skippable; v0.4 makes it a hard stop and asks about unnamed features.
- **Exceptions / counterexamples:** The user explicitly wants the agent to choose and iterate.
- **Verify by:** The intake message was sent and answers were recorded in the project log before modeling.
