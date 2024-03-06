---
tags:
  - Note
  - Incomplete
---
202402211402

Tags : [[Combinatorial Optimisation]]
# Primal-Dual Algorithm for general Min-cost Perfect Matching
---
We will show a Primal-Dual algorithm using a combination of [[Primal-Dual Algorithm for Bipartite Min-cost Perfect Matching]] and [[Edmond's algorithm for general Matching]].

## Tutte-Berge formula
---
$|M_{\max}|=\min\limits_{U\subseteq V} \frac{1}{2}(|V|+|U|-o(G\setminus U))$,
where $o(S)$ is the number of odd components in $S$.
A $U$ that achieves the above equality is called a **Tutte-Berge witness**.

## Factor-critical graphs
---
$G$ is *factor-critical* if $G$ has no perfect matching but $\forall v\in V$, $G\setminus \{ v \}$ has a perfect matching.
**Claim:** If $G$ is factor-critical then:
- $G$ has odd $|V|$,
- $G$ is connected,
- $\phi$ is the unique Tutte-Berge witness for $G$. (Prove.)

## Edmonds-Gallai decomposition
---
For $G=(V,E)$, let
$D(G)=\{ v\mid \exists \text{ a matching that leaves }v\text{ unmatched} \}$
$A(G)=\{ v\mid v \text{ has a neighbour in }D(G)\text{ but }v\notin D(G) \}$
$C(G)=V\setminus(D(G)\cup A(G))$

Then the following hold:
1. $A(G)$ is a Tutte-Berge witness,
2. $C(G)$ is the union of all even components of $G\setminus A(G)$,
3. $D(G)$ is the union of all odd components of $G\setminus A(G)$,
4. Each component in $D(G)$ is factor-critical.

> [!done] Lemma 1: For any max matching $M$, according to the labelling during Edmond's algorithm,
> 1. $Even(G,M)=D(G)$
> 2. $Odd(G,M)=A(G)$
> 3. $Unlabelled(G,M)=C(G)$
>  
> *Proof:*
> 1. $v\in Even(G,M)$.
> So, $v$ has an alternating path $P$ from some $x \in X$, ($X$ is the set of unmatched vertices in $M$). We take the path, and alternate the matching along it to get $M\oplus P$, which is also a max matching, and it leaves $v$ unmatched.
> Conversely, if $v\in D(G)$, then there exists a matching $M'$ that leaves $v$ unmatched. Following the 'alternating' path $M\oplus M'$, we get that $v$ is an endpoint of an even length alternating path starting from some unmatched vertex.
> 2. By definition, $v\in Odd(G,M)$ has a neighbour in $Even(G,M)=D(G)$, so $v\in A(G)$, and vice versa. So $A(G)=Odd(G,M)$.
>  > [!warning] Subtlety:
>  > In Edmond's algorithm, whenever a vertex can be labelled both even and odd, label it even. So essentially, $Even(G,M)$ is the set of all vertices that have an even length alternating path from $X$. So in a blossom, all the vertices will be labelled even.
> 3. It follows that $C(G)=Unlabelled(G,M)$.

Every vertex in $A(G)\cup C(G)$ must be matched in every max matching, by definition.
Also, $C(G)$ has no edge to $D(G)$.
Every vertex in $A(G)$ is matched to $D(G)$.
Every vertex in $C(G)$ is matched to some $v\in C(G)$. So all its components are even.

> [!lemma] 
> Every component $H$ in $D(G)$ has the following property:
> Either $H$ has one unmatched vertex and $|M\cap\delta(H)|=0$ or $|M\cap\delta(H)|=1$. Moreover, $H$ is factor-critical.
> *Proof:* Induction on $|H|$.
> Base case is fine.
> Induction step: If $D(G)$ is a bunch of singleton vertices, then we are fine. Otherwise, $H$ contains a blossom, which we shrink and apply induction hypothesis.
> Thus we get 2 and 4. (This is not a complete argument, but can be completed. We need to show that before/after of shrinking preserves the claims in the lemma.)

**To show:** $A(G)$ is a Tutte-Berge witness.
Or, that $|M|= \frac{1}{2}(|V|+|A(G)|-o(G\setminus A(G)))$.
But $|M|= \frac{1}{2}(|V|-|X|)$.
To show: $|X|=o(G\setminus A(G))-|A(G)|$.
Everything in $C(G)$ can be matched within. Everything in $A(G)$ is matched to something in $D(G)$. So, among all the odd components, i.e. all the components of $D(G)$, exactly $|A(G)|$ many components are matched (to $A(G)$), and the rest have exactly one unmatched vertex each. That is what we wanted to show.

## Primal-Dual Algorithm
---
Min-cost perfect matching LP:

$\min \sum\limits_{e\sim E}c_{e}x_{e}$ s.t.
- $\sum\limits_{e\sim v}x_{e}=1\quad \forall v\in V$
- $\sum\limits_{e\in\delta(U)}x_{e}\geq 1\quad \forall U\subseteq V,|U|\text{ odd},|U|\geq 3$
- $x_{e}\geq 0\quad \forall e\in E$.

Dual variables: $y_{U}\quad\forall U\subseteq V, |V|\text{ odd}$

$\max\sum\limits_{U\subseteq V,|U|\text{ odd}}$
$$\sum\limits_{U\subseteq V,e\in\delta(U), |U|\text{ odd}}y_{U}\leq c_{e}\quad\forall e\in E$$
$y_{U}\geq 0\quad\forall U\subseteq V,|U|\geq 3,|U|\text{ odd}$

## Algorithm
---
> [!idea]
> The idea is, because the number of dual variables is exponential, we only maintain a small set of "active" variables, and execute the primal-dual algorithm.

$\Omega:$ set of "active" dual variables
$\Omega=\{ y_{v}\mid v\in V \}$ (Other $y_{v}$ are assumed to be $0$.)

Initialise $y_{v}=0\ \forall y_{v}\in\Omega$. (This is feasible for dual.)
But $x_{e}=0\ \forall e\in E$, so this is infeasible for primal.

> [!success]
> $M=\phi$
> $G':$ graph on tight edges
> $X:$ set of vertices unmatched in $M$
> while $M$ is not perfect:
>> Find an alternating walk $P$ from $u\in X$ to $v\in X$ in $G'$.
>> If $P$ is an augmenting path, update $M\leftarrow M\oplus P$, continue;
>> else, we have a blossom $B$. Shrink $B$ to one vertex $b$.
>> Add $y_{B}$ to $\Omega$, set $y_{B}=0$.
>> > [!note] Note: $b$ is an even vertex.
>> 
>> Continue on $G/B$.
> If no alternating walk from $X$ to $X$ is found, then $M$ is maximum in $G'$, update the dual values:
> >>Find the largest $\epsilon$ s.t.
> > $y_{U}\leftarrow y_{U}+\epsilon$ for even $y_{U}\in\Omega$,
> >$y_{U}\leftarrow y_{U}-\epsilon$ for odd $y_{U}\in\Omega$
> >
> If $y_{U}$ becomes $0$ for $|U|\geq 3$, then unshrink the blossom corresponding to $U$, continue.

**Obs.:** Some edges which were once tight, can become slack (odd-odd/unlabelled). So number of tight edges is not a measure of progress. The measure of progress is the dual objective value.

### Correctness/Optimality
---
Primal objective value $=\sum\limits_{e\in M}c_{e}=\sum\limits_{e\in M}\sum\limits_{U\varepsilon \in\delta(U)}y_{U}=$ Dual objective value.

For all edges in $M$, the dual constraint is tight, which gives the second equality.
Each non zero $y_{U}$ appears exactly once, because it is a perfect matching and, for $U=\{ v \}$, only one $M$ edge is incident on $v$. For a shrunk blossom, $|M\cap\delta(U)|=1$.

### Running time
---
$|\Omega|=n+ \frac{n}{2}= O(n)$
$\frac{n}{2}$ augmentations, we will need $m+n$ time to go over all the edges here, and also during the updating values part.
Between any two augmentations, $\leq \frac{n}{2}$ shrinking operations.

---
# References
[[Linear Programming]]