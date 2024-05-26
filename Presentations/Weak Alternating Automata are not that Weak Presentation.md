---
theme: black
height: "1500"
width: "1800"
---

<grid drop="5 10" drag="90 40" style="font-family:'Inter',sans-serif;background-color:#303030;border-radius:8px!important;padding:auto;align:center;">
# Weak Alternating  <!-- .element style="font-family:'lato';color:#F8F8F8;" -->
#  Automata are <!-- .element style="font-family:'lato';color:#F8F8F8;" -->
#  not that weak<!-- .element style="font-family:'lato';color:#F8F8F8;" -->
</grid>

<grid drop="0 55" drag="100 30" style="line-height:0.6em;" align="top">
Jessica, Shubh and and Sreevani <!-- .element style="font-family:'Inter';font-size:1.6em;font-weight:500;line-height:0.6;color:#E0E0E0!important;vertical-align:bottom!important;" -->

April, 2024 <!-- .element style="font-family:'Nanum Pen Script'; font-size:1.8em;color:#616161;vertical-align:top;font-weight:400;" -->
</grid>

---

> [!note] Alternating Automata
> An alternating automata is defined by the following tuple
> $\langle Q, \Sigma, q_{in}, \delta, \alpha\rangle$
> where $\delta : Q\times \Sigma \to \mathcal B^+(Q)$

> [!note] Weak Alternating Automata
> It is an Alternating Automata where
>- $Q = \bigsqcup_{i \in [k]}Q_{i}$ such that $Q_{i} \subseteq \alpha$ or $Q_{i} \cap \alpha = \emptyset$
>- There is a partial order $\leq$ on the partition such that any transition goes to a state in partition that is less than or equal to the current one.

note:
State the *true-false* thingy

---
## Runs in Alternating Automata
Runs in alternating automata can be represented as trees in the following way 
$\langle T_{r}, r\rangle \langle\rangle\langle\rangle$
where $r$ is a labelling function from nodes of $T_{r}$ to $Q$ 

note:
Nodes of T_r representation

--

## Memoryless Runs

> [!note] Similar Nodes
>Two nodes are called *similar* if 
>- They have the same depth
>- They are labelled by the same state

> [!note] Memoryless runs
> A run is called memoryless if subtrees of similar 
> any pair of nodes are identical

> [!done] lemma
>Any accepting word has a accepting memoryless run on an Alternating Co-Buchi Automata.

note:
The Lemma is for Parity Automata(games i think lol) Alternating Co-Buchi is a special case

---

## DAG representation 
Quotienting similar nodes together to get a Directed Acyclic Graph from a tree $G_{r}$.

- Endangered: Only finitely many states are reachable 
- Safe: No $\alpha$ state is reachable

![[Pasted image 20240424065726.png]]


note:
DRAWWWWWW
mention progress measures
rank is like ease of acceptance proof

--
## Rank
![[Pasted image 20240424070048.png]]

> [!note] Lemma
> For every $i > 0$, there exists $d_{i}$ such that forall $d \geq d_{i}$, 
> there are at most $n-i$ vertices at depth $d$

note: 
mention odd for safe and even for endangered
Induction, 
- If finite then trivial
- Otherwise G_i+1 is infinte and we can find a safe state

Lemma : G2n is finite hence finite rank

--
> [!note] Lemma
> For any two states $s_{1}=\langle q_{i}, i\rangle$ and $s_{2}=\langle q_{j}, j \rangle$, if $s_{2}$ is reachable from $s_{1}$ 
> then rank of $s_{2}$ is less than the rank of $s_{1}$

> [!note] Final Lemma
> In an infinite path on $G_{r}$ there exists $\langle q, l \rangle$ such that every node after it in the run has 
> the same rank as itself which must be even.

note:
if $s_{1}$ is removed, its remaining descendants    
Induction : find fixpoint. And it cannot be even because infinte chain

---
## Alternating Co-Buchi to Weak Alternating Automata


> [!note] Theorem
> For every Alternating Co-Buchi Automata $A_{C}$, there exists a Weak Alternating Automata $W$ such that $\mathcal L(W) = \mathcal A_{C}$ and there is a quadratic blowup in number of states.

![[Pasted image 20240424072219.png]]
![[Pasted image 20240424072304.png]]
![[Pasted image 20240424072326.png]]

note:
Weak..duh
L(W)<= L(A_c) => (Tr, r) in W and (Tr, r') in A_c such that r(x) = q_i, n and r'(x) = q_i (projection).
L(A_c)<= L(W) => (Tr, r) in A_c, just get the ranks from constructions

Release Function
replacing an atom q by disjuction of (q,i)  

--
## Alternating Buchi to Weak Alternating Automata 
- Complement Buchi by taking a dual and produce Alternating Co-Buchi
- Convert CoBuchi to WAA
- Complement WAA (dual of edges and complement of good states)


--

## Improving Construction

> [!note] Required Rank
> We say that $j \in [n]$ is required for $w$ iff there exists $w\in \mathcal L(W)$ 
> such that for every memoryless run $\langle T_{r}, r \rangle$ of $ W$  on $w ,\; G_{2j+1}\ne \emptyset$

> [!note] Minimal rank
> Minimal rank is the max required rank 
> 

![[Pasted image 20240424081344.png]]

--
## Complexity of Finding the Minimal Rank

> [!note] Theorem
> Let $A_{C}$ be an alternating co-Buchi Automaton. The problem of finding minimal rank is $\text{PSPACE-Complete}$ .

---
## Complementing Buchi Automata
> [!note] Theorem 
> Let $A_{B}$ be an alternating Buchi Automata. There is a NBA $N$ with exponentially many states such that $\mathcal L(N) = \mathcal L(A_{B})$.

The Construction is as follows
- Given $A_{B} = \langle \Sigma, Q, q_{in} \delta, \alpha\rangle$ we construct
- $N =\langle \Sigma, 2^Q \times 2^Q, (\{ q_{in} \}, \emptyset ),\delta', 2^Q \times \{ \emptyset \} \rangle$ 

![[Pasted image 20240424082234.png]]

--
## The Actual Thing
Given the above construction
1. we build from $N$ its dual co-Buchi universal automaton $A_{C}$. The automaton $A_C$ satisfies $\mathcal L(A_{C}) = \Sigma^\omega \setminus \mathcal L(N)$. 
2. construct from $A_{C}$ its equivalent weak alternating automaton $W$. The automaton $W$ satisfies $\mathcal L(W) = \Sigma^\omega \setminus \mathcal L(N)$ 
3. construct from $W$ its equivalent nondeterministic Buchi automaton $N_{C}$. The automaton $N_C$ satisfies $\mathcal L(N_{c}) = \Sigma^\omega \setminus \mathcal L(N)$. 

note:
draw this on the board

--
## Optimizing Construction
We shall restrict the set of states to set of size  $2^{O(n\log n)}$ by using the following definition by using the structure of the weak alternating automata.

> [!note] Consistent
> We say that a subset $S$ is consistent if $(q, i) \in S$ and $(q, j) \in S$ implies $i= j$


--
## Final Construction
![[Pasted image 20240424082846.png]]