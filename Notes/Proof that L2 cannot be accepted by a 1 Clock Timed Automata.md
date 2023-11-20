---
tags:
  - Example
---

202311041509

tags : [[Timed Automata]]

#  Proof that $L_2$ cannot be accepted by a 1 Clock Timed Automata
---
>[!tldr] Plan
>We show that a part of the run can of our [[Alternating Timed Automata|ATA]] can be done on an [[Alternating Finite Automaton|AFA]], and we use a pumping lemma type argument on that. 

---
>[!info] DFA Analogy
>Consider a DFA $\mathcal B =\langle Q, q_0, \delta, F\rangle$ over the alphabet $\{a\}$.
>Let $f_{\mathcal B}= q\mapsto\delta(q, a):Q\to Q$ 
>Since the number of function of type $Q\to Q$ are finite, the sequence $\{f_{\mathcal B}^i\}_{i\in\mathbb N}$ will have $l,m$ such that $f_{\mathcal B}^m=f_{\mathcal B}^{m+l}$ and $f_{\mathcal B}^{m+i}=f_{\mathcal B}^{m+l+i}$ for all $i>0$

## Lemma 1
Consider an *ATA* $\mathcal A = \langle Q,q_0, \delta, F\rangle$ over the alphabet $\{a\}$ then let $f_\mathcal A= x\mapsto \delta(x, a) : 2^{2^Q}\to 2^{2^Q}$.
We have that the number of functions of the above type are finite, hence the sequence $\{f_{\mathcal A}^i\}_{i\in\mathbb N}$ will have $l,m$ such that $f_{\mathcal A}^m=f_{\mathcal A}^{m+l}$ and $f_{\mathcal A}^{m+i}=f_{\mathcal A}^{m+l+i}$ for all $i>0$

Consider all *ATA* with $n$ states. and find corresponding $m, l$ for them.
let $M= \max(m)$ and let $L=\prod l$.

---
## Untiming ATA
Let
$$
\begin{align}
L_{2}\quad:=\quad\{(a^k,\tau)\;&:\; (\tau_{1}<\tau_{2}<1) \\
&\land(\tau_{1}+1<\tau_{k}<\tau_{2}+1\text{ for exactly 1 }k) \\
&\land(\tau_{i}<\tau_{i+1}\text{ for all } i<k)\}
\end{align}
$$
FTSOC, let $\mathcal A$ be an *ATA* which recognises the language that has $n$ states. Pick $M$ and $L$ according to [[Proof that L2 cannot be accepted by a 1 Clock Timed Automata#Lemma 1|Lemma 1]]. 

We consider the word $a^{2+M+1+M}$ and we show that $a^{2+M+1+L+M}$ is also accepted by the language.

### No reset at $a_1$ and $a_2$
Since the entire run is in $t\in (1,2)$ and we have that $\tau_i>\tau_{i+1}$ we have that the only useful guards are
- $1<x<2$
- $0<x<1$
And we only ever go the second case if there is a reset.
also, since the guards are between consecutive integer, if we can deal with the reset, then clocks are useless.
So we make 2 copies of the automata, where we keep track of whether $x$ has been reset or not and enable/disable guards accordingly.
We send the control to the copy if a reset is done and hence, after $t=1$ the clocks do not make a difference. Hence the second word is accepted.

### Reset at $a_2$
In this case the value of $x$ from $\tau_2$ to $\tau_2+1$ will be in $(0,1)$ hence all of the guards will always or never be satisfied. Hence we can drop the transitions where the guards fail and remove the guards from where they were valid. Now we can accept the new word at any time stamps and continue after that from the same state.

### Reset at $a_1$ but not at $a_2$
We do a similar procedure in this case. We make 2 copies and we untime the first one considering that there will not be any other resets until $\tau_1+1$. Then we can accept multiple letters in the region $(\tau_1+1,\tau_2+2)$, if there is a reset, we move to the other copy as then the result of the guards will not change as $x$ will always be <1 after that.

---
# Related
- [[Expressability of One-Clock Alternating Timed Automata]]
- [[Alternating Timed Automata]]
- [[Alternating Finite Automaton]]