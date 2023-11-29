---
tags:
  - Note
  - Incomplete
---
202311292011

Tags : [[Logic]]
# Ehrenfeucht-Fraïssé Game
---
*Ehrenfeucht-Fraïssé Games* are a nice tool to for describing expressiveness of logics over finite model.

>[!important] Setup
>There are two players, a *spoiler* and a *duplicator*. And the board consists of two structure $\mathfrak U$ and $\mathfrak B$. The goal of the *spoiler* is to show that the two structures are different, and the goal of the *duplicator* is to show that the two structures are the same.
>

## Gameplay
In the classic *Ehrenfeucht-Fraïssé Game*, the players play a certain number of rounds, and each round consists of the following steps.
1. *Spoiler* picks a structure.
2. Then *spoiler* makes a move by picking a point in the structure.
3. the *duplicator* responds to the move by picking a point in the other structure.

An example game is given in [[Even is not FO-definable]].

## Winning
After $n$ rounds of an *Ehrenfeucht-Fraïssé Game*, we have the move $\vec{a}=(a_{1},a_{2}\dots a_{n})$ and $\vec{b}=(b_{1},b_{2}\dots b_{n})$. And let $c_{1},c_{2}\dots c_{k}$ be the set of constants in the language.
We define $\vec{c^\mathfrak U}=c^{\mathfrak U}_{1}\dots c^\mathfrak U_{k}$ and $\vec{c^\mathfrak B}=c^\mathfrak B_{1}\dots c^\mathfrak B_{k}$ is the interpretation of the constants in the two structures $\mathfrak B$ and $\mathfrak U$.

With that machinery, we say that the *spoiler* failed to show that the two structures if $((\vec{a}, \vec{c^\mathfrak U}), (\vec{b},\vec{c^\mathfrak B}))$ is a [[Partial Isomorphism]].

And we say $\mathfrak U \equiv_n \mathfrak B$ if *duplicator* has a winning strategy in an $n$ round game.

---
The Application of *Ehrenfeucht-Fraïssé Games* is given by the [[Ehrenfeucht-Fraïssé Theorem]] which links it to first order logic

---
# References
- [[Even is not FO-definable]]
- [[Quantifier rank]]
- [[Ehrenfeucht-Fraïssé Theorem]]