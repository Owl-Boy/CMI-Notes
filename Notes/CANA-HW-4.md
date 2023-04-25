Name: Rishabh Sharma 
Roll Number: BMC202144

### 1. Pg 130, Problem 5 
Suppose $f$ has an isolated singularity, if this were an essential singularity, then $f$ should come arbitrarily close to any complex value in every nbhd of the essential singularity. But this would mean that the $\mathrm{Im}(f)$ and $\mathrm{Re}(f)$ are both unbounded, so $f$ doesn't have an essential singularity.

If $f$ has a pole at say, $z_{0}$ then $\frac{1}{f}$ has a zero at $z_{0}$. So let $U$ be an open nbhd around $z_{0}$, it is mapped onto an open nbhd $V$ around $0$ by $\frac{1}{f}$ (open mapping theorem), and so $f$ maps $U$ onto an open nbhd around $\infty$. But an open nbhd around $\infty$ has $\mathrm{Im}$ and $\mathrm{Re}$ parts unbounded. That means $\mathrm{Re}(f(U))$ and $\mathrm{Im}(f(U))$ are both unbdd, which is contrary to the hypothesis.


### 2. Pg 130, Problem 6
Suppose $f(z)$ has a singularity at $z_{0}$, and let $z_{0}$ be a pole of $e ^{f(z)}$. But this implies that $e ^{u(z)+iv(z)}$ has a pole at $z_{0}$, where $f(z) = u(z) + iv(z)$.
This means that $u(z) \to \infty$ as $z \to z_{0}$. Which implies that $f(z)$ has a pole at $z_{0}$.
Now we claim that $f(z)$ having a pole at $z_{0}$ implies $e ^{f(z)}$ has an essential singularity at $z_{0}$, this will give us the desired contradiction.

Having a pole at $z_{0}$ means that given any $M > 0$, there is an $\epsilon > 0$ such that $\forall \ z \in B_{\epsilon}(z_{0})$, $|f(z)| > M$.
Now take any point $z$ in $B_{\epsilon}(z_{0})$, its image is something finite in size, but then $f(z) + 2\pi in$ forms a sequence converging to $\infty$, hence their preimages form a sequence converging to $z_{0}$, but $e ^{f(z) + 2\pi in}$ forms a constant sequence, hence we found a sequence $z_{n} \to z_{0}$ with $e ^{f(z_{n})} \to e ^{f(z)}$ for an arbitrary $z \in B_{\epsilon}(z_{0})$. Hence $z_{0}$ is neither a pole nor a removable singularity of $e^f$, it is an essential singularity.

This completes the proof.

### 3. Pg 133, Problem 3 
Let $f(z) = \cos z$, now $z_{0} = 0 \implies w_{0} = f(0) = 1$, and so $f(z) - 1$ has 0 as a root.
The derivative of this function $= f'(z) = \sin z$, this is 0 at $z = 0$. 
The second derivative $=f''(z) = -\cos z$, this is 1 at $z = 0$.
So, 0 is a zero of order 2 of the function $f(z)-1$.
This gives $\cos z-1 = z^{2}g(z) = \zeta(z)^{2}$ where $\zeta(z) = z\sqrt{g(z)}$ in some nbhd around 0.
But since we have the taylor series for $\cos z$, we can write 
$$
\zeta(z)^{2} = -\frac{1}{2!}z^{2}+\frac{1}{4}z ^{4} - \dots
$$
which gives $\zeta(z) = \sqrt{-\frac{1}{2}z^{2} + \frac{1}{4}z ^{4} - \dots}$


### 4. Pg 133, Problem 4
We know that $f(z ^{n}) - f(0)$ has all the $i$th order derivatives = 0, for all $i = 1,\dots n-1$, hence 0 is a root of order $n$ of $f(z ^{n}) - f(0)$.
Hence, $f(z ^{n}) -f(0) = z ^{n}h(z)$ where $h(0) \neq 0$.
But then we can choose a nbhd of 0 s.t. $|h(z)-h(0)| < |h(0)|$ for all $z$ in that nbhd, and so we can define a single valued analytic branch of $\sqrt[n]{h(z)}$ in this nbhd of $0$.
Thus we get: 
$$
f(z ^{n})-f(0) = \left(z \cdot \sqrt[n]{h(z)}\right)^{n}
$$
Which gives $g(z) := z \sqrt[n]{h(z)}$, and we are done.


### 5. Pg 136, Problem 1
 The equation $(36)$ states that, given a function $f$ analytic on $|z| < R$, s.t. $|f(z)| \le M, f(z_{0}) = w_{0}$, then we have 
$$
\left| \frac{M(f(z)-w_{0})}{M^{2}-\bar{w}_{0}f(z)}\right| \le \left| \frac{R(z-z_{0})}{R^{2}-\bar{z}_{0}z} \right|  
$$
Putting $R = 1$, $M = 1$, we get 
$$
\left| \frac{f(z)-w_{0}}{1-\bar{w}_{0}f(z)} \right| \le \left| \frac{z-z_{0}}{1-\bar{z}_{0}z} \right|  
$$
Now let $z \to z_{0}$, then $f(z) \to w_{0}$, which gives:
$$
\lim_{ z \to z_{0} } 
\left| \frac{f(z)-w_{0}}{(z-z_{0})(1-\bar{w}_{0}f(z))} \right| \le \lim_{ z \to z_{0} } \left| \frac{1}{1-\bar{z}_{0}z} \right|  
$$
This gives 
$$
\left| \frac{f'(z_{0})}{1-|f(z_{0})^{2}|} \right| \le \left| \frac{1}{1-|z_{0}|^{2}} \right|  
$$
But here, $z_{0}$ is any chosen point, hence 
$$
\frac{|f'(z)|}{1-|f(z)|^{2}} \le \frac{1}{1-|z|^{2}}  
$$

### 6. Pg 136, Problem 2
Consider the map $g : \mathcal{H} \to D$, where $D$ is the open unit disk and $\mathcal{H}$ is the upper half plane, given by $\displaystyle g(z) = \frac{z-z_{0}}{z-\bar{z}_{0}}$, where $z_{0} \in \mathcal{H}$ is a fixed point.
Also consider the map $h : \mathcal{H} \to D$ given by $\displaystyle h(z) = \frac{z-f(z_{0})}{z-\overline{f(z_{0})}}$
Consider the map $h \circ f \circ g ^{-1} : D \to \bar{D}$
This satisfies the conditions that the function is analytic on $D$, and $|h(f(g ^{-1}(z)))| \le 1$ for all $z \in D$. 
Also that $h(f(g ^{-1}(0))) = 0$. 
This gives $\displaystyle |h(f(g ^{-1}(z)))| \le |z| \implies |h(f(z))| \le |g(z)| \implies \frac{|f(z) - f(z_{0})|}{|f(z)-\overline{f(z_{0})}|} \le \frac{z-z_{0}}{z-\bar{z}_{0}}$.

Now take the limit as $z \to z_{0}$, which gives 
$$
\frac{|f'(z_{0})|}{\mathrm{Im}(f(z_{0}))} \le \frac{1}{\mathrm{Im}(z_{0})}
$$
Thus we are done.

### 7. Pg 136, Problem 3
In Problem 1, equality holds iff 
$$\left| \frac{f(z)-w_{0}}{1-\bar{w}_{0}f(z)} \right| = \left| \frac{z-z_{0}}{1-\bar{z}_{0}z} \right|$$
which holds iff equality holds in (36) with $M = R = 1$, which implies that $|Sf(T ^{-1}\zeta)| = |\zeta|$ where $S$ is an LFT mapping $|w| < M$ onto $|Sw| < 1$ with $Sw_{0} = 0$, and T is an LFT mapping $|z|<R$ onto $|\zeta| < 1$ with $T(z_{0}) = 0$, as in the discussion in the proof of $(36)$ in ahlfors.

This gives $SfT ^{-1}(\zeta) = c \zeta$ for some constant c. This gives $f = S ^{-1}(cT(\zeta))$ which is a composition of 3 LFTs and hence is an LFT.

In problem 2, equality holds iff $|h(f(g ^{-1}(z)))| = |z|$ which gives that $h(f(g ^{-1}(z))) = cz$ for some constant $c$, and all $z$.
This gives $f(z) = h ^{-1}(c g(z))$ which is again a composition of 3 LFTs and hence is an LFT.

### 8. Pg 148, Problem 2
Let $S$ be the simply connected space.
Let $P = S$ minus the $m$ points.
The $P ^{c} = S ^{c} + m$ points which are the $m+1$ connected components, hence $P$ has connectivity $m+1$.

The homology basis consists of $m$ loops each centered around the $m$ points. So for each of the $m$ points $\{a_{i}\}_{i=1}^m$, we can find a circle $\gamma_{i}$ around the $a_{i}$ and we will have $n(\gamma_{i}, a_{j}) = \delta_{i,j}$ hence it forms a basis.  

### 9. Pg 148, Problem 5
Suppose $S = \mathbb{R}^{2}\setminus [-1,1]$. Suppose $\Omega \subseteq S$ is the region on which we wish to define the analytic branch.
Take any closed curve $\gamma$ in $\Omega$, if it contains $\pm 1$ in its interior, then 
$$
\begin{align*}
\int _{\gamma} \frac{1}{1-z^{2}} dz &= \frac{1}{2} \int _{\gamma} \left(\frac{1}{1-z} + \frac{1}{1+z} \right) dz \\ 
&= \frac{1}{2}(-2\pi i + 2\pi i) = 0
\end{align*}
$$
And if it doesn't contain $\pm 1$ in its interior, then the integral is obviously 0 since then $\displaystyle\int _{\gamma} \frac{1}{1-z} \, dz = 0 = \int _{\gamma} \frac{1}{1+z} \, dz$.
Hence, $\frac{1}{1-z^{2}}$ is the derivative of an analytic function on $\Omega$.
The analytic function is just $\frac{1}{2}\log \left( \frac{1-z}{1+z} \right)$, and hence $e^{\frac{1}{2} \log((1-z)/(1+z))} = \sqrt{\frac{1-z}{1+z}}$ has a single valued analytic branch on $\Omega$. And therefore, multiplying by $z+1$, we get that $\sqrt{1-z^{2}}$ has a single valued analytic branch.

Now for the second part, 
If the closed curve is homologous to 0, then the integral is just 0.
If the closed curve is not homologous to 0, then it either contains $[-1,1]$ in its interior or it doesn't.
If it doesn't, then looking at it as a closed curve in $S$, it is homologous to 0 mod $S$ and hence the integral is 0.

Otherwise, it is homologous to a multiple of $|z| = 2$ mod $S$. And so, the integral is just an integer multiple of $\displaystyle\int _{|z| = 2}  \frac{dz}{\sqrt{1-z^{2}}}$.
$$
\begin{align*}
\int _{|z|=2} \frac{dz}{\sqrt{1-z^{2}}} &= \frac{1}{2}\int _{|z| =2} \left(\sqrt{\frac{1+z}{1-z}} - \sqrt{\frac{1-z}{1+z}}\right) dz \\
&=\frac{1}{2} \int _{|z| = 2} \left( -\frac{\sqrt{1-z^{2}}}{z-1} - \frac{\sqrt{1-z^{2}}}{1+z} \right) dz \\ 
\end{align*}
$$
By cauchy's formula, we have 
$$
\frac{1}{2\pi i}\int_{|z| = 2} \frac{\sqrt{1-z^{2}}}{z-1} = \sqrt{1-1^{2}} = 0 
$$
and 
$$
\frac{1}{2\pi i} \int _{{|z|=2}} \frac{\sqrt{1-z^{2}}}{1+z} = \sqrt{1-(-1)^{2}} = 0 
$$
This gives the integral  = 0.
Hence the only possible value of the integral is 0.