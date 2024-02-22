---
tags:
  - Note
  - Incomplete
---
202402210002

Tags : [[Game Theory]]
# Mixed Nash Equilibrium
---
>[!info]
>A *Mixed Nash Equilibrium* is a generalisation of [[Nash Equilibrium]] over [[Mixed Strategies]]. The idea is to talk about optimal worst case mixed strategies.

---
## Worst Case Optimal Strategies
>[!tip] Plan
>We want come up with a strategy that gives us the best [[Payoff]] in the scenario where out opponent plays the best move for them. 
>So :- 
>- We have to formalise a scenario where the opponent plays the best moves for them.
>- Compare between strategies given the above metric

For a fixed [[Payoff Matrix]] $M$ the following function capture the *worst-case* payoffs:
$$
\beta(\mathbf{x}) = \min_{\mathbf{y}}\mathbf{x}M\mathbf{y}, \quad\quad\alpha(\mathbf{y})=\max_{\mathbf{x}}\mathbf{x}M\mathbf{y} 
$$
In this case $\beta$ is the best case scenario for **BOB** (minimum payoff) and $\alpha$ is the best case scenario for **ALICE** (maximum payoff).

>[!idea] Topo sanity check
Since function if continuous, and the domain is a compact subset of $\mathbb{R}^m$ to $\mathbb{R}$, out image is compact, hence the $\min$ and $\max$ are defined, hence $\beta$ and $\alpha$ are well defined

---
## Mixed Nash Equilibrium
>[!definition]
>With the above information, we say two strategies $\tilde{\mathbf{x}}$ and $\tilde{\mathbf{y}}$ are a *Mixed Nash Equilibrium* if the worst case payoff for both the players is met simultaneously here.
>$$
>\beta(\tilde{\mathbf{x}}) = \tilde{\mathbf{x}}^T M \tilde{\mathbf{y}}=\alpha(\tilde{\mathbf{y}})
>$$
>This can also be thought of as "Both the players have the best strategy against the other player"

---
# References
[[Mixed Strategies]]
[[Minimax Theorem for Zero-Sum Games]]