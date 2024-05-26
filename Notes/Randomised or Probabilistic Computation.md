---
tags:
  - Note
  - Incomplete
---
202403201003

Tags : [[Complexity Theory]]
# Randomised or Probabilistic Computation
---
> [!hint] We want easy to design, efficient algorithms, that work well in practice.

We assume that we have a Decision Algorithm $A$, which takes an input $x$, and has access to an *Ideal Random Source:* a supply of independent unbiased coinflips.
So the behaviour of the algorithm becomes randomised. $A(x)$ is a random variable taking value $\{ 0,1 \}$. The runtime of $A$ is also a random variable.

The Ideal Random Source itself is an interesting object under study. Trying to get close to ideal, many random bits from a few truly random bits, or from some dependent, but high-entropy bits, also using a few truly random bits, and whether or not a truly random source exists are problems that are keeping some of the community awake at night.

---
A randomised $TM$ is just a machine which uses $p(|x|)$ many random bits, and does computations in polytime.

$BPP:$ *bounded-error probabilistic polynomial time*

$L\in BPP$ if there is a randomised polytime $TM$ $M$ running in time $p(n)$ s.t.
$x \in L\implies Prob[M(x,w)\text{ accepts},w\in_{R}\{ 0,1 \}^{p(|x|)}]\geq \frac{2}{3}$,
$x \notin L\implies Prob[M(x,w)\text{ rejects},w\in_{R}\{ 0,1 \}^{p(|x|)}]\geq \frac{2}{3}$.
Error probability of $M$ is $\leq \frac{1}{3}$.

Easy to see: $P\subseteq BPP$.

> [!question] Why is $\frac{2}{3}$ good? Isn't it quite low of an assurance?
> In fact, $\frac{1}{2}+ \frac{1}{poly(n)}$ also suffices! We can amplify the success probability to $1- \frac{1}{2^{q(n)}}$ for any polynomial $q(n)$.

$x \in L$ and we run $M$ on $x$ $m$ times: $ans_{1},ans_{2},\dots,ans_{m}\in\{ 0,1 \}$.
$ans_{i}$ is a $0-1$ random variable.
$\mathbb{E}[ans_{i}]\geq \frac{2}{3}.1 + \frac{1}{3}.0$
$\mathbb{E}\left[ \sum\limits_{i=1}^{n}ans_{i} \right]\geq \frac{2}{3}m$

**Claim:** If $M$ is run $m$ independent times then the majority of $\{ ans_{i} \}_{i=1}^{m}$ is correct with probability $\geq 1- \frac{1}{2^{2m}}$.(check exponent of 2 ??)
*Proof* can be done for general $\epsilon< \frac{1}{2}$, by bounding the probability that a bad sequence happens.

---
$RP:$ Randomised polytime
$L\in RP$ if there is a randomised polytime $TM$ $M$ and a polytime $p(n)$ s.t.
$x \in L\implies Prob[M(x,w)\text{ accepts}]\geq \frac{1}{2}$,
$x \notin L\implies Prob[M(x,w)\text{ accepts}]=0$.
$M$ has one sided error.
$RP\subseteq NP$.

> [!question] Why is $\frac{1}{2}$ good? Isn't it quite low of an assurance?
> In fact, $\frac{1}{poly(n)}$ also suffices! We can amplify the success probability to $1-\frac{1}{2^{q(n)}}$ for any polynomial $q(n)$.


**Claim:** We can get an $RP$ machine $M'$ for $L$ with error bounded by $(1-\epsilon)^{m}$ by running $M$ $m$ times and accepting if any one outcome is accepted.
$x \in L\implies Prob[M'(x,w_{1},\dots,w_{m})\text{ accepts}]\geq 1-(1-\epsilon)^{m}$,
$x \notin L\implies Prob[M'(x,w_{1},\dots,w_{m})\text{ accepts}]=0$.

We can take $\epsilon= \frac{1}{p(n)}$, and do this $p(n)q(n)$ many times, so the error probability is $\left( 1- \frac{1}{p(n)} \right)^{p(n)q(n)}\approx e^{ -q(n) }<2^{-q(n)}$.

---
$RP\cap coRP=ZPP$, Zero error
Given $L$, and $x$, if we want to check if $x$ is in $L$, we just run both $RP$ and $coRP$ machines, and if any one of them accepts, we can trust that. If not, we run them again. So there is a non zero yet diminishing probability that the machine goes on forever. But the expected runtime is polynomial.

**Theorem:** $L\in ZPP$ is equivalent to $L$ having a randomised algorithm with error probability $0$ and polynomial expected runtime.
*Proof:*
> [!example] *Markov's Inequality:* Let $X$ be a discrete non negative random variable taking values in $D$ with $\mathbb{E}[X]=\mu$.
> $$
> Prob[X>k\mu]\leq \frac{1}{k}.
> $$

Using this inequality for $k=2$, we can finish the proof.

## Examples
---
1. [[Bipartite Graph Perfect Matching]]
2. [[Miller-Rabin Algorithm for Primality]]










---
# References
