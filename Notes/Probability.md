---
tags:
  - Note
---
202409222109

Tags : [[Probability Theory]]
# Probability
---
A *Probability* is a special case of a measure such that $\mu(\Omega)=1$ as discussed in [[Special Types of Measures#^9add70]]. It is customary to denote probability measures by $P$ instead of $\mu$.

Measurable functions from probability spaces are called *Random Variables* and will usually be denoted by the variables $X,Y,Z$. When $X$  is integrable then we say that $\int X \, dP= E_{P}(X)$ and is called the expectation of $X$ under $P$. Sometimes it is simplified to $E(X)$ if it is clear from the context.

A random variables $X$ induces the measure $\mu$ on $(\mathbb{R}, \mathcal B)$ where $\mu(B)=P(X^{-1}(B))$ then we get
$$
E(X)=\int _{\Omega}X \, dP = \int _{R}xd \, d\mu
$$
The distribution function of $\mu$ is called the *distribution function of the random variable* $X$. So 
$$
E(f(X)) = \int f(X) \, dP = \int f(x) \, d\mu  
$$

---
# References
[[Joint Distribution Measure and Product of Probability]]