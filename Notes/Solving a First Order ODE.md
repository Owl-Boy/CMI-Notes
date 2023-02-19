202301041201

Type : #Note
Tags :[[Differential Equations]]

---
# Solving a First Order ODE
### Homogenous 1st order Linear ODE
$$
\begin{aligned}
a(x)y' + b(x)y &= 0\\
y' &= -\frac{a(x)}{b(x)}y\\
y' &= -p(x)y\\
\frac{dy}y&=-\int p(x)dx \implies \ln|y| = -\int p(x)dx + C\\
&\implies |y|=\kappa e^{P(x)}\\
\text{where } &P(x) = \int p(x)dx
\end{aligned}
$$
### Inhomogenous 1st order Linear ODE
$$
\begin{aligned}
y'&=-y\cdot p(x) - q(x)\\
\frac d{dx}(ye^{P(x)}) &= e^{P(x)}(y'+y\cdot p(x))\\
&=-e^{P(x)}q(x)\\
\therefore ye^{P(x)}&= c'-\int\limits_{i_0}^xq(t)e^{P(t)}dt\\
y&= e^{-P(X)}\left(c'-\int\limits_{i_0}^xq(t)e^{P(t)}dt\right)
\end{aligned}
$$
### Non Linear(Variable Separable) ODE
$$
\begin{aligned}
y'&=f(x, y)\\
y'&=h(x)\cdot g(y)&(g,h \text{ are continuous, $h$ is non vanishing})\\
\end{aligned}
$$

---
# Related Problems

---
# References
[[Solution of a differential equation]]