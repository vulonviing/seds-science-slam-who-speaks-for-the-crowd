# Science Slam — SEDS Conference 2026

Script, slides, and live-vote record for a 10-minute talk at the SEDS Conference
2026 Data Science Slam: **Who Speaks for the Crowd?** The research itself lives
in a separate repository; this one is where the talk was built.

## Presentation outputs

- [Web deck](https://emrecanulu.com/who-speaks-for-the-crowd/): a frozen replay of
  the talk; the QR code opens the closed results page
- [Web deck source](https://github.com/vulonviing/portfolio/tree/main/experiments/who-speaks-for-the-crowd)
- PowerPoint: `slides/2026-09-10-science-slam-v1.pptx`
- Talk script: `script/2026-09-10-slam-script-v1.md`
- Live vote record: `docs/vote-record.md`

This repository is the editorial source for the talk, script, and PowerPoint.
The web deck is maintained and deployed from
[`vulonviing/portfolio`](https://github.com/vulonviing/portfolio); updating one
does not update the other. The deck contacts no voting service, and nothing
about servers, credentials, or raw vote data is kept here.

## The interactive part

The talk was interactive: the audience voted live on which candidate note
should be shown under a post. The result is in `docs/vote-record.md`.

## The event

**1 October 2026, 09:30–17:00**, Wolkensteinsaal im Kulturzentrum,
Katzgasse 3, 78462 Konstanz.

The Data Science Slam is the last program block, **14:30–17:00**, moderated
by Prof. Dr. David García. Full day includes a keynote by Kate Nazarova
(Lead Data Science & AI, BASF), alumni talks, the launch of the SEDS
Mentoring Program, and an AK SEDS social event in the evening. Participation
is free; food and drinks are provided.

## Slam rules

- Topic must be related to data science.
- Talk length: approximately 10 minutes.
- Anything goes on stage — props, games, comedy, slides.
- Winner is judged on scientific quality, novelty, and how engaging the
  talk is; there's a prize.

## The talk's subject

**Cross-Constituency Aggregation for Community Notes** (Emrecan Ulu &
Jingyao Shi, University of Konstanz) — a new rule for deciding which
fact-checks X's Community Notes should show.

The pitch: on X, a note only becomes visible if the crowd's ratings clear
one pooled score. Count raw votes and the larger side always wins, so a
note can be buried by the group it makes uncomfortable rather than by
anything wrong with it. CCA settles this differently — it sorts raters into
behaviorally distinct camps first, then requires each camp to separately
approve a note before it can show. One camp's enthusiasm can no longer
outvote another camp's rejection.

Headline numbers (see `AGENTS.md` for the full locked list and how to cite
them honestly on stage):

| | |
|---|---|
| Posts analyzed | 44,722 |
| Shown by X today | 6,832 (15%) |
| Qualify under CCA | 20,405 (46%) |
| Hidden but CCA-qualified (rescue pool) | 13,655 |
| Hold up under independent LLM review | 8,558 (62.7%) |

The single best 30-second demo is the **Yarmouk case**: the note X already
displays has lower raw disapproval but describes the wrong historical
battle; the CCA alternative has slightly *lower* raw approval (91.2% vs.
92.2%) but wins because both camps back it — a direct, concrete picture of
what "non-compensation" means: a popular note can still lose if one camp
rejects it, and a less-popular note can win by earning both camps' trust.

## Source material

All paths are inside the sibling directory
`../cross-constituency-aggregation-community-notes`.

| Want | Path |
|---|---|
| The paper (PDF) | `paper/Ulu_Yao.pdf` |
| The paper (source) | `paper/main.tex` |
| Repo overview | `README.md` |
| Every number's origin | `REPRODUCING.md`, `tests/RESULTS.md` |
| Earlier class talk (25 Jun 2026) | `docs/presentations/25-06-2026-1408-class_presentation/CCA_presentation.pdf` (+ `.key`) |
| Final talk (11 Jul 2026), 42 slides, "WHO SPEAKS FOR THE CROWD?" | `docs/presentations/11-07-2026-community-notes-final/community-notes-final-presentation.pdf` (+ `.pptx`) |
| Paper figures (5, each as `.py` + `.pdf` + `.png`) | `figures/script_figures/` |

The 11 Jul deck already has reusable visual language — a stick-figure
rater/note diagram, a "the model asks who voted" framing, and a
red/blue camp motif — worth mining before designing new slides from
scratch.

## Workspace layout

- `research/` — summaries, quotes, and figures staged out of the CCA repo
  for reuse in the talk.
- `script/` — talk script drafts, `YYYY-MM-DD-<slug>.md`.
- `slides/` — slide drafts and supporting assets.
- `assets/` — exported images, figures, prop reference material.

`script/`, `slides/`, and `assets/` now contain the first complete draft.
Create `research/` only when staged research material is needed.

## Status

The talk was delivered on 1 October 2026. The live audience vote is recorded in
`docs/vote-record.md`. The first 15-slide PowerPoint remains the static
fallback; the web deck replays the talk with the recorded results.
