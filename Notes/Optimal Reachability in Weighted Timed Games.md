---
title: Optimal Reachability in Weighted Timed Games
theme: black
height: "900"
bg: black
---

<grid drop="2 10" drag="95 35" style="font-family:'lato',sans-serif;background-color:#303030;border-radius:8px!important;padding:auto;align:center;">
## Optimal Reachability in Weighted Timed Games<!-- .element style="font-family:'Montserrat';color:#F8F8F8;" -->
</grid>

<grid drop="0 70" drag="100 30" style="line-height:0.6em;" align="top">
Aditi Muthkhod<!-- .element style="font-family:'lato';font-size:1.3em;font-weight:500;line-height:0.6;color:#E0E0E0!important;vertical-align:bottom!important;" -->

NOVEMBER 2023 <!-- .element style="font-family:'Montserrat'; font-size:1.3em;color:#616161;vertical-align:top;font-weight:400;" -->
</grid>

---
<!-- .slide style="font-family:'Cantarell';" -->
## Why Weighted Timed Games?<!-- .element style="font-family:'Cantarell';" -->

<br>

- want to model systems, hence Timed Automata
- want to model systems interacting with uncontrollable components, hence Timed Games

> [!note] Reachability $\leftrightarrow$ Strategy to reach a state

---
<!-- .slide style="font-family:'Cantarell';" -->

## Plan<!-- .element style="font-family:'Cantarell';" -->

<br>

1. Weighted timed automata
2. Weighted timed games
3. Main results
4. Proof sketch for bounded cost

---
<!-- .slide style="font-family:'Cantarell';" -->

## What is a Weighted Timed Automaton?<!-- .element style="font-family:'Cantarell';" -->
<br>


$\mathcal{A}=(L,X,l_{0},E,F,cost)$

$cost:L\cup E \to \mathbb{N}$


> [!important] Cost does not affect the behaviour of the automaton, only affects the... cost!

--
<!-- .slide style="font-family:'Cantarell';" -->

### Example:<!-- .element style="font-family:'Cantarell';" -->
<br>

![[Pasted image 20231121002844.png]]


---
<!-- .slide style="font-family:'Cantarell';" -->

## What is a Weighted Timed Game?<!-- .element style="font-family:'Cantarell';" -->
<br>

A game played on WTA.

Edges are partitioned into Controllable edges, played by *Controller*, and Uncontrollable edges, played by *God!*

Assume final locations are sinks, have cost 0, and have cost 0 self loops.

A *strategy* is a partial function that associates with a finite run, $(d,e)=$ (delay,edge).

--
<!-- .slide style="font-family:'Cantarell';" --><!-- .slide style="font-family:'Cantarell';" -->

- run compatible with a strategy: we stick to strategy at every move, except when God plays before we can; gives a set of plays
- winning strategy: all plays reach final
- cost of winning strategy = sup (cost of all plays)
- optimal cost = inf (cost of all winning strategies)


---
<!-- .slide style="font-family:'Cantarell';" --><!-- .slide style="font-family:'Cantarell';" -->

## The problems at hand<!-- .element style="font-family:'Cantarell';" -->

> [!example] Bounded cost problem:
> Given a threshold $c\in \mathbb{Q}$, is there a strategy with cost at most $c$?

> [!example] Optimal cost problem:
> Given a threshold $c\in \mathbb{Q}$, is the optimal cost at most $c$?

--
<!-- .slide style="font-family:'Cantarell';" -->

### Example:<!-- .element style="font-family:'Cantarell';" -->
<br>
![[Pasted image 20231121002927.png]]

note: Dashed and plain arrows
Depending on what God chooses, the cost along plays of the game is either 5t + 10(2 − t) + 1 (through 2) or 5t + (2 − t) + 7 (through 3) where t is the delay elapsed in location 0.
The optimal cost the controller can ensure is thus inf t<=2 max(5t+ 10(2−t) + 1, 5t+ (2−t) + 7) = 14 + 1/3, and the optimal time for firing transition e1 is when t = 4/3 .
The controller has an optimal strategy: wait at location 0 until x = 4/3, and enter location 1. Then, the environment chooses to go either to 2 or to 3, and finally when x reaches 2, the controller goes to the final location.

---
<!-- .slide style="font-family:'Cantarell';" --><!-- .slide style="font-family:'Cantarell';" -->

## Main results:<!-- .element style="font-family:'Cantarell';" -->

> [!bug] The bounded cost problem for WTG with $\geq 3$ clocks is undecidable.

> [!bug] The optimal cost problem for WTG with $\geq 4$ clocks is undecidable.

--
<!-- .slide style="font-family:'Cantarell';" -->

### That's a bummer! :(<!-- .element style="font-family:'Cantarell';" -->

But people have been looking for decidable subclasses of WTG. The first result in that direction is:

> [!success] The optimal cost in single-clock 'stopwatch' timed games is computable.

---
<!-- .slide style="font-family:'Cantarell';" -->

## Proof sketch for undecidability of bounded cost<!-- .element style="font-family:'Cantarell';" -->


> [!todo] Idea: Reduce halting of 2-counter automaton to existence of a strategy in a particular weighted timed game with 3 clocks.

--
<!-- .slide style="font-family:'Cantarell';" -->

### Machinery<!-- .element style="font-family:'Cantarell';" -->

![[Pasted image 20231121013117.png|1200]]
<br>

- spends 1 time unit (ensured by $z$)
- maintains clock values $(x,y)$
- increases cost by $x_{0}$, (respectively $1-x_{0}$)

--
<!-- .slide style="font-family:'Cantarell';" -->

### More machinery!<!-- .element style="font-family:'Cantarell';" -->

- can build modules to increase cost by $\langle x_{0},y_{0},1-x_{0},1-y_{0},1 \rangle$

- in particular: $c_{1}(x_{0},y_{0})=2x_{0}+(1-y_{0})+2$, $c_{2}(x_{0},y_{0})=2(1-x_{0})+y_{0}+1$

- $2x_{0}\ne y_{0} \implies c_{i}(x_{0},y_{0})>3$, $2x_{0}= y_{0} \implies c_{i}(x_{0},y_{0})=3$
- get module $\text{Test}_{z}(2x=y)$

--
<!-- .slide style="font-family:'Cantarell';" -->

### Incrementing one counter<!-- .element style="font-family:'Cantarell';" -->
<br>

- store value of counters $c,d$ in clocks $x,y$ with values $\frac{1}{2^{c}}, \frac{1}{2^{d}}$
- guess the value of $z$ non-deterministically and test if $x=2z$
- swap $x$ and $z$

--
<!-- .slide style="font-family:'Cantarell';" -->

![[Pasted image 20231121020127.png]]

- spends 1 time unit (ensured by $u$)
- maintains clock values $(x,y)$
- if $z$ is guessed incorrectly, God can ensure cost $>3$
- decrementing module can be made similarly

--
<!-- .slide style="font-family:'Cantarell';" -->

### Putting it all together!<!-- .element style="font-family:'Cantarell';" -->
<br>

Simulate the 2-counter automaton using these modules. A run either terminates in a final state of the 2-CM, or if God takes the test edge.

> [!tldr] 2-CM halts $\leftrightarrow$ Controller has a winning strategy with cost $\leq 3$

(We used 4 clocks, not 3, but we can get rid of $u$.)

---
<!-- .slide style="font-family:'Cantarell';" -->

## References<!-- .element style="font-family:'Cantarell';" -->

> [!cite] Patricia Bouyer-Decitre. Optimal Reachability in Weighted Timed Automata and Games (Invited Talk). 41st International Symposium on Mathematical Foundations of Computer Science (MFCS 2016).

> [!cite] P. BOUYER, TH. BRIHAYE, N. MARKEY, Improved Undecidability Results on Weighted Timed Automata. Information Processing Letters 98 (2006) 5, 188–194.

---
# Thank you<!-- .element style="font-family:'Cantarell';" -->

![[Pasted image 20231121022404.png|500]]