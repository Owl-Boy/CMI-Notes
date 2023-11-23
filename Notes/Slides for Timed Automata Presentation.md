---
title: Almost certain model checking
theme: black
bg: black
height: "900"
---
<grid drop="5 10" drag="90 30" style="font-family:'lato',sans-serif;background-color:#303030;border-radius:8px!important;padding:auto;align:center;">
## Almost Certain Model Checking <!-- .element style="font-family:'Montserrat';color:#F8F8F8;" -->
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
The idea is to model a world, that evolves with time, and at every evolution(discrete) some statements are true. We can do propositional logic at a particular time in the world and we need to make relations between statements across time.

All Temporal Operators are defined to satisfy the previous description.

---
## Semantics for LTL using Timed Automata
Runs in a timed automata provide sequences of worlds, on which the semantics of LTL can be defined.

We say that a timed automata $\mathcal A$ satisfies the LTL formula $\varphi$ from $s$ if every run starting from $s$ satisfies $\varphi$

---

# Timed Automata
Now we can formally define *Timed Automata* 

We define a timed automaton $\mathcal A$ as the tuple 
$$
\mathcal A = \langle L, X, E, \mathcal I, \mathcal L\rangle
$$

We modify the definition of $E$ to respect $\mathcal I$

--

## Example
![[Pasted image 20231120095817.png]]

note: point out at the x <= 1

---
## Some important Things
![[Pasted image 20231119204522.png|700]]
$\mathcal A$ is said to be *non-blocking* if $I(s)\ne\emptyset$ for all $s$.

We define a symbolic path as a state, followed by a sequence of edges, such that the delay transitions follow a certain constraint
![[Pasted image 20231119205056.png|700]]

---
## Machinery for Probabilistic Semantics
We want to define a probability measure on the set of runs, to do that, we give properties for valid probability measures $\mu_s$ for edges.
- Given any state, some edge can  be eventually taken : $\mu_s(I(s))=1$
- If $I(s)$ is finite, then $\mu_s$ is uniform distributions between the points, otherwise it is equivalent to the Lebesgue measure $\lambda$.(volume of the set in $\mathbb R$)
- We also define $p_s(e)$ to be the probability measure defined on edges enabled from $s$

---
## Probability measure on Finite Paths
Given a finite path $\pi(s,e: es)$ , we can define the probability measure on the path as 

$$
\mathbb P_\mathcal A(\pi(s,e:es)) = \frac{1}{2}\int_{t\in I(s,e_{1})} p_{s+t}(e)\mathbb P_{\mathcal A}(\pi(s',es))  d\mu_{s}(t)
$$

This gives a probability distribution on $\text{Runs}(\mathcal A,s)$

We can give a similar probability distributions for stuff in $\text{R}_\mathcal A$ and get an equivalent probability distribution on $\text{Runs}(\text R_\mathcal A, \iota(s))$ 

---
## Probabilistic Semantics for LTL
Due to the semantics, LTL formulas only depend on the sequence of states in the run. Hence given an LTL formula $\varphi$ and path $\pi$ in a timed automata, either all the runs of $\pi$ satisfy $\varphi$ or none of them do.

So we can define the probability of a formula as the probability of all of the paths that accept it.

We say $\mathcal A$ *almost surely* satisfies $\varphi$ from $s_0$ and write $A,s \mid\!\approx_\mathbb P \varphi$ iff $\mathbb P_\mathcal A(s_0,\varphi)=1$

---
## Dimension of a Path
A path is a set of runs over a fixed sequence of edges, for each edge $e$ from a state $s$, once can pick $t\in I(s, e)$ to take the edge. This naturally leads to the questions: Can a path be embedded in $\mathbb R^m$ for some $m$?

Idea: We map each run to the polyhedron $(\tau_1\dots \tau_n)\in\mathbb R^n$ for a given path.

---
## Finding the Dimension
We say that the edges where the guard is a singleton, do not add dimension to the path, and the edges in which the guards are a non-degenerate interval, add 1 to the dimension.

We say that the dimension of a path is undefined if there exists $s$ which is reached by the sequence of edges $e_1\dots e_i$ from $\pi$ and dimension of $\text{Pol}(\pi_{\mathcal C}(s_0, e_1\dots e_i+1))<$ dimension of $\text{Pol}(\pi_{\mathcal C}(s_{0},e_{1}\dots e_{i},e))$ for some outgoing $e$ from $s$. Otherwise it is defined.

---
## Topology on the Space of Runs
Our goal is to give *topological semantics* for LTL, where we ignore extremely unlikely events while checking if the model satisfies the formula, those unlikely events intuitively correspond to small sets, which we define to be meager(countable union of nowhere dense sets).

We can define the topology to be paths that have a defined dimension. This makes sure that only paths where for some $s$ and an outgoing $e$, $I(s, e)$ is singleton and $I(s)$ is not.

---

## Topological Semantics for LTL
Now that we have defined what counts as small,we consider co-meager sets as large. Then we say that $\mathcal A$ *largely satisfies* $\varphi$ from $s$ and write $A,s \mid\!\approx_\mathcal L \varphi$ iff $[\![\varphi]\!]$ is large.

---
## Banach Mazur Games
A Banach Mazur Game is a 2-player infinite game which involves chasing points in a topological space.  To play the game there must be
- Topological Space $Y$
- Target Set $X\subseteq Y$
- A family of sets $\mathcal W$ such that
	- each $W\in \mathcal W$ contains an open set
	- Each open set contains a set in $\mathcal W$

The game proceeds by player 1 and player 2 take turns in choosing nested sets from $\mathcal W$. If the intersection of these sets with $X$ is non empty, then player 1 wins, otherwise player 2 wins

---
## Winning Strategies
There is a winning strategy for player 2 iff $X$ is small.

Since $X$ is a countable union of nowhere dense sets, on each turn, player 2 will decide to avoid of the sets in the union.

If $Y$ is a metric space, then there exists a winning strategy for player 1 iff $X$ is large is some open set.

Player 1 picks a family member in the open set for her first move, and then steals the player 2 strategy targeting the complement of the target set. While making sure intersection of the chain is nonempty

---
## Correspondence Between the two Semantics
$A, s\mid\!\approx_\mathbb P \varphi\Leftrightarrow A,s\mid\!\approx_\mathcal L\varphi$


Discovering Winning Strategies in Banach Mazur Games proves that the target set is small. 
It is used in the proof that the set of runs that satisfy $\lnot\varphi$ is small if $\varphi$ is almost surely satisfied.

---
# THANK YOU  <3
![[Pasted image 20231120101815.png]]

Here is a Tomato Tomato for you!