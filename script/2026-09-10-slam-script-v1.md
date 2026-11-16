# Who Speaks for the Crowd?

10-minute Science Slam script for the SEDS Conference 2026.

## Slide 1 — Who Speaks for the Crowd?

Before I show you any data, I need you to make three moderation decisions.

You are working for X now. The salary is zero, but the responsibility is
enormous. Keep your phone nearby. For each post, you will choose which of three
candidate Community Notes should appear beneath it.

## Slide 2 — Would you show this note?

Here is the first post.

Elon Musk asks why Wikipedia needs money if you can download the encyclopedia
to your phone.

[Reveal candidates A, B, and C.]

Three people could respond with three very different notes. Which one should
everyone see?

[Open voting and reveal the QR code.]

Scan once and choose A, B, or C. Keep the page open; it will follow us through
all three rounds.

[Let the bars move, then close the vote.]

Good. The room has made its first aggregation decision.

## Slide 3 — Would you show this note?

Second case. A user describes repeatedly running to a bomb shelter with their
family.

[Reveal candidates A, B, and C.]

One note questions what can be verified. One attacks the author. One asks
whether that attack addresses the post at all.

Your phone should already have moved to round two. Vote again.

[Let the bars move, then close the vote.]

That distribution is useful information too.

## Slide 4 — Would you show this note?

And sometimes a Community Note becomes the punchline.

[Reveal the Khamenei post. Pause for two or three seconds, then reveal the
three candidates.]

Same job. Which note should appear?

[Open round three, let the bars move, then close the vote.]

Excellent. We already disagree, and now we can see exactly how much.

## Slide 5 — One note. One decision.

Congratulations. You are now the algorithm.

That is Community Notes in one minute. People on X write short pieces of
context under posts. Other contributors rate whether those notes are helpful.
The platform combines those ratings and makes one decision: show the note, or
leave it in “Needs More Ratings.”

The note is not written by an employee in an X fact-checking office. It comes
from another user. The people rating it do not receive a simple answer key,
either. They judge whether the note is clear, relevant, neutral, and supported
well enough to help somebody reading the original post.

X does not simply count thumbs up. Its system looks for support from people who
have tended to disagree in their previous ratings. The goal is sensible: one
side should not be able to force its preferred correction onto everybody else.

But a difficult question is hiding inside that word “combine.” How should
thousands of votes become one decision?

## Slide 6 — 95.1% said helpful. X still did not display it.

Consider this note about raw chicken.

It says you do not need to wash chicken before cooking. Washing it can spread
bacteria around the kitchen. The note points to guidance from the CDC and the
USDA.

This is not exactly the most divisive topic on the internet.

Among the people who rated the note, 95.1% marked it helpful.

X still did not display it.

No conspiracy is required. The aggregation rule produced that outcome. High
overall approval was not enough.

So what was the system looking for?

## Slide 7 — X already looks for unlikely agreement.

Imagine that I always agree with one family of notes. When I approve another
note from that same family, the vote is predictable. The model learns very
little.

Now imagine two raters who usually disagree. If both approve the same note,
that handshake is surprising. X gives this kind of agreement more weight.

That is an important idea. The system reads the rater, not only the rating.

Our criticism is not that X forgot disagreement. The handshake is right. The
question is how the electorate behind that handshake is represented.

## Slide 8 — The handshake is right. The electorate is not.

The current system learns a shared latent map of raters and notes, then turns
that map into one visibility score. Representation remains implicit inside the
model.

That design is elegant, but it makes the meaning of “broad agreement” depend on
the geometry learned from whoever participated most. A very active minority can
help draw the map on which everyone else is later located. The model may still
find a bridge, but the bridge can inherit an uneven picture of the crowd.

We tried a different approach. Instead of asking one fitted score to speak for
the entire crowd, we first recover constituencies from voting behavior. Then we
ask every constituency directly: did your group approve this note?

Notice what we do not ask. We do not ask for anyone’s party, ideology,
location, gender, or profile. The groups come only from patterns in the ratings.
Calling them “left” and “right” would tell us more than the data does.

## Slide 9 — We recover constituencies from voting behavior.

Our dense analysis slice contains 100,000 notes and 200,000 raters.

We connect people who rated many of the same notes in similar ways. This
creates a co-rating graph. Spectral clustering then searches that graph for
stable behavioral groups.

The clustering settles on three groups. One is a tiny outlier group. After
reassigning those outliers by their vote profiles, the canonical partition has
two large camps: 107,734 and 92,266 raters.

Again, these are behavioral constituencies. They are not identities that we
assigned in advance.

## Slide 10 — Each camp gets its own approval rate.

Now each note receives an approval rate from each camp.

Both camps must be present, with at least three raters from each. Then we
combine their approval rates with a geometric mean.

For two camps, the score is the square root of camp A’s approval multiplied by
camp B’s approval. A note qualifies when that score is above 0.5.

The formula has one job: enthusiasm in one camp cannot fully compensate for
rejection in the other.

## Slide 11 — Enthusiasm cannot buy consent.

Suppose camp A gives a note 70% approval and camp B gives it 68%. The geometric
mean is about 0.69. It passes.

Now suppose one camp gives 90%, while the other gives only 20%. The ordinary
average is 55%. A simple majority rule might celebrate.

The geometric mean is about 0.42. It fails.

We call this a soft veto. One hostile camp can stop the note, but neither camp
gets extra power merely because it is larger.

This does not make the formula an oracle. It encodes a choice: cross-group
acceptance matters more than pooled popularity.

## Slide 12 — A different rule changes who is heard.

Then we applied that rule to real Community Notes data.

The representative-picked universe covers 44,722 posts. X displays 6,832 notes
on those posts—15%.

For a fair comparison, we choose one representative note for every post before
comparing the two rules. We are not helping CCA by giving it more attempts per
post. Both systems face the same 44,722 visibility decisions.

CCA qualifies 20,405 notes—46%.

The difference includes 13,655 notes that X did not display but that clear the
CCA rule. That is our rescue pool.

I am not saying X deliberately hid them. I am not saying all 13,655 are true.
The honest claim is both simpler and more interesting: change the aggregation
rule, and thousands of visibility decisions change with it.

## Slide 13 — 8,558 held up under an independent text review.

Still, a larger rescue pool is useless if it is full of bad notes. So we asked
an independent language model, Gemma, to review the candidates for sourcing and
visible-text quality.

Of the 13,655 candidates, 8,558 held up. That is 62.7%.

There is an important limit. Gemma saw the note’s text and its visible source
pointer. It did not open the source URL. It could not check whether the linked
article truly supported the claim.

So “held up under review” is the claim. “Verified as true” is not.

## Slide 14 — High approval. Wrong battle.

One pair of notes shows why the aggregation rule matters.

The post discusses the Battle of Yarmouk. The note that X displays has 92.2%
overall approval. It describes the Battle of Mu’tah—the wrong battle.

Another note addresses the actual event in the post: Yarmouk. Its raw approval
is slightly lower: 91.2%. But support is better balanced across the two
behavioral camps, so its cross-constituency score is higher. CCA selects that
alternative.

High approval. Wrong battle.

This example does not prove that CCA always finds the right answer. It shows
something narrower: pooled popularity and cross-constituency acceptance can
rank the same notes differently.

## Slide 15 — The crowd is not one number.

We began with three notes and one room full of opinions.

Some of you approved the sourced correction. Some rejected the personal
attack. I am fairly sure the third note divided the room for reasons no formula
can fully capture.

Community Notes sounds like a question about facts. Underneath, it is also a
question about representation.

Who counts as a constituency? How much agreement is enough? Can a large group
buy its way past a smaller group’s rejection?

An algorithm must answer those questions before it can decide what the crowd
said.

Our proposal is one possible answer: recover constituencies from behavior, ask
each one separately, and make approval cross the divide.

The crowd is not one number.

Every aggregation rule decides who gets heard.

## Source notes

- Slides 2–3: examples and visual treatment from the July 2026 project deck.
- Slide 4: user-provided screenshot; verify the original X post before final
  delivery and record the source URL in the PowerPoint speaker notes.
- Slide 5: X Community Notes documentation on notes, ratings, and diversity of
  perspectives.
- Slide 6: `paper/main.tex`, Table “Examples of hidden CCA rescues.”
- Slides 7–14: `paper/main.tex`, `tests/RESULTS.md`, and the canonical July 2026
  project deck.
- All slide assets require `[Sources]` blocks in PowerPoint speaker notes.
