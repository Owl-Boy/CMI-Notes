---
tags:
  - Note
  - Incomplete
---
202311162211

Tags : [[Timed Automata]], [[Probability]]
# Probability Measure over Finite Paths in a Timed Automata
---
Let $\mathcal A$ be a [[Timed Automata Alternate Definition|Timed Automaton]] and let $\pi(s, e_1, e_2\dots e_n)$ be a symbolic path to be fired. Then we define a probability measure on the sequence of transitions as follows.

$$
\mathbb P_{\mathcal A}(\pi(s,e_{1}\dots e_{n})) = 
\frac{1}{2}
\int_{t\in I(s, e_{1})} \, 
    p_{s+t}(e_{1})
    \mathbb P_{\mathcal A}(\pi(s_{t},e_{2}\dots e_{n})) 
d\mu_{s}(t) 
$$
where $s\xrightarrow{t,e_{1}}s_t$ .
We initialise $\mathbb P_\mathcal A(\pi(s))=\frac{1}{2}$ 

>[!attention] Don't get intimidated by the formula (Sanity Check)
>Ignore the $\frac{1}{2}$ for now
>Its the probability of that $e_1$ is picked and the rest of the path can be traversed, given that $t$ time has elapsed.
>Integrate that over all $t\in I(s, e_1)$
>For this situation, summing the probabilities of all paths of length $n$ is $1$
>$\frac{1}{2}$ is just the normalisation factor such that now the total probability of a path of any length is $1$

>[!example]
>![[Pasted image 20231116231532.png]]

The above formula gives us 

>[!note] Lemma A
>*Statement:* For every state $s$, $\mathbb P_{\mathcal A}$ is a probability measure over $\text{Runs}(\mathbb A, s)$ 
>*Proof Sketch:* Induction 
>- Base case: 0 len paths
>- For each $e$, consider paths that start with $e$. Probability that any of such paths will be taken is probability $e$ will be taken
>- Sum up over all $e$ to get 1

---
## Similar Measures on $\mathcal A$ and $\textbf{R}_\mathcal A$
We assume that for every state $\mu_s^\mathcal A = \mu_{\iota(s)}^{\textbf R_\mathcal A}$ 
this is possible because we have that $I(s)=I(\iota(s))$ 
If $p^\mathcal A$ is distributed over edges in $\mathcal A$, we assume that for every state $s$ in $\mathcal A$ and $t\in \mathbb R_+$ $p_{s+t}^\mathcal A=p_{\iota(s)+t}^{\textbf R_\mathcal A}$ 

so we get
>[!note] Lemma B
>*Statement:* Let $\mathcal A$ be a non-blocking Timed Automata. If measure in $\mathcal A$ and in $\textbf R_\mathcal A$ are similar as explained above and $\pi$  be  a path in $\mathcal A$. Then $\iota(\pi)$ is a $\mathbb P_{\textbf R_\mathcal A}$ measurable set  of runs in $R_\mathcal A$
> *Proof Sketch:* Consider a path in $\mathcal A$, this corresponds to a set of paths in $\textbf R_\mathcal A$, Then restrict the path in $\mathcal A$ such that it corresponds to a single path in the region automaton. 
> Find the measure of that, and these will be equivalent 


---
# References
[[Machinery for Probabilistic Semantics for Timed Automata]]
[[Timed Automata Alternate Definition]]
[[Region Automata Alternate Definition]]