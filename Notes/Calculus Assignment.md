- # Question 1
- If $|x - y| < \delta$ such that $x,y \in [1,\infty)$
- $$\begin{aligned}
  |\log(x) - \log(y)| &= \left|\log\left(\frac{x}y\right)\right|\\
  &\le \left|\log\left(\frac{y+\delta}y\right)\right|\\
  &\le \left|\log\left(1+\frac{\delta}{y}\right)\right|\\
  &\le \left|\frac\delta{y}\right|\\
   &\le \delta
  \end{aligned}$$
- Therefore, $\forall \epsilon>0, \exists \delta=\epsilon$ such that $|x-y|<\delta \implies |\log(x)-\log(y)| < \epsilon$
- Hence $\log$ is uniformly continuous in $[1,\infty)$
- ---
- # Question 2
- If $\phi$ is a continuous function and $f$is Riemann integrable, then $\phi\circ f$ is Riemann integrable
- let $g(x)= x^2,\ g$ is continuous
- then $g\circ f_r + g\circ f_i$ is riemann integrable
- let $h(x)=\sqrt{x}$ which is continuous
- hence, $\sqrt{f_r^2+f_i^2}$ is Riemann integrable
- let $f$ be a Riemann integrable complex function, $c=\alpha+\iota\beta$
- $$
  \begin{aligned}
  c\int\limits_a^b f(x)dx &=(\alpha+\iota\beta)\left(\int\limits_a^bf_r(x)dx+\iota\int\limits_a^bf_i(x)dx\right)\\
  &=\left(\alpha\int\limits_a^bf_r(x)dx-\beta\int\limits_a^bf_i(x)dx\right) +\iota\left(\alpha\int\limits_a^b f_r(x)dx-\beta\int\limits_a^b f_i(x)dx\right)\\
  &=\int\limits_a^bcg(x)dx
  \end{aligned}
  $$
- Let $z=\int\limits_0^1f(x)dx$. Define $O=\frac{z}{|z|}$
- $$
  \begin{aligned}
  \left|\int\limits_0^1f(x)dx\right| = |z| &= O\int\limits_0^1f(x)dx\\
  &= \int\limits_0^1Of(x)dx\\
  &= \int\limits_0^1Re(Of(x))dx + \iota\int\limits_0^1Im(Of(x))dx
  \end{aligned}
  $$
- As LHS is a real number,
- $\left|\int\limits_0^1f(x)dx\right| = \left|\int\limits_0^1Re(Of(x))dx\right| \le \int\limits_0^1\left|Of(x)\right|dx = \int\limits_0^1|O||f(x)|dx$
- Therefore $|\int_0^1f(x)dx| \le \int_0^1|f(x)|dx$
- ---
- # Question 3
	- ### a)
		- $\frac1p+\frac1q =1$
		- let $f(u) = \frac{u^p}p+\frac{v^q}q -uv$
		- $f'(u) = u^{p-1} - v$
		- $u^{p-1} = v$ for critical points
		- $f''(u) = (p-1)u^{p-2} = (p-1)\frac{v}u$
		- $\frac1p <1 \implies p > 1\implies f''(u) > 0$
		- hence $u_0^{p-1} = v, u_0$ is a minimum
		- $$
		  \begin{aligned}
		  \frac{u^p}p+\frac{v^q}q -uv &\ge \frac{u_0^p}p + \frac{u_0^{(p-1)q}}q - u_0^p\\
		  &\ge \frac{u_0^p}p+\frac{u_0^p}q - u_0^p\\
		  &\ge 0
		  \end{aligned}
		  $$
	- ### b)
		- $u=\frac{f(x)}{(\int_0^1f^p(x))^{\frac1p}}, v=\frac{g(x)}{(\int_0^1g^q(x))^{\frac1q}}$
		- applying part a
		- $$\begin{aligned}
		  \frac{fg}{(\int_0^1f^pdx)^{\frac1q}(\int_0^1g^qdx)^{\frac1q}} &\le \frac1p\left(\frac{f}{\left(\int_0^1f^pdx\right)^{\frac1p}}\right)^p + \frac1q\left(\frac{g}{\left(\int_0^1g^qdx\right)^{\frac1q}}\right)^q\\
		  &\le \frac1p\frac{f^p}{\int_0^1f^pdc}+ \frac1q\frac{g^q}{\int_0^1g^qdc}
		  \end{aligned}$$
		- Integrating on both sides from $0$ to $1$
		- $$\frac{\int_0^1fgdx}{(\int_0^1f^pdx)^{\frac1q}(\int_0^1g^qdx)^{\frac1q}}\le\frac1p+\frac1q=1$$
		- therfore $$\int_0^1fgdx \le \left(\int_0^1f^pdx\right)^\frac1p + \left(\int_0^1g^qdx\right)^\frac1q$$
	- ### c)
		- as proved in problem 2
		- $|\int_0^1fgdx| \le \int_0^1|fg|dx = \int_0^1|f||g|dx$
		- taking $|f|$ and $|g|$ be function for path (b)
		- $|\int_0^1fgdx| \le (\int_0^1|f|^p)^\frac1q + (\int_0^1|g|^q)^\frac1q$
- ---
- # Question 4
- ### a)
	- $S$ is not Jordan Measurable
	- Consider a partition $P_1\times P_2 = P$
	- Since $S$ is dense in $I^2,\ L(P, \chi_S) = 0,\ U(P, \chi_S)=1$ for any partition $P$
	- $\inf L(P, \chi_S)  = 0$
	- $\sup U(P, \chi_S) = 1$
	- hence $X_S$ is not Integrable
- ### b)
	- Since no open balls can be made around any point in $S$ which are a subset of $S$, $S^o = \emptyset$
	- $\overline{S} = I^2$
	- $\delta S = \overline{S}\setminus S^o = I^2$
	- $I^2$ is a closed and bounded subset of $\mathbb{R}^2$, hence $I^2$ is compact
	- Since $I^2$ is compact, there exits an open cover with finite subcover $\{R_n}
	- $I^2\sub \bigcup\limits_{1\le i\le n} R_i$
	- $Area(I^2) \le Area\left(\bigcup\limits_{1\le i \le n} R_i\right)$
	- Therefore area of any union of sets that make a cover of $I^2$, hence The jordan measure of $\delta S$ is non zero
- ---
- # Question 5
- ### a)
	- $\delta S = \left\{\left(\frac1n, y\right)|n\in \mathbb{N}, y\in I\right\}$
	- The set $\left(\frac1n, y\right)$ for a particulat $n$ can be covered  by the rectangle $I\times \left[\frac1n-\frac\epsilon3,\frac1n+\frac\epsilon3\right]$
	- The area of the cover of the set is $\frac{2\epsilon}3<\epsilon$, hence the has measure $0$
	- countable union of zero measure sets has measure $0$, hence $\delta S$ has measure 0, hence $S$ is Integrable
- ### b)
	- $Area(S) = Area(I^2) - \sum\limits_{i=1}^\infty Area\left(\left[\frac1n+\frac{\epsilon}{2\cdot2^i},\frac1n- \frac{\epsilon}{2\cdot2^i} \right]\right)$
	- $Area(S) = 1 - \epsilon$
	- $Area(S) = 1$
- ---
- # Question 6
- Since $f$ is continuous, it is integrable in a closed interval, let $\eta$ be the closed figure which is the union of $\Gamma_f$, and the area enclosed in the curve.
- since $f$ is integrable, we know that $\chi_\eta$ is integrable $\implies\Gamma_f$ has content $0$, as it is a subset of the boundary of $\eta$
- If $f$ is only integrable, the above argument still holds as the only Information used in the above proof is that $f$ is integrable.
  ---
- # Question 7
- $\int_\mathbb{R}\tilde{D} = \int_ID$
- $$
  \begin{aligned}
  \int\limits_0^1 (1-x) dx &= x - \frac{x^2}2 |_{[0, 1]}\\
  &= \frac12
  \end{aligned}
  $$
- Using Fubini's theorem
- $$\begin{aligned}
  \int_{I\times I} D(x)D(xy) dx dy &= \int_{I\times I} (1-x)(1-xy)dxdy\\
  &= \int_0^1(\int_0^1 (1-x)(1-y)dy)dx\\
  &= \int_0^1(1-x)*(1-\frac{x}2)dx\\
  &= \frac52
  \end{aligned}$$
  ---