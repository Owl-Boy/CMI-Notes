202212171912

Type : #Note
Tags : [[Analysis]]

---
# Trigonometric Functions
We define
$$
\begin{aligned}
&C(x) = \frac12[E(ix) + E(-ix)],&S(x) = \frac{1}{2i}[E(ix)-E(-ix)]
\end{aligned}
$$
where 
$$
E(z) = \sum_{n=0}^\infty \frac{z^n}{n!}
$$
Where $E(x)$ is the [[Exponential Function]].
We have
$$
\begin{aligned}
&C'(x) = -S(x), &S'(x) = C(x)
\end{aligned}
$$

There exists a positive number $x$ such that $C(x) = 0$, this is because if there does not exists an $x$ then $C(x)>0\implies S'(x)>0$ which implies $S(x)$ is monotonically increasing, since $S(0) = 0$, $S\ge 0$ , this implies $C$ is monotonically decreasing but for some $0<x<y$ we have
$$
S(x)(y-x)<\int_x^yS(t)dt=C(x)-C(y)\le 2
$$
 which is a contradiction, Hence there exists numbers such that $C$ vanishes on them. Let $x_0$ be the smallest such number, this exists as the set of zeros of continuous functions is closed, and we define $\pi$ by $$ \pi = 2x_0$$
 Thus we have
 $$
 E(\frac{\pi\iota}2) = i
 $$
 and the addition formula gives us 
 $$
 E(\pi\iota) = -1
 $$
 hence 
 $$
 E(z+2\pi\iota) = E(z)
 $$

---
# Related Problems

---
# References
 