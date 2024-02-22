---
tags:
  - Note
---
202402202302

Tags : [[Game Theory]]
# Mixed Strategies
---
>[!info]
>A *Mixed Strategy* is a generalisation of a [[Strategy]] that help talk about strategies in games like Rock-Paper-Scissors, i.e games where we might want to talk about probabilities over multiple strategies

>[!definition]
>A *Mixed Strategy* of a player is a [[Probability Distribution]] over their set of [[Pure Strategies]]. It is encoded as an $m$ dimensional vector for a player that has $m$ choices of moves.

---
## Expected Payoff of Mixed Strategies
Given two mixed strategies $\tilde{x}$ and $\tilde{y}$. The *expected payoff* given the [[Payoff Matrix]] $M$ is
$$
\begin{align}
&\sum_{i,j}m_{ij}\cdot\mathbf{Prob}\langle \text{Alice plays $i$ and Bob plays $j$}\rangle\\
= &\sum_{i,j}m_{ij}\cdot \mathbf{Prob}\langle \text{Alice playes $i$}\rangle\cdot  \mathbf{Prob}\langle\text{Bob plays $j$}\rangle\\
= &\sum_{i,j}m_{ij}\cdot x_{i}\cdot y_{j}\\
= &x^TMy
\end{align}
$$

---
## Why tho
The [[Minimax Theorem for Zero-Sum Games]].

This theorem gives us a way to find optimal strategies for both players for any $0$ sum game.

---
# References
[[Mixed Nash Equilibrium]]