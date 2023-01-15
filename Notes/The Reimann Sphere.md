202301111401

Type : #Note
Tags :[[Complex Analysis]]

---
# The Reimann Sphere
**Idea:** Construct an extended compelx plane with $\infty$
Let $$S=\{(x_1,x_2,x_3):x_1^2+x^2_2+x_3^2=1\}\subseteq\mathbb R^3$$
Define
$$
\begin{aligned}
\tau:S&\longrightarrow \mathbb C\\
(x_1,x_2,x_3)&\longmapsto z={x_1+ix_2\over 1-x_3}
\end{aligned}
$$
The inverse map is given by $\sigma: \mathbb C \to S$ and is called the sterographic projection
```ad-note
$$
\begin{aligned}
|z|={1+x_3\over 1-x_3}&\implies x_3={|z|^2-1\over|z|^2+1}\\
x_1={z+\overline z\over 1+|z|^2}&,x_2={z-\overline z\over 1+|z|^2}&
\end{aligned}
$$
```
Thus $\sigma:\mathbb C\longrightarrow S\setminus (0,0,1)$ is a diffeomorphism, infact it is a one point compaction.
### Alternative View Point
Let $X=\mathbb C, Y=\mathbb C$
Let $\phi:X\setminus \{0\}\to Y\setminus \{0\}$ 
$z\longmapsto \frac1z=w$ 
Define
$$
S={X\amalg Y\over x\rightsquigarrow\phi(x)}
$$
As $\phi$ is analytic, $S$ is a complex manifold.
This is equivalent to circle inversion.

---
# Related Problems

---
# References
