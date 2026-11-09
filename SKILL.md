---
name: icm
description: |
  Build, extend, audit, and restructure ICM (Interpretable Context
  Methodology) workspaces — folder structures that are the agent's
  instructions: a map (AGENTS.md), a room per working folder (CONTEXT.md
  contracts), tools loaded at point of use. Use when creating a workspace,
  restructuring an existing folder, repo, or vault into ICM shape, mapping a
  body of work so later agents can edit it ("map this repo", "what would a
  change hit"), adding a folder,
  stage, or workspace to an existing one, writing or editing AGENTS.md /
  CONTEXT.md / contracts / routing tables, choosing what form a structure
  should take, scaffolding from templates, checking a structure for drift, or
  explaining how an ICM workspace is meant to work. Do NOT use for ordinary
  work inside an existing workspace — running a stage, writing content,
  grading a call, editing code. Those follow that workspace's own AGENTS.md
  routing.
license: MIT
metadata:
  version: "1.1.1"
---

# ICM — structure work

ICM (Interpretable Context Methodology — Jake Van Clief; method source:
`https://github.com/RinDig/icm-architect`, arXiv:2603.16021) makes a folder
structure the agent's instructions: the agent loads only the context the task
needs, and every working folder states its job and its human check. This skill
governs **structure work** — creating, extending, auditing and explaining
workspaces. Ordinary work inside a workspace follows that workspace's own
`AGENTS.md`; this skill is not the daily driver.

Where a local `AGENTS.md` states a rule more strictly, the local rule wins: this
skill is the portable method, the workspace is the authority.

This skill absorbs `icm-architect`'s unique material — restructure mode,
the reference-integrity gate, the System map form — adapted to these rules.
The upstream skill is **not** installed alongside: one method, one home
(decision 2026-10-23, pinned `e16cafe`; `LICENSE`).

## The model

- **L0 — the map** (`AGENTS.md`): identity, hard rules, task routing. Routes only.
- **L1 — the root `CONTEXT.md`** (routing): how the project's parts connect, status rules. Its shape and name are the project's own — "the loop" is one workspace's label for it, not the rule.
- **L2/L3 — the rooms** (`CONTEXT.md` per workspace / stage): what the work is —
  job, inputs, command, outputs, person check. Never the whole project tree.
- **L3 — the tools** (`_shared/`, `_templates/`, skills): stable reference and
  factory material, loaded at point of use.
- **L4 — the work** (output, artifacts, records): products at their stage's gate.

A contract is six fields and thin (≤ 25 lines of core):
**Job · Inputs · Command · Outputs · Person check · Do NOT load.**
A fat contract means a missing command, not more prose.

## Invariants

1. **One home per fact.** Reference by path, never copy. Two homes for one fact means one of them is wrong.
2. **Routes only in `AGENTS.md`; contracts say what the work is.** Never the other way around.
3. **Factory vs product.** Scaffold only from the factory (`_templates/`, or the repo's own scaffold command). Never hand-build what the factory builds; never leave placeholder residue in a run.
4. **Instantiate by copying, then edit.** The factory holds no run content; the run holds no template residue.
5. **The person check is a human act.** Nothing advances until a person has read the previous output. Tooling never claims approval; receipts live with the artifact (`REVIEW.md`).
6. **No aggregate `output/`.** Products live in the run that produced them; a stage's check artifacts live **directly in the stage folder** — no `gate/` nesting (the structure already says what they are).
7. **Status = what exists.** File presence, never hand-written summaries.
8. **Records vs projections.** Compiled/derived files are regenerated, never hand-edited; the record is corrected at its own gate.
9. **Smallest structure that fits.** The repeating unit of work picks the form. Start minimal, grow on evidence.

## Modes

| You are… | Do this | Read |
|---|---|---|
| Creating a workspace | find the repeating unit → pick the smallest form → scaffold from the factory → wire the routes | `references/forms.md`, then `references/contracts.md` |
| Writing or editing a contract / routing table | six fields, size test, trigger column | `references/contracts.md` |
| Extending a workspace | run the growth test before creating anything | `references/extend.md` |
| Auditing structure / drift | run the anti-rot checklist; report findings, fix only with approval | `references/audit.md` |
| Restructuring an existing folder / vault / repo | inventory → classify → migration map at a human gate → copy-verify-remove | `references/restructure.md` (move safety: `references/reference-integrity.md`) |
| Mapping a tree so later agents can edit it | gated slices: catalog → nouns → verbs → change-impact → re-verify | `references/system-map.md` |
| Building one for a client | design from their evidence → scaffold with their factory → walk-test with the person | `references/build-for-others.md` |
| Explaining how ICM works | the model and the invariants above | `references/contracts.md` |

## Walk test

Validate any structure — new, extended, or restructured — by walking it cold,
as an agent with no memory:

- Root: *where am I* / *where do I go* — entry file plus two reads at most?
- Room: contract names exact input paths, job, output, person check?
- Status: derivable from what exists, with no hand-written summary?
- Payload: routing file carrying content? A fact in two homes?
- After a move: does every pre-existing reference still resolve?
- Tokens: entry + one contract + its inputs ≈ 2k–8k.

If a step fails, fix the structure — move or split files, don't explain more.
System map extras: `references/system-map.md`.

## Guardrails

- **The ladder: chat → saved prompt / skill → folders + one agent.** Climb
  only when the rung below is genuinely automated and repeating — a workspace
  for a thing done twice is scaffolding, not architecture.
- **Where ICM loses:** real-time multi-agent loops, high-concurrency serving,
  automated mid-pipeline branching — those need framework code. ICM is for
  sequential, human-reviewed, repeatable work.
- **Anti-patterns:** entry files duplicated by hand (generate or point);
  schemas naming files that renamed themselves; hand-edited generated
  indexes; patterns declared top-down (one complaint is a gripe — three
  independent occurrences are structure).

## Never

- Restate another file's rules here — point at their home (the paths above and in the workspace's `AGENTS.md`).
- Grow a `CONTEXT.md` into an encyclopedia: stable knowledge goes to `_shared/` or `docs/`.
- Add a stage, workspace or folder without the growth test in `references/extend.md`.
- Invent structure before knowing the repeating unit of work.
- Build a whole workspace up front — start minimal and grow on what goes wrong.
