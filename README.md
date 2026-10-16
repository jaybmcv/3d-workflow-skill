# 3d-workflow-skill

An agent skill for planning, building and verifying 3D work: concept visuals, editable meshes and game assets, dimensioned or printable parts, and interactive Three.js/web scenes.

**Status: v0, provisional.** The rules are drawn from a small number of real projects and have not been evaluated yet. See `rules/` for the evidence behind each one.

## Install

The skill lives in `skill/` and uses the shared `SKILL.md` format.

- **Claude Code:** copy or symlink `skill/` to `~/.claude/skills/3d-workflow/` (personal) or `.claude/skills/3d-workflow/` (project). This repo already links it at `.claude/skills/3d-workflow`.
- **Codex:** copy or symlink `skill/` to `.agents/skills/3d-workflow/`. Already linked in this repo.
- **Claude.ai / ChatGPT:** zip the `skill/` folder and upload it as a custom skill where supported. Otherwise attach `skill/SKILL.md` to the conversation and ask the assistant to follow it.

## Layout

```
skill/SKILL.md   The skill: route by deliverable, ask/assume/mark, capability checks, build order, completion check
rules/           One file per rule: when it applies, action, evidence, exceptions, how to verify, status
evals/README.md  Pilot evaluation protocol and adoption bar
```

## How rules get here

Retrospectives of past projects are recorded as evidence in a separate private archive. A lesson becomes a rule here only with its evidence and verification method stated, and starts as `hypothesis`. Rules move to `supported` or `evaluated` only after more cases or an evaluation back them up, and are marked `superseded` rather than deleted.
