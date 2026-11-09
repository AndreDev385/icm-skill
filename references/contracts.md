# Contracts — the map, the rooms, the shape

## The six fields (every working folder)

| Field | Answers | Prevents |
|---|---|---|
| **Job** | what this folder does, one or two sentences | working in the wrong room |
| **Inputs** | what to read before starting (by path) | loading the whole workspace |
| **Command** | how the work actually happens (real commands / moves) | improvised process |
| **Outputs** | what is produced and where it lands (the product home) | files in the wrong place |
| **Person check** | what a human must read or verify before work advances | tooling claiming approval |
| **Do NOT load** | what must stay out of context here | wasted context, cross-contamination |

Thin: ≤ 25 lines of core. When a contract outgrows that, the missing piece is
usually a command or a reference file — find it before writing more prose.

## `AGENTS.md` — the map (L0)

Identity in 2–3 sentences · hard rules · one task-routing table
(`You want to… | Go to | Also load`) · nothing else. One screen: anything more
is a `CONTEXT.md` hiding inside the map.

## `CONTEXT.md` — the room (L1–L3)

- **One job line** — what work happens here, what is upstream and downstream.
- **The stage table** (`Stage | Command | Output | Person checks`) — or, for a
  single stage, the six-field contract.
- **Handoff** — what comes in and out, documented on **both** sides.
- **Status rules** — what file presence means; no hand-written summaries.
- **Decisions (dated)** — dated notes in the file that governs the thing decided.
- **Do NOT load.**

Size: 25–80 lines is right. Under 15 and the agent lacks context; over 100 and
stable knowledge has accumulated that belongs in `_shared/` or `docs/`.

## Load tables

- The **Skip** column matters more than the Load column: not loading the wrong
  thing is what keeps the context clean.
- Every skill row needs a **trigger** ("before a draft moves to `final/`").
  "Available" is not a trigger.

## Naming and placement

- Date-prefixed records (`YYYY-MM-DD-<what>.md`); slug folders per run.
- `_shared/` = stable reference · `_templates/` = the factory (placeholders live
  only here) · `docs/` = how and why · check artifacts live **at the stage level**
  (no `gate/` nesting — the structure says what they are) · the run folder = products.
- **Media policy:** git keeps what cannot be regenerated or re-downloaded — words,
  code, decisions, receipts, and the recordings that can't be re-recorded. Renders
  and intermediates are rebuilt, not stored (disk + a media mirror, named by the
  run's record). A lean repo travels; the pixels don't need to.
- Products live in the run that produced them. No aggregate `output/` folders.

## Exemplars (shape)

- Six-field stage contract: any stage folder's `CONTEXT.md` in a pipeline workspace.
- Room with a stage table and status rules: a workspace's `CONTEXT.md` with its
  stage table.
- Client deliverable map + router: a repo-level `CLAUDE.md` (map) and its
  `CONTEXT.md` (router).
