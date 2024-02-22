---
tags:
  - Note
  - Incomplete
---
202401111401

Tags : [[Expander Graphs and Applications]]
# INW generator for Space Bounded Computation
---

> [!hint] In his work towards the $RL=L$ conjecture, Nisan gave the following function that works irrespective of the algorithm and the problem, and shows that $RL\subset L^{2}$.

> [!note] Note that that's not the best known bound known. The best known is $RL\leq L^{3/2}$.

Given a randomised algorithm $\mathcal{A}$ such that $\Pr[\mathcal{A}(x,r)=1]$, on an input $x$ using a uniformly random input $r\in\{ 0,1 \}^{l}$, Nisan gave a global function $g_{\text{Nisan}}:\{ 0,1 \}^{l'}\to \{ 0,1 \}^{l}$, $l' \approx \log l$, such that $|\Pr[\mathcal{A}(x,r)=1]-\Pr[\mathcal{A}(x,g(r'))=1]|\leq\epsilon$, where $r'\in\{ 0,1 \}^{l'}$.

> [!hint] The following construction is due to [INW'95].
> $\mathcal{A}:$ space bound algorithm using space $S$
> Because space is bounded, there are only $2^{S}$ many configurations. We divide it into $\frac{2^{S}}{R}$ groups of size $R$ each. We think of each group as an independent algorithm that uses $R$ random bits. We use expander graphs, to get the work done in $R+\log D$ bits instead of $2R$ bits, by pairing these groups up. Now we have half as many groups that use $R+\log D$ bits each, we can use a larger expander in the same family (same degree) to reduce this to $R+2\log D$ bits and so on recursively, to effectively only use $R+O(S\log D)$ random bits.

> [!warning] deets
> So $r$ is an $l-$bit random string, where $l=2^{S}$. We get $l'=R+O(S\log D)$. Since $S$ is logarithmic, this is fine.
> We want the error to be small. $error\leq 2^{S}\epsilon\leq \frac{1}{2^{2S}}$ or some such.

## Analysis
---
We want to bound the error that our algorithm introduces.
If we write it out, it is just comparing the probability of choosing two vertices independently, uniformly at random from sets $S_{b'},T_{b'}$, which is the original algorithm, and probability of choosing an edge that goes across $S_{b'}$ and $T_{b'}$, where we look at the first two chunks $\mathcal{A}_{1},\mathcal{A}_{2}$. Assume $\mathcal{A}_{1}$ takes in $x$, and gives out some $b'$, $\mathcal{A}_{2}$ takes in $b'$ and gives out $b$. Fix $b$. Define $S_{b'}:=\{ r_{1}|\mathcal{A}_{1}(x,r_{1})=b' \}$, and $T_{b'}:=\{ r_{2}|\mathcal{A}_{2}(b',r_{2})=b \}$.

We observe that the difference in probabilities is just $\sum\limits_{b' \in\{ 0,1 \}^{S}} \left( \frac{|S_{b'}|}{|V|} \frac{|T_{b'}|}{|V|}- \frac{E(S_{b'},T_{b'})}{|E|} \right)$ which we can bound by the Expander Mixing Lemma. We get that the error is at most $2^{S}\lambda$.




---
# References
[[Expander Graphs and Applications]]