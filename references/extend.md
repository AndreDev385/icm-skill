# Extend — grow the structure without rotting it

## The growth test (run before creating anything)

| The thing is… | It becomes… |
|---|---|
| a step with its own command and its own person check | a **new stage** (`NN_*/` + contract) in the workspace that owns the sequence |
| a new mental mode (different context, different load set) | a **new workspace** (own `CONTEXT.md`) |
| the same material needed across runs | a **`_shared/`** fact (one home) or a **`_templates/`** scaffold |
| one artifact of an existing run | a **folder inside that run's product home** |
| a new platform / tool / channel | a **file in `_shared/`** — never a stage |
| recurring maintenance after the work "ends" | a drawer stage after the last one (e.g. `06_support/`) |
| a capability whose instructions belong at one workflow moment | a **skill** (`<name>/SKILL.md` in the skills folder) + a route with its trigger in `AGENTS.md` |

If none of these fit, create nothing yet — name the repeating unit first
(`references/forms.md`).

## New skill

Drop the skill folder in (its `SKILL.md` carries a trigger-rich description),
then wire it: one route row per affected `AGENTS.md`, each naming the moment it
loads. No index or registry file — the directory listing is the status and the
routes are the wiring. A hand-maintained table of installed skills is a
projection, and it rots.

## Promotion to the factory

Something that repeats across runs gets promoted once: `_templates/` if it has
shape, `_shared/` if it is a fact. The day the factory takes over, the ad-hoc
copies move to the attic (superseded, not deleted) — two homes for one fact is
exactly the drift this skill exists to prevent.

## Structure change checklist

1. Name the change and its home (one home per fact).
2. Grow the structure via the table above; scaffold from the factory — copy, then edit.
3. Write or adjust the contract (six fields: `references/contracts.md`).
4. **Update the route in `AGENTS.md`** — the route is part of the change.
5. Update the parent `CONTEXT.md`'s table and handoff (both sides of any handoff).
6. Regenerate derived files (with the repo's status/check command, if it has one);
   never hand-edit a projection.
7. Record the decision as a dated note in the file that governs the thing decided.

## Change discipline

- Records are corrected at their stage's gate; everything downstream is regenerated.
- Scope changes are re-agreed with the person first, then recorded — never
  rewritten silently.
- Retired material moves aside with a label (the attic pattern): superseded,
  not deleted.
