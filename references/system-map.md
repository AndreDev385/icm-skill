# System map — map a tree so later agents can edit it

Adapted from `icm-architect` (Van Clief, MIT — see `../LICENSE`). The form
for a body of work someone will change: a repo, a markdown vault, or a mix.
The deliverable is a walkable graph — the nouns, how they move, and what else
moves if you touch one — so a later agent answers "what is X" and "what would
a change hit" without slurping the tree.

When this is the right form: `forms.md`. Not for a production line
(Pipeline), an organization (Context map), or how something thinks (Knowledge
bundle). If one `CONTEXT.md` plus an index answers both questions, stop
there — no `objects/`/`processes/`/`effects/` for a dozen files.

## Where it lives

Propose before writing. A `map/` shelf beside the existing orientation
(`docs/`, the vault root) so the subject's entry file gains one routing row —
never inside `src/`, never cards scattered through the tree. The entry file is
`AGENTS.md`; in a client repo use what their tool reads (`CLAUDE.md` for
Claude Code). One maintained map; any twin is generated, never hand-edited.

## Target tree (smallest that carries the work)

```
map/
├─ AGENTS.md              the catalog
├─ CONTEXT.md             how to walk; universes; name collisions
├─ _meta/schema.md        closed node types
├─ _templates/            object.md, process.md
├─ objects/
│  ├─ CONTEXT.md
│  ├─ _index.md           one line per noun (stub | verified | stale)
│  └─ <cluster>/          cards, clustered by how an editor asks
├─ processes/             only after nouns exist; only real movements
└─ effects/CONTEXT.md     which cards to open before a change
```

No empty `processes/` or `effects/`. Three verified noun clusters beat seven
imagined shelves.

## Universes

| Universe | Meaning |
|---|---|
| **live** | in force — implement and cite against these |
| **leftover** | still present, no longer the main path |
| **ghost** | named or filed, not wired — stubs, dead types, docs of functions that do not exist |

Product language and file names often disagree. State both once in the
catalog ("Chat = `Incubator`").

## Audit pipeline (gated slices)

Stop after each slice; a person or a cold walk reads the output first.

- **0 Inventory** — no cards. Classify areas (the roles in
  `restructure.md`), infer nouns and verbs, mark universes, propose the tree
  and clusters. Approval before writing.
- **1 Catalog** — `AGENTS.md`, `CONTEXT.md`, schema, templates, and
  `objects/_index.md` with **stub lines** for every noun not yet filled. One
  routing row from the subject's entry file. Walk: "where do I go to
  understand X?" lands in two hops.
- **2 Nouns** — one card per type, copied from `_templates/object.md`. Source
  of truth: code is the type/table/module, cited `path:line`; markdown is the
  file that owns the fact. `status: verified` only with a date and citations;
  `stale` is allowed, a confident wrong date is not. Fill **If you change
  this** as Hits / Does not hit — first order only; "does not hit" names the
  obvious next noun that is the *wrong* one.
- **3 Verbs** — only movements that actually run or are actually followed:
  auth, publish, hydrate, promote — don't invent a sixth. Card: Input →
  Movement → Output, numbered steps with citations, `consumes`/`produces`
  links to object cards, Hits / Does not hit.
- **4 Change-impact index** — `effects/CONTEXT.md` is a catalog of "if you
  are changing X, open these cards"; it copies nothing from the cards. Walk
  it backwards, then ask the owner what *outside* the tree points in
  (configs, cron, agents, issue trackers) and record each hit on the card it
  lands on — nothing in the tree names these, so no card will until you go
  looking.
- **5 Re-verify** — rip the load-bearing claims again, especially the
  waterfalls. Wrong waterfalls cost more than missing cards.

## Object card (required sections)

1. One sentence — product name and file name if they differ
2. Why this shape — the load-bearing why, not a field tour
3. Shape — keys, constraints, owning files, with citations
4. Connected to — owns / owned-by / joins / looks-like-but-is-not
5. If you change this — Hits / Does not hit
6. Surfaces — who reads/writes (apps, agents, humans, none)
7. See — the source file; at most one as-built page

## Walk test (this form)

Cold agent, no memory of the subject:

1. The subject's entry file — is the map one hop away?
2. The catalog — can it say what the colliding names mean without opening a
   card?
3. One object card — cites source, states the why, gives a first-order
   waterfall?
4. `effects/` — can it name what a stated change hits and what it does not?
5. One `See` link — lands on source, not another essay?
6. Token check: entry + hub + one card ≈ 2k–8k tokens.

## Watch for

- Aspiration mapped as live — ghost it.
- Behaviour copied into cards — point at the file that owns it.
- Empty `processes/` / `effects/` shelves.
- Two hand-maintained entry files that drift.
- `verified` cards with no citations.
- Slurping all of `objects/` in a later session — the catalog exists so you
  don't.
- An `effects/` index that only walks outward: what points INTO the tree from
  outside is invisible from inside it.
