---
tags:
  - Assignment
---

# Timed Automata Homework 1
Name: Shubh Sharma
Roll Number: BMC202170

### 1.
![[Drawing 2023-09-16 13.47.36.excalidraw|600]]

### 2.
Let 
- $Q = S\cup A\cup B\cup C\cup D$ where
	- $S = \{s\}$
	- $A=\{a_{0}\}$
	- $B = \{b_{0}, \dots,b_{3}\}$
	- $C = \{c_{(i,j)}\}$ where $i,j\in\{0..3\}$
	- $D = \{d_{3}, \dots d_{6}\}$
- $\Sigma=\{a,b,c,d\}$
- $X=\{*\}$
- $Q_{0}= S$
- $F = D$

And for the transitions, we have a transition from $s$ to $a_{0}$ accepting $a$ and resetting the clock.

We have transitions $a_{0}$ to $b_{i}$ for $i\in \{0..3\}$ accepting $b$ if clock reads $i$. We reset the clock

We have transitions $b_{i}\in B$ to $c_{(i,i+t)}$ if $c_{(i,i+t)}\in C$ which accept $c$ if clock reads $t\in\{0..3\}$. We reset the clock. $i+t$ is when $c$ is accepted after $a$ so first condition checks

We have transitions $c_{(i,j)}\in C$ to $d_{j+t}$ if $d_{j+t}\in D$ and $j+t-i\ge 3$ which accept $d$ if the clock reads $t\in\mathbb N$.   $j+t$ is when $d$ is accepted and $i$ is when $b$ was accepted, so second conditions also checks
### 3.
Consider a language $L$, we can construct a timed automaton $\mathcal A$ that accepts $L$, and because of question 4, without loss of generality, assume $\mathcal A$ has just $1$ clock and let $l$ be one more than the largest number in any guard. And that the __clock is reset on every transition__.

Since the clock resets on every transition. If there is a transition, from a state whose guard is satisfiable. Then we keep the transition otherwise we remove it. As, given a state and such a transition, we can always wait for a suitable amount of time and take the transition.

Construct a new timed automaton $\mathcal A'$ where we remove everything related to clocks, it becomes a standard finite state automaton. This automata accepts $\text{Untime(L)}$ as for any run in $\mathcal A$, there is a corresponding run in $\mathcal A'$ accepting the same word. And for any run in $\mathcal A'$, we can look at the corresponding transitions in $\mathcal A$, which can always be taken because the clock always resets.

### 4.
Suppose we are given a Discrete Timed Autotmaton $\mathcal A$ such that $|X|=n$. let $l$ be one more than the largest number occurring in any guard.

We construct a new automata $\mathcal A'$ such that    
- $Q'=Q\times\{0,1,2\dots l\}^{n}$  
- $\Sigma' = \Sigma$
- $X' = \{*\}$
- $Q_{0}' = \{(q, \underbrace{0,\dots 0}_{n \text{ 0s}})\ :\ q\in Q_{0}\}$ 
- $F_{0}' = \{q' :\ \text{ such that } q \text{ is the first component of } q' \text{ and } q\in F_{0}\}$ 
- $T'$ = all tuples $(q', g', a, R', q_{1}')$ for all $t\in \{0..l\}$ where
	- $q' = (q, a_{1}, a_{2},\dots a_{n})$
	- $R' = \{*\}$
	- $q_{1}''=(q_{1},b_{1},b_{2}\dots b_{n})$ where $b_{i}=\min\{l,a_{i}+ t\}$
	-  We get $g'$ by replacing clock $i$ with $b_{i}$ in $g$
	- if replacing clock $i$ with $b_{i}$ in $g$ satisfies it
	- $q' = (q_{1}, c_{1}, \dots c_{n})$ where $c_{i}= 0$ if clock $i$ is in $R$ and $b'$ otherwise.

Here we have constructed a discrete timed automaton with just $1$ clock, that is $*$. Since none of the guards can differentiate between number $\ge l$ we represent all of them by $l$. This gives a finite amount of configurations represented by clocks.
  