# Restructure — give an existing folder ICM shape

Adapted from `icm-architect` (Van Clief, MIT — see `../LICENSE`). For a
folder, repo, or vault that already holds work. Building from a described
process is the create mode in `../SKILL.md`; this is the retrofit. Seven
steps, each ending in a person check: stop, let the person read the output,
continue.

## 1. Inventory before touching

List the tree. For each area note: what it is, when last touched, what refers
to it. Never delete or move in this pass.

## 2. Find the hidden form

Ask the owner (or infer and confirm): what is the repeating unit here? Where
does work enter and leave? The mess usually contains a real pipeline, library,
or map that grew without a skeleton — extract it, don't replace it. Interview
the folder the way you'd interview the person (`forms.md`).

## 3. Classify every file

| Role | What it is | Where it goes |
|---|---|---|
| **Catalog** | identity / routing | becomes or feeds `AGENTS.md` |
| **Contract** | how a step works | becomes a `CONTEXT.md` |
| **Factory** | stable reference | `_shared/` · `docs/` |
| **Product** | run-specific artifact | the run's product home |
| **Dead** | stale, duplicated, superseded | the attic — labeled, never deleted |

Dead only after step 4 confirms nothing depends on it.

## 4. Verify reference integrity — before proposing

Read `reference-integrity.md` and enumerate referrers: in-vault, sibling-path,
symlink, external. A file with a live referrer is held, or moved only if
every referrer is updated in the same change.

## 5. Propose before moving

Present the target tree and a migration map (old path → new path → role →
referrers found). Get the person's approval — tooling never claims it. The
target obeys the local hard rules whatever the incoming shape: products live
in the run that produced them (no stage `output/` piles), one entry map (never
two hand-maintained copies), check artifacts at stage level.

## 6. Migrate — copy, verify, then remove

Case-folded destination check first. Copy → verify parity (file count +
content hash) → remove. Then write the entry file and contracts,
de-duplicate toward one home per fact (leave a link where a copy lived), and
separate method from instance: blank templates apart from filled-in
deployments. From here on, scaffold from the factory — `_templates/`, or the
repo's own scaffold command if it has one.

## 7. Validate and report

Walk test (`../SKILL.md`), plus the person running one real piece of work
through the new shape (`build-for-others.md` for client hand-offs).
Regenerate derived files (the repo's status/check command, if it has one);
never hand-edit a projection. Report as rows: `path` · finding · fix ·
severity (`audit.md`).
