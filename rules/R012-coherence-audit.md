# R012 Audit concept sheets for coherence before approval and modeling

- **Status:** supported (4 project families, including the only failed project)
- **Applies when:** two or more views, plans or images describe the same object, whether generated or supplied.
- **Action:** before asking for approval and before modeling, run the audit in `skill/references/coherence-audit.md`: inventory countable features per view, cross-check views (levels, stair positions, exterior windows against interior layout, outlines, fixed features, avatar clearance), rule out perspective effects with a quick greybox, report conflicts with options, and record the decisions. With many conflicts, regenerate the sheet or make the greybox the master.
- **Evidence:**
  - Three-deck yacht (failed, user verdict: "this was generally a failure since the concept images at the start didn't cohere... windows cutting off sofas etc. I wish the agent detected the concept sheets didn't cohere before modeling"). The prompt asked for consistency, the user approved the look, and at least five rework passes followed before the agent produced a conflicts list. Later clearance work changed the approved layout again.
  - Six-deck superyacht: exterior and plan disagreed on level count (5 vs 6); at least four clarification turns.
  - Procedural island scene: drift continued until the user supplied a greybox as the master.
  - Large spacecraft (user verdict): progress went backwards until the user specified which concept sheets to use.
  - Hours (user estimates): projects whose generated sheets cohered took 1 to 2 hours (hot-air balloon, wearable jetpack, both trains). Both yachts, whose sheets did not cohere, took about 4 hours each, and one failed.
- **Exceptions / counterexamples:** single-view references with nothing to cross-check. The yacht agent also over-reported one conflict that was really perspective, which is why the audit uses a greybox to confirm.
- **Verify by:** a conflicts list with recorded decisions exists before the first non-greybox geometry is built.
