# Build for a client — design + build + hand-off

## Boundary

Discovery, pricing and the conversation live in the sales process (a contact →
close pipeline, with evidence kept in one folder per client). The community kit (interview → workflow package) is its own product. This file
covers designing, scaffolding and handing over the workspace itself.

## Inputs

- The person's words: one recent completed example of their repeating unit,
  their vocabulary, their volume, their checks.
- What they do **today**, kept separate from what is **proposed**. Unknowns are
  labeled, never guessed.

## Design

1. Find the repeating unit → the smallest form that fits (`references/forms.md`).
2. One workspace per mental mode; one stage per gate; folder names in **their**
   words. The method vocabulary can stay in the contracts if they want it.
3. Contracts in their language, six fields (`references/contracts.md`).
4. Every workspace declares its product home and its person check — a workspace
   without a check is a workspace that will drift.
5. Vocabulary: the forms, the contracts and the walk test speak the paper's
   canon where it doesn't conflict with local hard rules — the deliverable
   should read as the real method.

## Scaffold

- **Instantiate by copying, then edit.** If they have no factory yet, the factory
  is part of the deliverable: a minimal `_templates/` plus a scaffold note, so
  their next workspace never starts from a blank page.
- Separate factory material from run material on day one (`_shared/` +
  `_templates/` vs the run folders).
- No aggregate `output/`; products live in their runs.

## Walk-test

The person runs **one real piece of work** through the new structure, in front
of you. Their mistakes are the fixes to the contracts: a file in the wrong place
means the route or the naming is unclear; a hesitation means a missing Command
line. Do not run the real workflow yourself — the structure must survive their
hands.

## Hand-off

They leave with:

1. A map they can read in one screen (their `AGENTS.md`/`CLAUDE.md`, their language).
2. The growth rules in their words (when a new folder, stage or workspace is allowed) — `references/extend.md` shape.
3. Where the receipts go and what each check means.
4. One completed example inside the structure (the walk-test artifact).

And the same discipline you work by: nothing changes in their folders without
their go.

## Worked example (shape)

A client repo with a root `CLAUDE.md` (map) + `CONTEXT.md` (router), one
workspace per mental mode (e.g. `brand/`, `ideas/`, `scripts/`), each with its own
`CONTEXT.md`, `_shared/`, `_templates/` and product home; a `setup/` folder holds the
factory configuration and the open questions; an `ops/` folder covers how the repo is shared.
