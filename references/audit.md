# Audit — the anti-rot checklist

Structure drifts the same ways everywhere. Run the checklist, then **report
findings (path · finding · fix) and fix only with approval.** If the repo has a
mechanical checker, run it first; findings land wherever the repo keeps its audit
records. This skill's checklist is for everything that checker cannot see.

## The checklist

| # | Finding | Fix |
|---|---|---|
| 1 | Contract past ~25 lines of core | find the missing command or reference file; split, don't summarize |
| 2 | `CONTEXT.md` past ~100 lines | move stable knowledge to `_shared/`/`docs/`; keep routing + process |
| 3 | Route missing, or living in a contract | routes live in `AGENTS.md`; contracts say what the work is |
| 4 | One fact in two places | keep one home, replace the other with a path |
| 5 | Placeholder residue in active work (`YYYY-MM-DD-*` blanks, `_[to define]_`) | templates are the only home of placeholders; files appear at their stage's moment |
| 6 | Aggregate `output/` or exports outside their run | move products to the run that produced them |
| 7 | A `gate/` subfolder left from the retired pattern | flatten: check artifacts live at stage level (decision 2026-10-21) |
| 8 | Approval claimed by file presence | delete the claim; approval is a human act, receipt in `REVIEW.md` |
| 9 | Person check missing or vague | write what a human must actually read or verify |
| 10 | Skill listed without a trigger | give it a moment ("before X moves to Y") or unlist it |
| 11 | Handoff documented on one side only | document it in, on both workspaces |
| 12 | Generated / derived file hand-edited | restore it, fix the record at its own gate, regenerate |
| 13 | Ad-hoc stage or folder bypassing the factory | scaffold from `_templates/`; promote the repeatable part |
| 14 | Orphaned template (never used, or holding run content) | empty or delete it; the factory holds no run content |
| 15 | Regenerable media committed (renders, frames, stills, previews) | keep words + irreplaceable recordings in git; rebuild the rest (media policy) |
| 16 | Products piled in a stage's `output/` (incoming scaffold shape) | move products to the run that produced them (finding 6) |
| 17 | Hand-maintained status log (`log.md`-style catalog) | status = file presence; make the log generated or delete it |

## Severity

1. **Broken gates** (8, 9, 17) — the system can lie about approval or status.
2. **Broken homes** (4, 6, 12, 13, 16) — facts drift apart.
3. **Wasted context** (1, 2, 3, 5, 7, 10, 11, 14, 15) — cost and confusion.

## How to report

One row per finding: `path` · what is wrong · the fix · severity. Group by
workspace. Never fix silently: the structure is the person's, and every fix
changes how they work.
