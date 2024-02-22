---
tags:
  - Note
  - Incomplete
---
202402141102

Tags : [[Complexity Theory]]
# Immerman–Szelepcsényi Theorem [1987]
---
> [!question] $NSPACE(S(n))=coNSPACE(S(n))$ if $S(n)\geq \log n$ is fully space constructible.

*Proof:* We will only prove $NSPACE(\log n)=coNSPACE(\log n)$, or in other words $NL=coNL$, and generalising will be left as an exercise.

> [!tip] Idea:
> We want to find some $NL-$complete problem and show that its complement is in $coNL$.

If $M$ is an $NL$ machine then $\forall x \in\Sigma^{*}$, in the configuration graph $G_{M,x}$, $M$ with input $x$, $x \in L(M)$ iff there is a directed path in $G_{M,x}$ from $Init$ to $Final$.

${PATH}=\{ (G,s,t):\exists \text{ a directed }s\text{ to }t\text{ path in }G \}$ is $NL-$complete wrt logspace reductions.
$\overline{PATH}=\{ (G,s,t):\not\exists \text{ an }s\text{ to }t\text{ path in }G \}$

> [!help] *Claim:* $NL=coNL\iff \overline{PATH}\in NL$.
 *Proof:* Forward direction is easy.
 Backward direction is also easy.

### Nondeterministic inductive counting
---
$A_{0}=\{ s \}$.
$A_{i}=\{ u\in G: \exists \text{ an }s \text{ to }u\text{ path of length}\leq i \}$.
Is $t\in A_{n}$?

> [!hint] We want to guess all the vertices that are reachable from $s$, but we don't have the space, so we will guess how many, and verify, nondeterministically.

$c=$ # vertices reachable from $s$, $|c|=\log n$.
Suppose $|A_{n}|=c$ is given as part of input.
**Input:** $(G,s,t,c)$
Then $\overline{PATH}$ has an $NL$ machine.
*Proof:*
*Goal:* Verify that $c$ vertices in $G\setminus t$ are reachable from $s$.

> [!success] 
 $V=\{ 1,2,\dots,n \}=V(G)$
 $s=1$
 $c':=1$;
 for each $u\in G\setminus t$, guess:
 whether $u$ is reachable from $s$, i.e. $(G,s,u)\in PATH$?
 If 'yes' then also guess an $s-u$ path and increment $c'$, and on other paths REJECT.
 end;
 ACCEPT iff $c'=c$.

#### Inductive Counting NL machine
---
$NL$ machine that takes $(G,s,c_{i})$ as input and compute $c_{i+1}$.
$c_{i}=|A_{i}|$, $c_{0}=1$

**Obs.:** $v\in A_{i+1}\iff v=s$ or $v$ is adjacent to something in $A_{i}$.
$v\notin A_{i+1}\iff \forall u\in A_{i}$, $(u,v)$ is a non-edge.

> [!success]
 $c'_{i+1}:=0$;
 $(*)$ For each $v\neq s$, do:
 {
 $counter_{i}:=0$;
 for each $u$, do:
 Guess if $u\in A_{i}$;
 If 'YES' then also guess an $s-u$ path; 
 $counter_{i}:=counter_{i}+1$
 if $(u,v)\in E$, then
 $c_{i+1}:=c_{i+1}+1$;
 goto $(*)$
 end-for
 }
 If $counter_{i}=c_{i}$, then goto $(*)$
 else REJECT

Property of this $NL$ machine: On every non rejected path, $c_{i+1}$ is the correct value.

---
Now that we have that $NSPACE(S(n))=coNSPACE(S(n))$, for fully space constructible $S(n)$, we are ready for the [[Non deterministic Space Hierarchy Theorem]]


> [!hint] $CSL=NSPACE(n)$
> $CSL$ is Context-Sensitive Language: In the grammar, transitions are of the form $\alpha\to\beta$, where $|\alpha|\leq |\beta|$, and $\alpha \in(\Sigma \cup V)^{*}V(\Sigma \cup V)^{*}$.

---
# References
