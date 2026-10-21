# 3d-workflow-skill

An agent skill for planning, building and verifying procedural Three.js models from concept art or a text brief, from the first concept sheet through a walkable, rideable or game-ready asset.

**Status: v0.5.** Piloted on two briefs (v0.3): the skill runs were the user's pick both times and passed more required checks, at about 2.5× the agent time. Rules come from 16 real projects (14 successes and 2 failures) across Claude and ChatGPT/Codex. All delivered in Three.js; one used headless Blender to smooth a car body, and the skill allows Blender as an optional helper. A Blender-only workflow, CAD and 3D printing, and image-to-3D are out of scope for now. See `rules/` for the evidence and status behind each rule.

## Install

The skill lives in `skill/` and uses the shared `SKILL.md` format.

- **Claude Code:** copy or symlink `skill/` to `~/.claude/skills/3d-workflow/` (personal) or `.claude/skills/3d-workflow/` (project). This repo already links it at `.claude/skills/3d-workflow`.
- **Codex:** copy or symlink `skill/` to `.agents/skills/3d-workflow/`. Already linked in this repo.
- **Claude.ai / ChatGPT:** zip the `skill/` folder and upload it as a custom skill where supported. Otherwise attach `skill/SKILL.md` to the conversation and ask the assistant to follow it.

## Layout

```
skill/SKILL.md                         The skill: intake questions, reference and camera lock, build order, verification, done criteria
skill/references/coherence-audit.md    How to check concept sheets agree with each other before modeling
skill/references/threejs-pitfalls.md   Technical gotchas that each cost a fix round in a past project
rules/           One file per rule: when it applies, action, evidence, exceptions, how to verify, status
evals/README.md  Pilot evaluation protocol and adoption bar
```

## How rules get here

Retrospectives of past projects are recorded as evidence in a separate private archive. A lesson becomes a rule here only with its evidence and verification method stated, and starts as `hypothesis`. Rules move to `supported` or `evaluated` only after more cases or an evaluation back them up, and are marked `superseded` rather than deleted.
