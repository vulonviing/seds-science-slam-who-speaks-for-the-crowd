# Science Slam Deck Draft — Who Speaks for the Crowd?

Slide specification for a 10-minute talk. The July 2026 PowerPoint is the
visual source. Each final slide should duplicate the listed source slide and
edit inherited elements rather than rebuild the design.

## Deck contract

- Format: 16:9 PowerPoint fallback plus a 15-slide web deck with approximately
  27 click states after the three live audience polls are included.
- Visual system: white background, black headlines, blue/coral constituencies,
  teal positive results, sparse layouts, and existing stick-figure language.
- Speaker notes: add a `[Sources]` block to every slide containing an external
  claim or asset.
- Do not put timings, talk-track instructions, or internal labels on slides.
- The two clusters are always “behavioral constituencies” or “camps,” never
  ideological groups.

## Slide map

### 1. WHO SPEAKS FOR THE CROWD?

- Source slide: July deck 1.
- Visible copy:
  - `WHO SPEAKS FOR THE CROWD?`
  - `Emrecan Ulu / Jingyao Shi`
  - `SEDS Data Science Slam · 1 October 2026`
- Visual: retain the note card receiving blue and coral lines.
- Narrative job: holding slide while the presenter is introduced.

### 2. Which note should be shown? — Wikimedia

- Source slide: July deck 4.
- First state: show only the Elon Musk/Wikimedia post.
- Second state: reveal three equal A/B/C candidate-note cards. Keep the current
  sourced note and mark the two temporary alternatives as illustrative.
- Third state: reveal the fixed QR code, open voting, and show live percentage
  bars plus the total vote count.
- Fourth state: Next closes the poll, freezes the bars, and highlights the
  winner or tied winners without labeling an answer correct.
- Narrative job: make the room experience one aggregation decision directly.

### 3. Which note should be shown? — Shelter post

- Source slide: July deck 5.
- Use the same four-state interaction as slide 2; the phone page advances
  automatically, so the audience does not scan again.
- Keep the existing unsupported personal attack as one candidate. The two
  illustrative alternatives focus on verifiability and relevance without
  claiming the original post is false.
- Narrative job: show that a note can be unhelpful because it targets the
  author rather than the claim.

### 4. Which note should be shown? — Punchline

- Source slide: July deck 4.
- First show the Khamenei post without its note, then reveal three candidates.
  Keep `assets/khamenei-community-note.png` as the source composition.
- Open and close the final poll with the same live bars. Keep the distribution
  visible but do not present a correct answer.
- Narrative job: first planned laugh and a genuinely ambiguous vote whose
  disagreement is visible rather than estimated from raised hands.

### 5. One note. One decision.

- Source slide: July deck 5.
- Visible flow: `Post → Candidate note → Helpful? → Show / Needs More Ratings`.
- Visible copy:
  - `One note. One decision.`
  - `People write context.`
  - `Other contributors rate helpfulness.`
  - `The ratings become one visibility decision.`
- Narrative job: define Community Notes for an unfamiliar audience.

### 6. 95.1% said helpful. X still did not display it.

- Source slide: July deck 39.
- Replace the note card with the raw-chicken note:
  `Raw chicken does not need to be washed before cooking. Washing poultry can
  increase bacterial contamination in the kitchen. [CDC; USDA]`
- First state: note card only.
- Second state: reveal `95.1% helpful`.
- Third state: reveal `NEEDS MORE RATINGS` in coral.
- Narrative job: create the paradox that drives the talk.

### 7. X already looks for unlikely agreement.

- Source slide: July deck 12.
- Retain the `AMIGO` and `ENEMIES SHAKE HANDS` comparison.
- Keep only two captions:
  - `Predictable support`
  - `Unexpected agreement`
- Bottom line: `The system reads the rater—not only the rating.`
- Narrative job: represent X’s current bridging idea fairly.

### 8. The handshake is right. The electorate is not.

- Source slide: July deck 20.
- Left: retain the handshake visual.
- Right, progressive reveal:
  - `One learned map`
  - `One fitted visibility score`
  - `Representation stays implicit`
- Bottom line: `CCA makes constituencies explicit.`
- Narrative job: state the gap without attributing intent to X.

### 9. We recover constituencies from voting behavior.

- Source slide: July deck 23.
- Visual flow: `Ratings → Co-rating graph → Spectral clustering → Camps`.
- Metrics:
  - `100,000 notes`
  - `200,000 raters`
  - `k = 3`
  - `After outlier reassignment: 107,734 / 92,266`
- Footer callout: `Behavior—not demographics or declared ideology.`
- Narrative job: provide the single clustering visual and establish scientific
  depth.

### 10. Each camp gets its own approval rate.

- Source slide: July deck 27.
- Visual: one note in the center, one approval rate from each camp.
- Visible rules:
  - `≥3 raters from every camp`
  - `Camp A approval: pA`
  - `Camp B approval: pB`
- Narrative job: move from recovered groups to an aggregation rule.

### 11. Enthusiasm cannot buy consent.

- Source slide: July deck 28.
- Main equation: `Cᵢ = √(pA × pB)`.
- Decision rule: `Cᵢ > 0.5`.
- Progressive examples:
  - `70% × 68% → 0.69 → PASS`
  - `90% × 20% → 0.42 → FAIL`
- Small label: `Soft veto`.
- Narrative job: explain non-compensation with the talk’s only equation.

### 12. A different rule changes who is heard.

- Source slide: July deck 33.
- Progressive result tree:
  - `44,722 posts`
  - `X displays 6,832 · 15%`
  - `CCA qualifies 20,405 · 46%`
  - `13,655 not displayed by X but CCA-qualified`
- Use `RESCUE POOL` only as a project label, not a truth verdict.
- Narrative job: deliver the headline empirical result.

### 13. 8,558 held up under independent text review.

- Source slide: July deck 38.
- Visual flow: `13,655 candidates → Gemma review → 8,558 · 62.7%`.
- Visible caveat: `Note text + visible source pointer only`.
- Footer: `No URL opening. No source-content verification.`
- Narrative job: demonstrate validation while keeping the limitation prominent.

### 14. High approval. Wrong battle.

- Source slide: July deck 40.
- First state: platform-shown note only.
  - `92.2% overall approval`
  - `Describes Mu’tah`
  - `PLATFORM SHOWS`
- Second state: reveal the CCA alternative.
  - `91.2% overall approval`
  - `Addresses Yarmouk`
  - `Higher cross-constituency score`
  - `CCA PICKS`
- Bottom line: `Lower popularity. Better-balanced support.`
- Narrative job: show that the two rules can rank real notes differently.

### 15. The crowd is not one number.

- Source slide: July deck 1.
- Replace the title while retaining the blue/coral crowd and note-card visual.
- Visible copy:
  - `THE CROWD IS NOT ONE NUMBER.`
  - `Every aggregation rule decides who gets heard.`
- Narrative job: resolve the opening vote and end on the research contribution,
  not on a generic thank-you slide.

## Source blocks

Use these blocks as the basis for PowerPoint speaker notes.

- Slides 2–3, 7–15:
  `[Sources] Ulu, E. & Shi, J. (2026), Cross-Constituency Aggregation for
  Community Notes; paper/main.tex; tests/RESULTS.md; July 2026 project deck.`
- Slide 4:
  `[Sources] User-provided screenshot, received 10 September 2026; repost
  record: https://www.reddit.com/r/GetNoted/comments/1rj32kq/allah_didnt_protect_him/`
- Slide 5:
  `[Sources] https://help.x.com/en/using-x/community-notes;
  https://communitynotes.x.com/guide/en/contributing/diversity-of-perspectives`
- Slide 6:
  `[Sources] Ulu & Shi (2026), paper/main.tex, raw-chicken safety case; CDC and
  USDA links reproduced in the paper.`

## Delivery safeguards

- If the room does not vote, wait three seconds and continue with:
  `Uncertainty is data too.`
- Do not expand the Khamenei joke verbally or repeat the note text aloud.
- Do not call the rescue pool censored, verified, true, or the right answer.
- Keep the prepared delivery at 9:20–9:40 to leave room for hands and laughter.
