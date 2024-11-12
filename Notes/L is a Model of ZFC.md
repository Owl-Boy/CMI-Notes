---
tags:
  - Note
  - Incomplete
---
202411102111

Tags : [[Set Theory]]
# L is a Model of ZFC
---
The proof proceeds by well ordering of $\mathbf{L}$ which is done by well ordering all formulas:

>[!definition] Well order
>By recursion on $\alpha$ we define the well order $\triangleleft_{\alpha}=\triangleleft(\alpha)$ of $L(\alpha)$ as follows.
>- $\triangleleft_{0}=0$
>- If $\alpha$ is a limit ordinal, then to compare 2 elements
>	- If their rank is unequal, let the one with smaller rank be smaller.
>	- If both their ranks are $\xi$, compare them with $\triangleleft_{\xi+1}$
>	1. This also induces a lexicographical ordering $\triangleleft_{\alpha}^n$ on $L(\alpha)^n$
>- For a successor ordinal $\alpha+1$, for $X\in L(\alpha+1)$
>	1. Let $n$ be the smallest number such that $X$ can be written using a formula of $N$ variables from sets in $L(\alpha)$
>	2. $s$ be the least set in $\text{Df}(L(\alpha), n+1)$ that can be used to construct $X$ according to $\triangleleft_{\alpha}^n$.
>	3. $m$ be the least number when enumerating formulas on $L(alpha)$ on $n$ variables as defined in [[Definable Formulas are Countable]].
>	- $X\triangleleft_{\alpha+1} Y$ iff
>		- $X, Y \in L(\alpha) \land X \triangleleft_{\alpha} Y$
>		- $X\in L(\alpha) \land Y\not\in L(\alpha)$
>		- $X, Y\not\in L(\alpha)$ then we use the lexicographical order defined above.

We can use this ordering, to well order all of $\mathbf{L}$ and hence we get the following:
>[!theorem] $\mathbf{V}=\mathbf{L}\to \text{AC}$



---
# References
