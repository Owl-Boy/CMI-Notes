---
tags:
  - Note
---
202409192109

Tags : [[Measure Theory]]
# Some Useful Inequalities
---
- *Chebyshev's Inequality*
	- If $X \in L^1(\mu_{1})$ and $a \geq 0$ then $\mu(|X| \geq a) \leq \frac{\int |X| d \mu}{a}$.
- *Cauchy Schwarz Inequality*
	- For non-negative $X$ and $Y$, 
	- $\int |XY| \, d\mu \leq \sqrt{ \int |X| \, d\mu }\sqrt{ \int |Y| \, d\mu }$
- *Holder's Inequality*
	- For non-negative $X$ and $Y$
	- For $p,q>1$ such that $\frac{1}{p}+\frac{1}{q}=1$
	- $\int XY \, d\mu \leq \sqrt[p]{ \int X^p \, d\mu }\sqrt[q]{\int Y^q \, d\mu  }$
- *Minkowski's Inequality*
	- If $X$ and $Y$ are non-negative functions, and if $p\geq 1$ is a number.
	- Then $\sqrt[p]{\int (X+Y)^p \, d\mu  }\leq \sqrt[p]{ \int X^p \, d\mu }+\sqrt[p]{\int Y^p \, d\mu  }$
- *Chebyshev's Inequality*
	- Let $\mu$ be a probability measure
	- If $X \in L^2$ and $\int X \, d\mu = \theta$ and $\int (X-\theta) \, d\mu = \sigma$
	- For all $a> 0$ we have
	- $P(|X-\theta| >a)\leq \frac{\sigma^2}{a^2}$
- *Jensen's Inequality*
	- $X$ be an integrable function taking values in $(a, b)$
	- $\varphi$ is convex on the interval $(a, b)$ 
	- $\varphi\circ X$ is also integrable
	- $\varphi\left( \int X \, d\mu \right) \leq \int \varphi\circ X \, d\mu$

---
# References
