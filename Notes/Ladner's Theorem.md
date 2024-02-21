---
tags:
  - Note
  - Incomplete
---
202402131202

Tags : [[Complexity Theory]]
# Ladner's Theorem
---
> [!question] If $P\neq NP$, then do we have any problem that's in $NP\setminus P$ but is not $NP-complete$?

**Theorem (Ladner's):** If $P\neq NP$ then there *is* an $L\in NP$ s.t.
1. $L\not\in P$.
2. $L$ is not $NP-complete$.

- $\equiv_{m}^{P}$ is an equivalence relation on $NP$. $NP/\equiv^{P}_{m}$ with $\leq^{P}_{m}$ is a partial order, with $P$ as the bottom element and $NPC$ as the top element.
- An antichain in this poset is a set $\{ A_{1},A_{2},\dots \}\subset NP$ s.t. $A_{i}\not\leq^{P}_{m}A_{j}\quad \forall i\neq j$.

> [!attention] In fact, there are infinitely many problems along any chain, and it is dense. Also, there are infinitely many anti-chains.

*Proof (Ladner's theorem, Impagliazzo's proof):*

Our goal is to construct $f$ so that $A$ fulfils the following requirements:
1. $\forall i\quad A\neq L(M_{i})$ (call this requirement, $R_{i}$), where $M_{1},\dots,M_{i},\dots$ is an enumeration of clocked polytime $DTM$s ($M_{i}$ runs in $n^{i}$ time for length $n$ inputs.)
2. Let $f_{1},\dots,f_{j},\dots$ be the enumeration of all clocked poly time bounded transducers ($f_{j}$ runs in time $n^{j}$.)
$S_{j}:f_{j}$ is not a reduction from $SAT$ to $A$ $\forall j$.
$\exists x$ s.t. $x \in SAT$ and $f_{j}(x)\not\in A$, or $x \not\in SAT$ and $f_{j}(x)\in A$.
3. $A\in NP$.

> [!hint] $A$ will be a "padded" version of $SAT\subseteq\Sigma^{*}$.
> We want to construct a function $f:\mathbb{N}\to \mathbb{N}$ s.t. $f(n)$ is poly(n) time computable and $A=\{ x10^{f(|x|)-|x|-1}: x\in SAT \}\subseteq\Sigma^{*}$.

If $f(n)=n^{i}\quad\forall n\geq n_{0}$, ($i$ fixed), then $A$ is $NP-$complete. (We can reduce $SAT$ to $A$ as: $x\mapsto x 10^{f(|x|)-|x|-1}$, in polytime).

#### Construction of $f$
$i=1,n=1,f(1)=2$

Do forever:
0. Suppose the current values are $i$ and $n$. (All requirements $R_{1},\dots,R_{i-1}$ have been satisfied and $f(m)$ for $m<n$ is already defined.)
1. Let $f(n)=n^{i}$. Search for a $y \in \Sigma^{\leq \log n}$ (witness that $A\neq L(M_{i})$) such that $y \in L(M_{i})$ and $y\not\in L$ or $y \in L$ and $y\not\in L(M_{i})$;
Then $y=A 10^{f(|A|-|A|-1)}$ for some $A$. Check if $A \in SAT$ in $poly(n)$
2. if witness found $i:=i+1$;
3. Either way, $n:=n+1$;
4. End.

**Claim 1:** $A\not\in P$.
Suppose not. $A=L(M_{i})$ for some polytime machine $M_{i}$. So $f(n)=n^{i}\quad\forall n\geq n_{0}$ for some $n_{0}$. $A$ is also $NP-$complete. But we assumed $P\not=NP$. Contradiction!

> [!note] $(*)$ How $f$ grows:
> $\forall k\ \ \exists n:f(n)=n^{k}$, and $f(n)=n^{k}\implies f(n+1)=n^{l}, l\in\{ k,k+1 \}$.

**Claim 2:** $A$ is not $NP-$complete.
Suppose not. Then some $f_{j}$ is a reduction from $SAT$ to $A$. $f_{j}$ is polytime computable $\implies |f_{j}(x)|\leq |x|^{j}$.

*Aim:* If $A$ is $NPC$, we want to give a polytime algo for $SAT$.

By $(*)$, we can get an $n_{0}$ for $j$.
Let $x$ be a $SAT$ instance s.t. $|x|>n_{0}$.
$x \in SAT$ iff $f_{j}(x)\in A$ so $f_{j}(x)=y 10^{f(|y|-|y|-1)}$ for some $y$.
Check if $f_{j}(x)$ is in the right format.
*Case 1:* $|y|\leq n_{0}$.
Check if $y \in SAT$ by brute force.
*Case 2:* $|y|>n_{0}\implies$

...

---
**Theorem:** There are oracles $B$ s.t. $P^{B}= NP^{B}$.
*Proof:* Choose $B$ to be an $EXP-$complete problem.

**Theorem:** There is an oracle $A$ s.t. $P^{A}\neq NP^{A}$. [Hopcroft-Ullman]
*Proof:* $L(A)=\{ 0^{n}:\text{if }\exists w\in A \text{ s.t. }|w|=n \}$.
Unary language $L(A)\subseteq 0^{*}$.
$\forall A,L(A)\in NP^{A}$.
*Goal:* Construct oracle $A$ so that $L(A)\not\in P^{A}$.
We have to ensure that $L(A)\neq L(M_{i}^{A})$ for every *polynomial-time* oracle $DTM \ M_{i}$ with oracle $A$. ($M_{1},M_{2},\dots$ is an enumeration of all oracle $DTM$s.)

for $i=1$ to $\infty$, do:
Current oracle is $A_{i-1}$.
Choose $n$ more than all query or input lengths that have so far occurred in the previous stages $(1,\dots,i-1)$.
Simulate $M_{i}$ on $0^{n}$ for $n^{\log n}$ steps. (We only need $p(n)<n^{\log n}<2^{n}$, so something like $2^{\sqrt{ n }}$ also works.)
If $M_{i}$ queries for $q \in A$, answer according to $A_{i-1}$, and in the end if $M_{i}$ rejects(?) $0^{n}$, put an unqueried $w\in A_{i}$ of length $n$. (This exists because $n^{\log n}<2^{n}$.)
else leave $A_{i}\cap \{ 0,1 \}^{n}=\phi$.




---
# References
