202303111603

Type : #Note
Tags : [[Differential Equations]]

---
# Homogenous Linear Systems
```ad-note
title:
A homogenous Linear system is of the form 
$$\dot{\bar{x}}(t) = A(t)x(t)$$
Where $A : I \to M_n(\mathbb{R})$
```
## How do we find its solutions?
Assume henceforth that $A(t)$ is continuous.

Consider $$T_{A} : C^{1}(I,\mathbb{R}^{n}) \to C^{0}(I,\mathbb{R}^{n})$$$$f \mapsto \frac{ df }{ dt } - A(t)f(t)$$
### Claim 1: $T_{A}$ is a linear map.
### Claim 2: The map $T_{A}$ is surjective. 
##### Proof: 
Let $g \in C^{0}(I,\mathbb{R}^{n})$. Then $g \in Im(T_{A})$ if there exists $\varphi \in C^{1}(I,\mathbb{R}^{n})$ s.t. 
$$\frac{ d\varphi }{ dt } - A(t)\varphi(t) = g(t)$$
This is true by [[Existence and uniqueness for linear systems]].

### Claim 3: $\dim (\ker T_{A}) = n$.
##### Proof:
Fix $t_{0} \in I$, let $\varepsilon_{t_{0}} : \ker T_{A} \to \mathbb{R}^{n}$
$$\varphi \mapsto \varphi(t_{0})$$
Then $\varepsilon_{t_{0}}$ is linear. 
Suppose $\varphi(t_{0}) = 0$ for some $\varphi$. Then $\varphi$ is a solution of $$
\dot{x} = Ax;  \ \ x(t_{0}) = 0
$$
By uniqueness of solution, $\varphi(t) = 0 \ \forall t \in I$ as $\varphi \equiv 0$ is a solution.

Thus $\varepsilon_{t_{0}}$ is an injective linear map.

Now for any $x_{0} \in \mathbb{R}^{n}$, we need to find a $\varphi \in \ker T_{A}$ such that $\varphi(t_{0}) = x_{0}$
But this is a consequence of [[Existence and uniqueness for linear systems]].
Thus $\varepsilon_{t_{0}}$ is an isomorphism, hence we are done.

Let $\varphi_{1}, \varphi_{2} \dots \varphi_{n}$ be a basis of $\ker T_{A}$, then any element of $\ker T_{A}$ can be written as a linear combination of these.

---
# Related Problems
[[Inhomogenous Linear Systems]]

---
# References
[[Existence and uniqueness for linear systems]]
