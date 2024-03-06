---
tags:
  - Note
  - Incomplete
---
202402131402

Tags : [[Expander Graphs and Applications]]
# Dinur's Theorem
---
## PCP Theorem
---
If $L\in NP$, there is a way to write the proof which can be *effectively verified* using $O(\log n)$ random bits and $O(1)$ queries.
$$
NP=PCP(O(\log n),O(1)).
$$
So the proof will be polynomial length, $poly(n)=n^{k}$. To query one bit in the entire proof randomly, we need $r=\log(n^{k})=O(\log n)$.

**Completeness:** $x \in L\implies\exists$ a proof s.t. $V$ accepts with $p=1$.
**Soundness:** $x\not\in L\implies \forall P$ $V$ rejects with high probability $\geq \frac{1}{3}$.

> [!success] Dinur's Theorem $\implies$ PCP Theorem
> $3COLOUR\xrightarrow{polytime}Gap-3COLOUR_{1,s}$
> $G\to G'$
> Proof: Give the $OPT$ colouring, $\psi:V(G')\to \{ 1,2,3 \}$ as the proof. If the graph is indeed 3 colourable, the optimal colouring will show that, which gives completeness. Randomly pick an edge $(u,v)\in G'$ and check if $\psi(u)\neq \psi(v)$. This will give the correct thing (??) with high probability.

## Dinur's Theorem
---
**3-Colourability of Graphs**

$\sigma:V\to \{ 1,2,3 \}=[3]$ s.t. all edges are satisfied.
Constraint $C_{e}\subseteq[3]\times[3], C_{e}=\{ (i,j)\ |\ i\neq j \}$

$\mathcal{C}=\{G=(V,E),\Sigma,C_{e}\subseteq\Sigma \times\Sigma\}$

Define the *gap* to be the fraction of edges (edge constraints) that are not satisfied. So it is zero for a 3-colourable graph and at least $\frac{1}{|E|}$ for the others.

$\mathcal{C}_{c,s}$ is a promise that, if the graph is a
- "YES" instance, then $\geq c$ fraction of the constraints are satisfied
- "NO" instance, then at most $\leq s$ fraction of the constraints are satisfied.

**Theorem:** We know that $3COLOUR_{1,1- \frac{1}{|E|}}$ is $NP-$hard. There exists a constant $s_{0}$ s.t. $3COLOUR_{1,s_{0}}$ is $NP-$hard.

1. Regularise the graph.
2. Expanderise
3. Gap amplification
4. Alphabet reduction

### Regularise
---
We replace each vertex $v\in V$ by a cloud of $deg(v)$ many vertices and put an expander $(|V_{u}|=deg(u),d_{0},\lambda_{0})$ coming from this family with degree $d_{0}$ and second eigenvalue $\lambda_{0}$, but of varying vertex set size.

Call this new graph $G'=(V',E')$.
$deg(G')=d_{0}+1$
$|V'|=\sum\limits_{u\in V}|cloud(u)|=\sum\limits_{u\in V}2|E|$
$|E'|=|E|(1+d_{0})$.

---
Now we will analyse the difference in gaps.
We try to see what new fraction is infeasible.
.
.
.

### Expanderise
---
We overwrite notation. We start with the graph $(G,d)$, which has a gap $gap$, which is not too far from the original gap, as seen in the analysis above.

Now, we take an expander graph $H=(n,d_{0},\lambda_{0})$, (not normalised, $\lambda_{0}<d_{0}$), and just superimpose it on $G$. To the new edges, we add no constraints.
$A_{G\boxplus H}=A_{G}+A_{H}$ (It's a multigraph so all is good.)
First eigenvalue $=d+d_{0}$ (??)

Take a vector $v$ perpendicular to the all 1 vector, $\mathbb{1}$.
$$
\begin{align}
\| A_{G\boxplus H}v \|&\leq \| A_{G}v \|+\| A_{H}v \| \\
&<d\| v \|+\lambda_{0}\| v \| \\
&<(d+d_{0})\| v \|. 
\end{align}
$$

What happens to the gap?
None of the new edges add any constraints, so they are vacuously satisfied.
$|E'|=|E|\left( 1+\frac{d_{0}}{d} \right)$
$\sigma'$ is the best assignment for $G\boxplus H$, $F=F'$.
$gap'=gap\left( 1+\frac{d_{0}}{d} \right)$
So, $gap'=\frac{gap}{O(1)}$.

### Gap amplification
---
#### A wrong argument
---
Fix a parameter $t$.
From $G$, construct $G'$ as: $V(G)=V(G')$,
$(a,b)\in E(G')\iff \exists \text{ a path of length }t\text{ between }a\text{ and }b\in G$.
Instead of assigning one of 3 colours to each vertex, now we assign a $d^{t+1}$ dimensional vector. $\sigma':V\to\Sigma'=\Sigma^{d^{t+1}}$.
$deg(G')=d^{t}$
The assignment function can be thought of as: for each vertex $v$, look at all its neighbours within a distance of $t$, there will be $1+d+\dots+d^{t}=d^{t+1}$ many such, and each of them have an opinion of $v$.
The constraint for $(a,b)\in E(G')$ is satisfied iff for all $u-v$ along the $a\sim b$ path, $((\sigma'(u))_{u},(\sigma'(v))_{b})$ is something aaaaaaaaaaa
.
.
.
#### Another wrongish argument
---
Dinur's proof (original) is difficult, so we look at Jaikumar Radhakrishnan's simplified proof.
He studies *clocked random walks*. $(t\geq 1)$

**ASRW:** After stop random walk:
1. Sample $u\in V$.
2. Take a random step $u\to v$ in $G$.
3. STOP at $v$ with probability $\frac{1}{t}$.
4. Otherwise go to step 2.

**BSRW:** Before stop random walk:
From any vertex $u$,
1. STOP at $u$ with probability $\frac{1}{t}.$
2. Pick $u\to v$ uniformly at random otherwise.
3. Go back to step 1.

**Obs.:** ASRW is of a finite length.
$$
\begin{align}
\sum\limits_{n=1}^{\infty}Pr[\text{ASRW is of length }n]&=1 \\
&=\frac{1}{t}+\left( 1-\frac{1}{t}\right) \frac{1}{t}+\left( 1-\frac{1}{t} \right)^{2} \frac{1}{t}+\dots \\
&=\frac{1}{t} \frac{1}{1-\left( 1-\frac{1}{t} \right)} \\
&=1.
\end{align}
$$

**Intuition:**
Here, $a\sim b$ is an ASRW. $u-v$ is an edge along the path.
We say $u-v$ is unsatisfied if aaaaaaaaaa fml

---
**Lemma:** Fix an edge $(u\to v)$ (we are saying that we want to pick $u$ before $v$), and any integer $k\geq 1$. Consider an ASRW conditioned on traversing the edge $u\to v$ exactly $k$ times. Then the following are true:
1. The distribution of $a$ is like a random walk from $u$.
2. The distribution of $b$ is like a random walk from $v$.
3. $a,b$ are independent.

*Proof:*
Consider the following:
$Pr[b=w\ |\ y\geq k]$
This is like once we traversed the edge $u\to v$ $k$ times, we don't care about anything anymore. Now we are at $v$, and we just do a BSRW to reach $w$, and the above quantity does not depend on $k$.

Now to what we wanted:
$$
\begin{align}
Pr[b=w\ |\ y\geq k]&=\frac{Pr[b=w\land y=k]+Pr[b=w\land y\geq k+1]}{Pr[y=k]+Pr[y\geq k+1]} \\
&=\frac{Pr[b=w\ |\ y=k]Pr[y=k]+Pr[b=w\ |\ y\geq k+1]Pr[y\geq k+1]}{Pr[y=k]+Pr[y\geq k+1]} \\
&=\frac{Pr[b=w\ |\ y=k]+Pr[b=w\ |\ y\geq k+1]\left( \frac{Pr[y\geq k+1]}{Pr[y=k]} \right)}{1+\frac{Pr[y\geq k+1]}{Pr[y=k]}} \\
Pr[b=w\ |\ y\geq k]\left(1+ \frac{Pr[y\geq k+1]}{Pr[y=k]}\right)&=Pr[b=w\ |\ y=k]+Pr[b=w\ |\ y\geq k+1]\left( \frac{Pr[y\geq k+1]}{Pr[y=k]} \right) \\
&=Pr[b=w\ |\ y=k]+Pr[b=w\ |\ y\geq k]\left( \frac{Pr[y\geq k+1]}{Pr[y=k]} \right) \\
Pr[b=w\ |\ y\geq k]&=Pr[b=w\ |\ y=k].
\end{align}
$$
So we have Proof for 2.
We can reverse the whole thing and prove 1. similarly.
1 and 2 together give 3.

---
.
.
.
.
> [!idea] First prove a lower bound on $\mathbb{E}[N]$.

For any $(u,v)\in F$
$$
\begin{align}
\mathbb{E}[\# \text{ of faulty }u\to v\text{ steps}]&=\sum\limits_{k\geq 1}\mathbb{E}[\#\text{ of faulty }u\to v\text{ steps}\mid k\ u\to v\text{ steps}]\\
&= \sum k(Pr[u\to v\text{ step is faulty}\mid k\ u\to v\text{ steps}]).Pr[k\ u\to v\text{ steps}]  &&\text{once a faulty }u\to v\text{ step, always a faulty }u\to v\text{ step} \\
&=\sum k.p.Pr[k\ u\to v\text{ steps}]  \\
&=p\sum k.Pr[k\ u\to v\text{ steps}]  \\
&=p.\mathbb{E}[u\to v\text{ steps}]
\end{align}
$$
Now, the expected number of $u\to v$ steps is equal to the expected length of an ASRW times the expected number of $u\to v$ steps in one ASRW. (??)

$$
\begin{align}
\frac{\mathbb{E}[u\to v\text{ steps}]}{\mathbb{E}[u\to v\text{ steps in one ASRW}]}&=\mathbb{E}[\text{length of an ASRW}] \\
&=\sum\limits_{k\geq 1} \frac{1}{t}k\left( 1-\frac{1}{t} \right)^{k} \\
&=\frac{1}{t} \frac{1}{\left[ 1-\left( 1-\frac{1}{t} \right) \right]^{2}} \\
&=t.
\end{align}
$$


.
.
.

**Theorem:** Let $G=(n,d,\lambda)$ be an expander graph and $F\subset E$ be a set of edges. Then the probability that a random walk starting from one edge in $F$ traverses an edge from $F$ again at $t^{th}$ step $\leq\left( \frac{|F|}{|E|}+\lambda^{t+1} \right)$.

*Proof:*
Let $x$ be the initial distribution on the vertex set.
After $(t-1)^{th}$ step of the walk, the distribution we get is $A^{t-1}x$, where $A$ is the normalised adjacency matrix.
$(A^{t-1}x)_{w}=$ probability that we reach vertex $w$.

Let $k_{w}$ be the number of edges incident on $w$, that are in $F$.
$y_{w}= \frac{k_{w}}{d}$.
$x=(x_{1},\dots,x_{w},\dots,x_{n})^{T}$
$x_{w}=\frac{k_{w}}{2|F|}$
So $y_{w}=\frac{2|F|}{d}x_{w}$.
$$
\begin{align*}
\text{Probability that $t^{th}$ step lands in } F&=\sum\limits_{w\in V}(A^{t-1}x)_{w}y_{w}\\
&=\frac{2|F|}{d}\sum\limits_{w}(A^{t-1}x)_{w}x_{w}\\
&=\frac{2|F|}{d}\langle A^{t-1}x,x \rangle \\
&\leq \frac{2|F|}{nd}+\lambda^{t-1}&&(*)\\
&=\frac{2|F|}{|E|}+\lambda^{t-1}.
\end{align*}
$$
$(*):$
$$
\begin{align*}
\langle A^{t-1}(x_{\parallel}+x_{\perp}),(x_{\parallel}+x_{\perp}) \rangle &=\langle A^{t-1}x_{\parallel},x_{\parallel} \rangle+\langle A^{t-1}x_{\perp},x_{\perp} \rangle +0+0\\
&=\langle x_{\parallel},x_{\parallel} \rangle   +\langle A^{t-1}x_{\perp},x_{\perp} \rangle \\
&\leq \| x_{\parallel} \|^{2} +\lambda^{t-1}\| x_{\perp} \| ^{2}\\
&\leq \frac{1}{n}+\lambda^{t-1}\| x \| ^{2}\\
&\leq \frac{1}{n}+\lambda^{t-1}\max\limits_{w}|x_{w}|\\
&\leq \frac{1}{n}+\lambda^{t-1} \frac{d}{2|F|}.
\end{align*}
$$


### Alphabet reduction
---
[[Building of Assignment Tester]] is the algorithm we will use a lot.









---
# References
[[Probabilistically Checkable Proof]]