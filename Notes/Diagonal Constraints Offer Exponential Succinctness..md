---
tags:
  - Example
---

202310282118

tags : [[Timed Automata]]

#  Diagonal Constraints Offer Exponential Succinctness.
---
>[!abstract]  Abstract, lmao
>We will show that *d-timed automata* are exponentially more succinct that *diagonal free timed automata* by constructing a set of languages $\{L_{i}\}_{i\in \mathbb N}$  such that for each $L_i$ there is a *d-timed automaton* of size polynomial in $n$ and a *diagonal free timed automaton* that has exponential states in $n$.

Let $L_i$ be defined as follows
$$
\left\{\;\left(a^{2^n},\tau \right)\ |\ 0<\tau_{1}<\tau_{2}<\cdots<\tau_{2^n}<1\;\right\}
$$
---
## Construction of a small *d-timed automaton*
We use a counter $c$ that can store $n$ bits and its initial value if $0$, each time an $a$ is seen, the counter is incremented and after $2^{n-1}$ $a$s we accept the last one and go to the final state.

We use $n$ pairs of clocks to encode the counter bits, for the $i^\text{th}$ bit, we have clocks $x_i$ and $x_i'$ such that the value of the counter bit $b_i$ is
$$
b_{i} = 
\begin{cases}
0&x_{i}-x_{i}'=0 \\
1&x_{i}-x_{i}'>0
\end{cases}
$$
The incrementing of the counter works in the following manner, if the first $j-1$ bits $1$ and the next bit is $0$. We set the first $j-1$ bits to $0$ and the $j^{\text{th}}$ bit to $1$ and stop. This gives us a set of $n-1$ transitions(to check if the first $n-1$ digits are $1$ and next digit is $0$).

then the $j^\text{th}$ transition is 
$$
\begin{cases}
g_{j}\text{ is } \left(\bigwedge\limits_{x=1}^{j-1} (x_{i}-x_{i}'>0)\right) \land (x_{j} -x_{j}'=0) \\ \\
R_{j}\text{ is } \left(\bigcup\limits_{i=1}^{j-1}\{x_{i},x_{i}'\}\right) \cup\{x_{j}'\}
\end{cases}
$$
There is a final transition that checks if all bits are 1 and $x_{n}<1$ and takes us to final state. 
There are only $2$ states and $n+1$ transitions.

---
## Every *Diagonal Free Timed Automata* for $L_i$ has atleast $2^i$ states
**FTSOC:** 
Lets say there is a state a *diagonal free timed automaton* $\mathcal B_n$ that has less thatn $2^n$ states.
Then consider the word defined below
$$
w:=
\begin{matrix}
\left(a^{2^n},\tau\right) & \text{s.t.} & \tau_{i}= \frac{i}{2^n+1}
\end{matrix}
$$
clearly $w\in L_{n}$, there is an accepting run in $\mathcal B_n$ on $w$:
$$
(q_{0},v_{0})
\xrightarrow{\delta_{0},\theta_{0}}
(q_{1},v_{1})
\xrightarrow{\delta_{1},\theta_{1}}
\dots 
(q_{2^n},v_{2^n})
$$
but since the number of states are less than $2^n$. There exists $i, j$ such that $i\ne j$ and $q_i = q_j$. However, the total time spent in the run is less that $1$, there for every transition, all clock evaluations belong to $(0,1)$. Thus for the above run, we can say that during any transition, the clock would have satisfied the guards of all the transitions in the run. Hence consider the word $\left(a^{2^n -(j-i)},\tau\right)$ such that 
$$
\tau_{k} = 
\begin{cases}
\frac{k}{2^n+1} &\text{if } k\leq i \\ \\
\frac{k+j-i}{2^n+1} &\text{if } k >i
\end{cases}
$$
using the fact that all guards used in the previous run accept in the hypercube $(0,1)^X$ we have the following run
$$
(q_{0},v_{0})
\xrightarrow{\delta_{0},\theta_{0}}
(q_{1},v_{1})
\xrightarrow{\delta_{1},\theta_{1}}
\dots
(q_{i},v_{i})
\xrightarrow{\Delta,\theta_{j}}
(q_{j+1},v_{j+1})
\xrightarrow{\delta_{j+1},\theta_{j+1}}
\dots
(q_{2^n},v_{2^n})
$$
where $\Delta = \frac{(j-i)+1}{2^n+1}$
Hence $\mathcal B_n$ accepts the above word, which is a contradiction.

---
# Related
[[Timed Automata with Diagonal Constraints]]
[[D-Timed Automata to Timed Automata Construction]]