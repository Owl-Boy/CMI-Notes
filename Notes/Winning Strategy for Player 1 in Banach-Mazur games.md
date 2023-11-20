---
tags:
  - Note
  - Incomplete
---
202311172311

Tags : [[Topology]]
# Winning Strategy for Player 1 in Banach-Mazur games
---
>[!info]
>Given that there exists a winning strategy for player 2 in certain conditions, If the *'opposite'* conditions are met, then player 1 can steal her strategy.

The idea for player 1 here is to make sure that intersection of $W'$ with the compliment of $X$ is empty. So if $W'$ is not empty itself, then it will intersect with $X$.
To ensure this condition we make the space $Y$ a *complete metric space*. Then every decreasing nested sequence of sets in $\mathcal W$ will give a corresponding decreasing nested sequence of compact sets.

>[!hint] Winning Condition
>If $Y$ is a metric space, then there exists a winning strategy for player 1 iff the set $X$ is *large* in some open set of $Y$

^305cd2

If $X$ is large in an open set $O$. Player 1 picks $W_i$ inside $O$.
Now she will pretend to be the second player of the game that starts after this step, i.e of the game $MB(X', W_1, \mathcal W)$ where $X' =X^c\cap W_1$

Here $X^c\cap W_{1}$ is *meager*. This means that player 1 can use [[Winning Strategy for Player 2 in Banach-Mazur games]] by slightly modifying it to produce the following sequence of sets 
$$
W_{1}, W_{2}\dots
$$
and $W'\cap X'=\emptyset$. So $W'\cap X = W'$
But we have that $Y$ is a complete metric space so for each $W_{2i}$ find an open set $O$ in it which contains $W_{2i+1}$.  
The modification we use above is that instead finding $W_{2i+1}$ in $O$, we find an open set $O'\in O$ such that $\overline{O'}\subseteq O$.
This ensure that if we take the odd terms in the above sequence, the give a corresponding decreasing nested sequence of compact sets $\overline{O'}$ for each $W_i$. 
Intersection of all of those compact sets is non empty because of the [[Cantor's Intersection Theorem]] Hence Intersection of all $W_i\ne\emptyset$.

Thus $W'\cap X$ is nonempty.

---
# References
[[Winning Strategy for Player 2 in Banach-Mazur games]]
[[Banach-Mazur Games]]