# Intro
(Aditi)
We have a bunch of problems, but we generally assume that we know the inputs accurately, but that's not always the case.
"What's the truth? Well that's a difficult thing; we are not gonna talk about that here."
When you google something, you'll get a subset of things, and that subset may be biased and distort human perception (which can be discouraging for a little girl who googles 'scientist' and sees a bunch of white males).
Algorithms that differentiate based on race, colour, gender etc

# The problem
In different scenarios, we ask questions. But the important thing is to not forget the context.
## Subset selection
---
$m$ items, weighted non negative (utility)
Pick a subset of size $n$ to maximise utility.

**Assumption:** Utilities correlate to 'quality', known exactly, and that things are additive in some sense... How realistic is that?

# Other similar problems
## Ranking
---
weighted bipartite matching
putting object $i$ in thing $j$ gives utility $U_{ij}$, we want to maximise utility through matching
(how's this related to ranking?)

## Supervised Learning
---



# Inputs may not be accurate
---
What is your level of education on a scale of $1$ to $10$? This question doesn't make sense...
One can add noise to get rid of biases like race etc, (which is what people do for privacy), but that can cause (fair) algorithms to fail.

We want to come up with algorithms that provide guarantees wrt the original data, not the noisy one we received. Because noise and bias (explicit/implicit) is happening, and we would like to undo the noise.
(We are not looking at this from a coding theory perspective.)

# Back to the problem
---
Our model is:
people, some bias (multiplicative, say $\beta$) towards a certain group

**Rooney Rule:** Spend more time (interview) with at least one person from an underrepresentated group.
Someone has showed that this can increase the latent (total) utility.

Generalisation: interview at least $l\geq 1$ people from underrepresented



1. Why can we not just get rid of the names, genders, ages before assessment? Where is the bias being introduced?
2. Can we try to find an approximation for $\beta$ and unmultiply it?
3. Why would the overall order be preserved after bias? If it is, can't we just pick highest few? Is it within a group? Ah okay!






