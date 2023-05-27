# Cana Assignment 4
Name: Shubh Sharma
Roll Number: BMC202170

### 1. PG 130, Problem 5
 
If $f$ has an essential singularity, it would come arbitrarily close to every point, then $f$ is would not be bounded, hence $f$ does not have an essential singularity.

Let $z_0$ be a pole of $f$, then by the open mapping theorem, an open set around $z_0$ would be mapped to an open neighbourhood of $\infty$, which would mean, either the $Re$ or the $Im$ parts are unbounded, Hence $f$ does not have a pole either.

Hence an isolated singularity of $f(z)$ is removable.

### 2. PG 130, Problem 6

If $e^{f(z)}$ has a pole at $z_{0}$ then the real part of $f(z)$ goes to $\infty$ as $z$ goes to $z_{0}$. Hence $f(z)$ would also have a pole at $z_0$.

Having a pole at $z_{0}$ implies, given any $M>0,\;\exists\epsilon>0$ Such that $z\in B_{\epsilon}(z_{0})\implies |f(z_{0})|>M$.
Pick $z\in B_\epsilon(z_{0})\ne z_{0}$, its image is finite and the sequence $f(z)+2n\pi i$ converges to $\infty$., take the inverse images of each of the points of the sequence. which form a sequence $z_{n}\to z_{0}$. $e^{f(z_{n})}$ is a constant sequence which is finite, hence $z_{0}$ is not a pole of $e^{f(z)}$ which is a contradiction.


### 3. PG 133, Problem 3

Let $f(z)= \cos z$ and let $z_{0}=0$, $f(z)-1$ has a root at $z_{0}$ 
The derivative of $f'(0)=\sin 0=0$, 
second derivative is $-\cos 0=-1$. Hence the root has degree $2$.
Hence $\cos z -1 = z^{2}g(z)=\zeta^{2}(z)$ , hence $\zeta(z) = z\sqrt {g(z)}$ and we get
$$
\begin{align*}
f(z)-1 &= \cos z -1\\
&= -2\sin^{2}\left(\frac{z}{2}\right)\\
&= \zeta^{2}(z)\\
\therefore \zeta(z) &= \sqrt 2 i \sin\left(\frac{z}{2}\right)
\end{align*}
$$

### 4. PG 133, Problem 4

$f(z^{n})-f(0)$ has all $i$ order derivatives for $i\in\{1\dots n-1\}$ and $0$ is a root 
hence $f(z^n)-f(0)=z^{n}h(z)$ where $h(0)\ne 0$
Hence we can choose a neighborhood of $0$ such that $|h(z)-h(0)|\le|h(0)|$ for all $z$ in the neighborhood, so we can define a single valued branch of $\sqrt[n]{h(z)}$ in the neighbourhood of $0$
$$
f(z^{n})-f(0) = \left(z\sqrt[n]{h(z)}\right)^n
$$
and have $g(z)=z\sqrt[n]{h(z)}$ 

### 5. PG 136, Problem 1

The equation $36$ in ahlfors states that, given a function $f$ analytic on $|z|< R$, such taht $|f(z)|<M,f(z_0)=w_0$, then we have 
$$
\left |
    \frac
    {M(f(z)-w_0)}
    {M^{2}-\bar w_{0}f(z)}
\right|
\le
\left |
    \frac
    {R(z-z_{0})}
    {R^{2}-\bar z_{0}z}
\right|
$$
putting $R=M=1$ we get
$$
\left |
    \frac
        {f(z)-w_{0}}
        {1-\bar w_{0}f(z)}
\right|
\le
\left |
    \frac
        {z-z_{0}}
        {1-\bar z_{0}z}
\right|
$$
as $z\to z_0$ we have $f(z)\to w_{0}$ 
$$
\left |
    \frac
	    {f'(z_{0})}
	    {1-|f^{2}(z_{0})}
\right|
\le
\left |
	\frac
		{1}
		{1-|z_{0}|^{2}}
\right|
$$
but $z_0$ can be any point
$$
\left |
    \frac
	    {f'(z)}
	    {1-|f^{2}(z)}
\right|
\le
\left |
	\frac
		{1}
		{1-|z|^{2}}
\right|
$$
### 6. PG 136, Problem 2

Consider the map $g:\mathcal H\to\mathcal D$, where $\mathcal D$ is an open unit disk and $\mathcal H$ is the upper half plane, given by $g(z)= \frac{z-z_{0}}{z-\bar{z_{0}}}$, where $z_0\in\mathcal H$ is a fixed point.
Consider the map $h(z)= \frac{z-f(z_{0})}{z-\overline{f(z_{0})}}$ 

And consider the map $h\circ f \circ g^{-1}: \mathcal D\to \bar{\mathcal D}$ 
This satisfies the conditions that the function is analytic on $\mathcal D$, and $|h(f(g^{-1}(z)))|\le 1$ for all $z\in \mathcal D$ 
also $h(f(g^{-1}(0)))=0$.

This gives $|h(f(g^{-1}(z)))|\le|z|\implies |h(f(z))|\le |g(z)|\implies \left| \frac{f(z)-f(z_{0})}{f(z)-\overline{f(z_{0})}} \right|\le \frac{z-z_{0}}{z-\bar{z}_{0}}$ 
taking $z\to z_{0}$ we get
$$
\frac{|f'(z_{0})|}{Im(f(z_{0}))}\le \frac{1}{Im(z_{0})}
$$

### 7. PG 136, Problem 3

In [[Cana Assignment 4#5. PG 136, Problem 1|problem 5]], equality holds iff
$$
\left|
    \frac
        {f(z)-w_{0}}
        {1-\overline w_{0}f(z)}
\right|
=
\left| 
    \frac
        {z-z_{0}}
        {1-\overline z_{0}z}
\right|
$$
which holds iff equality holds in $(36)$ with $M=R=1$ hence $|Sf(T^{-1}\zeta)|=|\zeta|$ where $S$ adn $T$ are linear fractional transformations.

This gives $SfT^{-1}(\zeta)=c\zeta$ for some $c$. This gives $f=S^{-1}(cT(\zeta))$ which is a compostition of $3$ linear fractional transformationsm, and hence is a Linear fractional transformation.

In [[Cana Assignment 4#6. PG 136, Problem 2|Problem 6]], equality holds iff $|h(f(g^{-1}(z)))|=|z|$ which gives $h(f(g^{-1}(z)))=cz$ for some constant $c$. That gives $f$ as $f(z)=h^{-1}(cg(z))$ which is also a linear fractional transformation.

### 8. PG 148, Problem 2

Let $S$ be a simply connected space.
Let $P=S\setminus M$ where $M$ is a set with $m$ points
The $P^{c}= S^{C}\cup M$ points which are $m+1$ connected components, hence $p$ has connectivity  $m+1$

The homology basis consists of $m$ loops each centered around the $m$ points. So for each of the $m$ points, we can find a circle $\gamma_{i}$ around the points $a_{i}\in M$  and we will have $n(\gamma_{i}, a_{j})= \delta_{i, j}$ which forms a basis

### 9. PG 148, Problem 5
Any closed curve $\gamma$ in the domain $\Omega$ that winds around $1$ also winds around $-1$. consider some point $z_{0}\in\gamma$ and choose some value of $\theta_{1}=arg(1-z)$ such that $(1-z_{0})=r_{1} e^{i\theta_{1}}$ . and take a branch of $\sqrt{1-z_{0}}$.
Now as we travel around $\gamma$, as we come back to $z_0$ we add $2\pi$ to the argument of $(1-z)$ . The same works for the argument of $(1+z)$ and so the argument of the product changes by $4\pi$. Now when we take the square root, we divide the argument by $2$ which means that as we move around $\gamma$  and come back to $z_0$, the argument of $\sqrt {1-z^{2}}$ changes by $2\pi$.

Now we compute 
$$
\int_\gamma\frac{1}{\sqrt{1-z^{2}}}dz.
$$
And by Cauchy's Theorem, we can assume $\gamma$ is a very large cirle and so acts as a small disc about infinity. we apply the change of variables $z=\frac{1}{w}$ and we get the integral
$$
-\int_{|w|=\delta} \frac{dw}{w\sqrt{w^{2}-1}} 
$$
$\sqrt{w^{2}-1}$ is analytic in a neighbourhood of $0$ so we can compute the integral by cauchy's formula to be $2\pi$
 
 