---
title: "Scientific Data Science"
center: true
theme: black
transition: slide
margin: 0.04
revealOptions:
   transition: 'slide'
css: 
- css/custom.css
---
<grid drop="5 10" drag="90 30" style="font-family:'lato',sans-serif;background-color:#303030;border-radius:8px!important;padding:auto;align:center;">
## Almost Certain Model Chekcing <!-- .element style="font-family:'Montserrat';color:#F8F8F8;" -->
</grid>

<grid drop="0 70" drag="100 30" style="line-height:0.6em;" align="top">
Shubh Sharma <!-- .element style="font-family:'lato';font-size:1.3em;font-weight:500;line-height:0.6;color:#E0E0E0!important;vertical-align:bottom!important;" -->

NOVEMBER, 2023 <!-- .element style="font-family:'Montserrat'; font-size:1.3em;color:#616161;vertical-align:top;font-weight:400;" -->
</grid>

---
# Outline
1. Introduction
1. Linear Temporal Logic
2. Timed Automata
3. Probabilistic Semantics
1. Topological Semantics
1. Correspondence of the two Semantics
2. Model Checking Hardness

---

# Introduction
#### Timed Automata are really nice (=

They let us describe systems with real-time constraints but still satisfy a lot of nice properties like reachability, safety properties, etc ,etc.

<br><br>

### But

---
### **Timed Automata are too nice )=**

Like most mathematical objects, they several assumptions made about them like infinite precision, instantaneous events which are unrealistic

So we discuss two semantics for Linear Time Logic using timed automata that let us model check ignoring cases that are too unlikely/extreme a *topological* and a *probabilistic* one.

---

# Linear Temporal Logic

*Temporal Logics* introduce operators that describe how the world changes without explicitly referring to time. This helps us guarantee properties like
- Safety: Anything bad will not happen
- Liveness: Something good will happen
- Fairness: Evolution of subsystems

--
*Linear Temporal Logic* introduces operators with the assumption that there is one execution path in time. That is, we sort of know what how the evolution of the system will be.

---
## Syntax
We have a set of *Atomic proposition* $\mathcal P$ and the formulae satisfy the following grammar.
![[Pasted image 20231119185337.png|700]]

--
where the 4 temporal operators are
- $\bigcirc f\;\;$ :  $f$ is true in the next state
- $\square f\;\;\;$ : $f$ will be true in all future states 
- $\diamond f\quad$ : $f$ is true in some future state
- $f\cup g$  : $g$ will be true in some state in the future, $f$ is true in each state until then  

And $p\in\mathcal P$

---
## Semantics
The idea is to model a world, that evolves with time, and at every evolution(discrete) some statements are true. We do logic at a particular time in the world and we need to make relations between statements across time.

To give the semantics, we define a satisfactory relation $\models$ of the type $(\mathbb N\to 2^\mathcal P)\times\mathbb N\times LTL$.

We define the boolean operators in the usual manner, for the rest of the operators

--

##### Propositions
$$
\
(\sigma, j)\models p\quad\text{iff}\quad p \in\sigma(j)
$$
![[Pasted image 20231117151425.png]]

--
##### Next
$$
(\sigma, j)\models \bigcirc p\quad\text{iff}\quad (\sigma,j+1) \models p
$$
![[Pasted image 20231117151610.png]]

--

##### Henceforth

$$
(\sigma, j)\models \square p\quad\text{iff}\quad \forall k\cdot(k \geq j \Rightarrow (\sigma,k)\models p)
$$
![[Pasted image 20231117152033.png]]

--
##### Until
$$
(\sigma, j)\models f\cup g\quad\text{iff}\quad \exists k \cdot(A \land B)
$$
where 
- $A = k\ge j \Rightarrow (\sigma,k)\models g$ 
	- $g$ will happen
- $B=\forall i \cdot(j \leq i < k \Rightarrow (\sigma, i) \models f)$
	- $f$ keeps happening $g$

![[Pasted image 20231117152206.png]]

---

# Timed Automata
Now we can formally define *Timed Automata* 

We define a timed automaton $\mathcal A$ as the tuple 
$$
\mathcal A = \langle L, X, E, \mathcal I, \mathcal L\rangle
$$

--
$$
\mathcal A = \langle L, X, E, \mathcal I, \mathcal L\rangle
$$
- $L$ : Location / States
- $X$ : Clocks
- $E \subseteq L \times \mathcal G(X) \times \mathcal 2^{X} \times L$ : Edges
	- State + Guard + Resets -> State
- $\mathcal I : L\to \mathcal G(X)$ : Invariant 
- $\mathcal L : L\to\mathcal 2^{\text{AP}}$
	- $\text{AP}$ is a finite set of atomic propositions
	- Assignment of a logical proposition to each location.

--
**Semantics** of a *Timed Automata* $\mathcal A$ is given by a labelled Transition system $T_{\mathcal A}$
$$
T_{\mathcal A} = \langle S, E \sqcup \mathbb R_{+}, \rightarrow \rangle
$$

- $S$ is a set of *states/symbolic states* $\{s=(l, \nu) \in L \times\mathbb R^{X}_{+}\;:\;\nu\vDash \mathcal I(l)\}$
	- The clock valuations need to respect the state invariant
- We gave 2 kinds of transtions
	- Discrete transitions 
	- Delay transitions
	- And in both cases state invariants should be respected at all times

--
![[Pasted image 20231119204522.png|700]]
$\mathcal A$ is said to be *non-blocking* if $I(s)\ne\emptyset$ for all $s$.

We define a symbolic path as a state, followed by a sequence of edges, such that the delay transitions follow a certain constraint
![[Pasted image 20231119205056.png|700]]
--

### Example
![[Pasted image 20231119222007.png]]

---
# Region Automata
Here, we will modify the region automaton to be a timed automaton. The goal is to use this, as a more well behaved and easy to work version of the original automaton, that satisfies some strong properties which will be discussed later.

--
Let $\mathcal R_\mathcal A$ be the set of regions in $\mathcal A$, then the region automata $\text{R}_\mathcal A$ is $\langle Q, X, T, \kappa,\lambda\rangle$ such that
- $Q=L\times \mathcal R_\mathcal A$
- $\kappa((l,\tau))=\mathcal I(l)$
- $\lambda((l,r))=\mathcal L(l)$
- $X$ is the same set of clocks
- $T\subseteq Q\times \text{cell}(R_\mathcal A) \times E\times \mathcal 2^X\times Q$, so $(l,r)\xrightarrow{\text{cell}(r''),e,Y}(l',r')$ exists if

we can recover the usual region automata by getting rid of time constraints and clocks.

--

### Important Property 
*Path correspondence:* every finite path $\pi((l,\nu),e_{1}\dots e_{n})$ in $\mathcal A$ has a finite set of corresponding paths $\pi(((l,[\nu]),\nu),f_{1}\dots f_{n})$ in $\text{R}_\mathcal A$. Each path in the set represents the choice of regions and delays taken while traversing the above path in $\mathcal A$

Also, if $A$ is non-blocking, so is $\text R_\mathcal A$

---
# Probabilistic Semantics
We will now build some machinery to give probabilistic semantics for LTL formulae

We define a probability measure for $I(s)$ and a probability measure on the set of enabled transitions.
Extending this will give a probability measure on runs.

---
## Probability measure on $I(s)$ and edges
Our probability measure $\pi_{s}$ need to satisfy the following propeties
- $\pi_s(I(s))=1$ 
- given the Lebesgue measure $\lambda$ if $I(s)$ is not finite, $\mu_s$ should be equivalent to $\lambda$, otherwise it is uniform over the points
- Given any $s$, we also define a probability measure $p_s$ on the set of enabled edges

--
## Example
 - Uniform Distribution over $I(s)$ if it is finite.
 - Lebesgue Measure normalised to have a probability measure if $I(s)$ is a finite set of bounded intervals.
 - Exponential distribution if $I(s)$ contains an unbounded interval.
 
The exact measure does note matter as the property we desire are qualitative.

---
# Probability measure on Finite Paths
Given a finite path $\pi(s,e: es)$ , we can define the probability measure on the path as 

$$
\mathbb P_\mathcal A(\pi(s,e:es)) = \frac{1}{2}\int_{t\in I(s,e_{1})} p_{s+t}(e)\mathbb P_{\mathcal A}(\pi(s',es))  d\mu_{s}(t)
$$

This gives a probability distribution on $\text{Runs}(\mathcal A,s)$
--

## Sanity Check!

- Ignore the $\frac{1}{2}$ for now
- Its the probability of that $e_1$ is picked and the rest of the path can be traversed, given that $t$ time has elapsed.
- Integrate that over all $t\in I(s, e_1)$
- For this situation, summing the probabilities of all paths of length $n$ is $1$
- $\frac{1}{2}$ is just the normalisation factor such that now the total probability of a path of any length is $1$

--
## Example

![[Pasted image 20231116231532.png]]

---
## Similar measures on $\mathcal A$ and $\text{R}_\mathcal A$
We assume that for every state $\mu_s^\mathcal A = \mu_{\iota(s)}^{\textbf R_\mathcal A}$ 
this is possible because we have that $I(s)=I(\iota(s))$ 
If $p^\mathcal A$ is distributed over edges in $\mathcal A$, we assume that for every state $s$ in $\mathcal A$ and $t\in \mathbb R_+$ $p_{s+t}^\mathcal A=p_{\iota(s)+t}^{\textbf R_\mathcal A}$ 

This also gives us that probability of a path in $\mathcal A$ is the same as probability of its projection in $\text R_\mathcal A$.

---
# Probabilistic Semantics for LTL
We consider runs of a *timed automaton* as sequences of worlds over which we give semantics for our *LTL* formulae.

Here we see $\mathcal L$ begin used for the very first time. This is like the function which assigns worlds *atomic proposition*.

---
# Probability on LTL Formulae

Since satisfiability only depends on states, either all, or none of the runs in a path satisfy the formula. Hence we give probability to an LTL formula $\varphi$ from $s$ as 

![[Pasted image 20231119235346.png|600]]
Which is the total probability of all paths that satisfy $\varphi$.

---
## Satisfying LTL formulae

We say that $\mathcal A$ *almost surely satisfies* $\varphi$ from $s_0$ wrt $\mathbb P_{\mathcal A}$ and write $\mathcal A,s_0 \mid\!\approx_{\mathbb P} \varphi$ iff $\mathbb P_\mathcal A(s_0,\varphi)=1$.

And because of the earlier claim we have.

![[Pasted image 20231120000557.png|500]]

---
