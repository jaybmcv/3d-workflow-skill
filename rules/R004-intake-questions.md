# R004 Ask about style, detail level, interior and use before modeling

- **Status:** supported (4 project families, from the user's own verdicts)
- **Applies when:** Any new model.
- **Action:** In one short message with defaults, ask: art style, detail level/budget, whether an interior is modeled and whether avatars walk/sit in it, working doors/windows, intended use and movement, scale, and reference priority.
- **Evidence:**
  - Both robot cats (user verdict): "would have been great to get asked what art style i wanted"; the agent picked toon silently.
  - Walkable cargo spaceship (user verdict): "would have liked the agent to ask me how detailed... and whether the inside should be modeled and navigatable"; doors and windows had to be added later.
  - Small spacecraft with interior (user verdict): same request, working door and interior added later.
  - Passenger train and high-speed train: "can an avatar sit?" came after the model was built; seating was retrofitted.
- **Exceptions / counterexamples:** The user explicitly wants the agent to choose and iterate.
- **Verify by:** The intake message was sent and answers were recorded in the project log before modeling.
