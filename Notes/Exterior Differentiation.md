202211040911

Type : #Note
Tags : [[Calc]]

---
# Exterior Differentiation

$U\subset V$ 
there are $0$-forms, $1$-forms, $2$-forms$\dots$ $l$-forms$\dots$$n$-forms
we make a function $d:l-$forms $\to (l+1)-$forms having the condition
1. $d\circ d = 0$
2. $d:0-$form $\to 1-$form
3. $d(\eta \wedge \rho) = d(\eta)\wedge \rho + (-1)^l\eta\wedge d(\rho)$

#### $d:0-$forms $\to 1-$forms
Choose a basis $e_1,e_2\dots e_n$ for $V$
get the dual basis $\phi_1, \phi_2\dots \phi_n$ for $V^*$
$$
df = \sum_{i=1}^n {\partial f \over \partial x_i}\phi_i
$$
by definition the derivative 
$$d_tf(p)[\vec u]= \lim\limits_{\epsilon \to 0} {f(p+\epsilon\vec u) - f(p)\over\epsilon}$$
To prove that both the derivatives are equivalent:
$$
\begin{aligned}
df(p)\left[\vec u = \sum u_je_j\right] &= \left\{\sum{\partial f\over\partial x_i}(p)\phi_i\right\}\left[\sum u_je_j\right]\\
&=\sum_{i,j}{\partial f\over \partial x_i}u_j\phi_i[e_j]\\
\end{aligned}
$$
Applying the function on a basis
$$
\begin{aligned}
df(p)[e_j] &= \sum_i{\partial f \over \partial x_i}(p)\phi_i[e_j]\\
&= {\partial f \over \partial x_j}(p)\\
&= \lim\limits_{t\to 0}{f(p+te_j) -f(p)\over t}\\
&=Df(p)[e_j]\\
\end{aligned}
$$
Putting it all back together
$$
\begin{aligned}
df(p)\left[\vec u = \sum u_je_j \right] &= \sum u_j\ df(p)[e_j]\\
&= \sum u_j Df(p)[e_j]\\ 
&= Df(p)[\vec u]
\end{aligned}
$$

---
# Related Problems

---
# References
