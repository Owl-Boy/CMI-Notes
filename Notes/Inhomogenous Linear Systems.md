202303111803

Type : #Note
Tags :[[Differential Equations]]

---
# Inhomogenous Linear Systems
```ad-note
title:
Given the IVP 
$$
\dot{\bar{x}}(t) = A(t)x(t) + b(t)
$$
with $x(t_{0}) = x_{0}$.
The set of all solutions is given by $\{ c_{1}\varphi_{1} + c_{2}\varphi_{2} + \dots + c_{n} \varphi_{n} + \varphi_{b}\mid c_{1},c_{2},\dots c_{n} \in \mathbb{R} \}$, where $\varphi_{1}, \varphi_{2},\dots \varphi_{n}$ is a basis for $\ker T_{A}$ and $\varphi_{b}$ is one specific solution to the given IVP.

For the definition of $T_A$, look at [[Homogenous Linear Systems]].
```

### How do we find a specific solution ($\varphi_{b}$) to this IVP given a basis for $\ker T_{A}$?
```ad-info
title: Idea
Allow coefficients of $\varphi_1, \varphi_2, \dots, \varphi_n$ to be functions $c_1(t),c_2(t),\dots, c_n(t)$, i.e., $$\varphi := c_1(t)\varphi_1(t) + \dots + c_n(t)\varphi_n(t)$$
where $c_i : I \to \mathbb{R}$.
```

This gives $$
\begin{align}
\dot{\varphi} &= (c_{1}(t)\dot{\varphi_{1}}(t) + c_{2}(t)\dot{\varphi_{2}}(t) + \dots + c_{n}(t)\dot{\varphi_{n}}(t)) + (\dot{c_{1}}(t)\varphi_{1}(t) + \dot{c_{2}}(t)\varphi_{2}(t) + \dots + \dot{c_{n}}(t)\varphi_{n}(t)) \\
&= (c_{1}(t) A(t)\varphi_{1}(t) + c_{2}(t) A(t) \varphi_{2}(t) + \dots + c_{n}(t) A(t) \varphi_{n}(t)) + (\dot{c_{1}}\varphi_{1} + \dots + \dot{c_{n}}\varphi_{n})\\
&= A(t)\varphi(t) + (\dot{c_{1}}\varphi_{1} + \dots + \dot{c_{n}}\varphi_{n})
\end{align} 
$$
Therefore it suffices to find $c_{1},\dots ,c_{n}$ satisfying $\dot{c_{1}}\varphi_{1} + \dots + \dot{c_{n}}\varphi_{n} = b$.
Writing this as a matrix equation, we get:
$$
\begin{bmatrix}
\varphi_{1} \ \varphi_{2} \ \dots \ \varphi_{n}
\end{bmatrix}_{n\times n}
\begin{bmatrix}
\dot{c_{1}} \\ 
\dot{c_{2}}\\
\vdots \\
\dot{c_{n}}
\end{bmatrix}_{n\times 1}
 = 
 \begin{bmatrix}
b(t)
\end{bmatrix}_{n\times_{1}}
$$
Thus 
$$
\begin{bmatrix}
\dot{c_{1}} \\
\dot{c_{2}}  \\
\vdots \\
\dot{c_{n}}
\end{bmatrix}
 = 
 \begin{bmatrix}
\varphi_{1} & \varphi_{2} & \dots & \varphi_{n}
\end{bmatrix}^{-1}
\begin{bmatrix}
b(t)
\end{bmatrix}
$$
Hence $$
\begin{bmatrix}
c_{1} \\
c_{2} \\
\vdots  \\
c_{n}
\end{bmatrix}
 = \int \begin{bmatrix}
\varphi_{1} & \varphi_{2} & \dots & \varphi_{n}
\end{bmatrix}^{-1} 
\begin{bmatrix}
b(t)
\end{bmatrix}\, dt 
$$
So we are done.

---
# Related Problems
1. How to find the $\varphi_{1}, \varphi_{2},\dots,\varphi_{n}$? We do this in [[Linear systems with constant coefficients]], for the special case of linear systems with constant coefficients.

---
# References
[[Homogenous Linear Systems]]