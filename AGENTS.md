# Repository Working Rules

This directory is the working space for one task: a 10-minute talk for the
SEDS Conference 2026 Data Science Slam (1 Oct 2026, Konstanz). No research
happens here — the science already exists in a separate, finished repository.
The talk has been delivered; this repository now keeps the script, slides,
assets, and the recorded live vote.

## HARD RULE — No infrastructure material in this repository

Nothing about servers, hosts, hostnames of internal services, SSH, tunnels,
tokens, keys, `.env` files, databases, or per-participant vote data belongs
here — not in code, docs, commit messages, or chat-history exports. The only
vote data kept is the aggregate record in `docs/vote-record.md` and
`results/`. Never copy credentials or runtime data into any repository. The
web deck contacts no voting service; do not reintroduce one from here.

## HARD RULE — The research repo is read-only from here

The subject of the talk is
`../cross-constituency-aggregation-community-notes` (Cross-Constituency
Aggregation for Community Notes, Emrecan Ulu & Jingyao Shi, Uni Konstanz).
Read from it freely — `paper/main.tex`, `README.md`, `REPRODUCING.md`,
`tests/RESULTS.md`, `figures/script_figures/`, `docs/presentations/` — but
never write, edit, or commit into it from this workspace. If a slide or
argument needs a number or figure that isn't already in this workspace,
say so and ask before pulling more out of that repo. Do not `git commit` or
`git push` there under any circumstances. Talk drafts and slide assets stay
in this directory; moving a finished deck into the research repo's own
`docs/presentations/DD-MM-YYYY-<label>/` convention is the user's call, not
an automatic step.

## HARD RULE — The web deck lives in the Portfolio repo

This repository is the editorial source for the talk, script, and PowerPoint.
The browser presentation is a separate application in
`../Portfolio/experiments/who-speaks-for-the-crowd`; its committed deployment
output is `../Portfolio/who-speaks-for-the-crowd`, and the live URL is
`https://emrecanulu.com/who-speaks-for-the-crowd/`. It is a frozen replay with
the recorded vote embedded.

Read those locations when alignment needs to be checked, but do not edit,
build, commit, or push the Portfolio repository unless the user explicitly
requests that action in the current turn. Slide edits here do not
automatically propagate to the web deck. When synchronization is requested,
copy only approved slide assets and keep the Portfolio source and generated
output in sync.

## HARD RULE — Locked facts

Numbers are quoted, not rounded or estimated. These are pinned by the
paper and by `tests/RESULTS.md` (68/68 passing) in the research repo:

- 44,722 posts in the representative-picked note universe
- X displays 6,832 of them today (15%)
- CCA qualifies 20,405 notes (46%)
- 13,655 of those are hidden by X but qualify under CCA — the rescue pool
- 8,558 of the rescue pool hold up under independent LLM review (62.7%)
- Dense analysis slice: 100,000 notes / 200,000 raters, 44,722 tweets
- Clustering settles on k = 3; after outlier reassignment: 107,734 vs.
  92,266 raters (Method B, canonical)
- Selection rule: cross-constituency score C_i > 0.5 (geometric mean of
  per-camp approval, with a ≥3-rater coverage floor per camp)
- LLM validation threshold: Gemma rescue-worthiness score ≥ 50
- 68 tests, `python run_tests.py`, no data downloads needed

If a talk draft needs a number not on this list, cite where it comes from
(`paper/main.tex`, `data/processed/selection_log.parquet`,
`tests/RESULTS.md`) before using it on stage.

## HARD RULE — Claims must stay honest on stage

A slam stage rewards overstatement; do not give in to it.

- Never say the 8,558 rescued notes are "verified" or "true." Say an
  independent language model checked them for sourcing and quality and
  they held up. Gemma sees only the note's own text — never the source
  URL's contents, never whether the cited source actually supports the
  claim.
- Never say X "censored" or "hid" these notes on purpose. Say X did not
  display them / they stayed in "Needs More Ratings." The paper argues
  the *aggregation rule* produces this outcome, not platform intent.
  Attributing motive to X is a claim the paper does not make.
- Never say CCA finds "the right answer." Say a different aggregation
  rule produces a different outcome — the Yarmouk case (lower raw
  approval, higher cross-constituency score, and the better note) is the
  cleanest demonstration of this, not of CCA being "correct."
  Non-compensation just means one hostile camp can veto.
- Never label the two behavioral camps "left" and "right" or any other
  ideological name. They are recovered from voting behavior via spectral
  clustering, not assigned an identity — the paper is explicit that this
  does not prove politics on the platform is binary.

## HARD RULE — Talk format constraints

- Roughly 10 minutes spoken ≈ 1,300–1,500 words. Check any full draft
  against this before calling it timed.
- The topic must stay recognizably data-science-related throughout.
- Props, games, comedy, and slides are all allowed and encouraged — this
  is judged as a performance, not a paper reading.
- Judging criteria: scientific quality, novelty, how engaging the talk
  is. Weigh any structural choice (what to cut, what to dramatize)
  against these three, not against paper-completeness.

## HARD RULE — Writing style

Write talk scripts in clear, spoken-register English, B2–C1, American
spelling. Sentences should sound natural read aloud, not like manuscript
prose. Carry over the research repo's anti-formulaic discipline:

- Do not open consecutive sentences or beats with the same frame
  ("This means… This shows… This is why…").
- Do not use signal-only transitions that add no content ("This directly
  connects to…").
- One claim per sentence where possible; cut restatements.
- Vary sentence length — a slam talk needs short punches next to setup
  lines, not uniform academic cadence.

## File conventions

- `research/` — pulled-out summaries, quotes, and figures staged from the
  CCA repo for reuse in the talk (never the reverse).
- `results/` and `docs/vote-record.md` — the aggregate live-vote record.
- `script/` — talk script drafts and revisions.
- `slides/` — slide drafts and supporting assets.
- `assets/` — images, exported figures, props reference material.

`research/` does not exist yet; create it the first time a real file goes into
it, not preemptively.

Versioned drafts use `YYYY-MM-DD-<slug>.md`. All filenames, comments, and
documentation in this directory are in English, regardless of the
conversation language used to produce them.

## Side effects

Do not commit, push, open a PR, send mail, or touch any external service
from this directory without the user explicitly asking for that specific
action in that moment. Plugin/skill routing is defined in `PLUGINS.md` —
follow it without re-announcing it here.
