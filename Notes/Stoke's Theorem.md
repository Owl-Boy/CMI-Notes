202210141010

Type : #Note
Tags : [[Calc]]

---
# Stoke's Theorem
### Speical case of Stoke's Theorem in $\mathbb R^2$ 
Let $U\subset \mathbb R^2$ be a connected, non empty and open. A vector field on $U$ is a map $\vec v: U\to \mathbb R^2$.
We can write $\vec v(x, y) = \big(v_x(x,y), v_y(x,y)\big)$ where $v_x, v_y$ are real valued function. We will suppose that $\vec v$ is $C^1$, equivalently $v_x, v_y$ are continuous.

```ad-info
title: Vector Field as Fluids
Think of a fluid flowing in $U$, the vector field $\vec v$ can be thought of as the vecocity field for the fluid
```

```ad-note
title: Curl
$$
\nabla \times \vec v = \frac{\partial v_y}{\partial x} - \frac{\partial v_x}{\partial y}
$$
Curl can be thought of as the amount of "swirl" in the fluid or the amount of "spin" in the fluid around a point
```
```ad-note
title: Divergence
$$
\nabla \cdot \vec v = \frac{\partial v_x}{\partial x} + \frac{\partial v_y}{\partial y}
$$
Divergence can be thought of as the volume of fluid created or destroyed at a point.
```
Let $R\subset U$ be a rectangle (Represented by ABCD) then the Stoke's theorem says
$$
\begin{aligned}
\int_R\nabla\times\vec v = \int_{\vec\gamma_{AB}}\vec v\cdot d\vec\gamma_{AB}+\int_{\vec\gamma_{BC}}\vec v\cdot d\vec\gamma_{BC}+\int_{\vec\gamma_{CD}}\vec v\cdot d\vec\gamma_{CD}+\int_{\vec\gamma_{DA}}\vec v\cdot d\vec\gamma_{DA}
\end{aligned}
$$

In General, the Stokes theorem can be written as 
$$
\int_R\nabla\times\vec v = \int_{\vec\gamma_R} \vec v\cdot d\vec\gamma_R
$$
where $\int_{\vec\gamma_R}$ is a [[Line Integral]].


---
# Related Problems

---
# References
