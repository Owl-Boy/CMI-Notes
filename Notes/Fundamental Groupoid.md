202304031604

Type : #Note
Tags : [[Topology]]

---
# Fundamental Groupoid
```ad-note
title:
If $f$ is a path in $X$ from $x$ to $y$ and $g$ is a path from $y$ to $z$, then $f * g$ is defined as a path from $x$ to $z$ with concatenates $f,g$.
$$
(f*g)(s) = \begin{cases}
f(2s) \ 0 \le t \le \frac{1}{2} \\
g(2s-1) \ \frac{1}{2} \le t \le 1
\end{cases}
$$
```
##### This also gives a binary operation on the set of path-homotopy classes as well, as long as $f(1) = g(0)$.
If $f \simeq_{p} f'$ and $g \simeq_{p} g'$ with homotopies $F(s,t)$ and $G(s,t)$ then $f*g \simeq_{p} f'*g'$ using $$
(F*G)(s,t) = \begin{cases}
F(s,2t), \ 0 \le t\le \frac{1}{2}  \\
G(s,2t-1), \ \frac{1}{2} \le t\le 1
\end{cases}
$$
So we can define $[f] *[g] = [f*g]$

##### The operation $*$ is associative on path-homotopy classes, and has identity and inverses.
- Associative:
Let $f,g,h$ be three paths with $f(1) = g(0)$ and $g(1) = h(0)$. We claim $(f*g)*h \simeq_{p} f*(g*h)$.
$$
F(s,t) = \begin{cases}
f\left( \frac{4s}{1+t} \right), \ 0 \le s \le \frac{t+1}{4} \\
g(4s-(1+t)), \ \frac{t+1}{4} \le s \le \frac{t+2}{4} \\
h\left( \frac{4s-(2+t)}{2-t} \right), \ \frac{2+t}{4} \le s \le 1
\end{cases}
$$
- Identity:
Given $x,y \in X$, and $f$ any path from $x$ to $y$, we claim that $id_{x}:=[e_{x}]$ is the identity for this operation, where $e_{x} : I \to X$ is the constant path $e_{x}(s) = x \ \forall \ s \in I$.
###### Claim: $[f]*id_{y} = id_{x}*[f]$
##### Proof:
$f \simeq_{p} f*id_{y}$ by defining $$
F(s,t) = \begin{cases}
f(s(1+t)), 0 \le s \le \frac{2-t}{2} \\
y, \frac{2-t}{2} \le s \le 1
\end{cases}
$$
similarly $id_{x}*f \simeq_{p} f$.

- Inverse:
Given a path $f$ from $x$ to $y$, define the reverse path $\bar{f}(s) = f(1-s)$. Then $e_{x}\simeq f*\bar{f}$ and $e_{y}\simeq \bar{f}*f$.
In the first case, $$
F(s,t) = \begin{cases}
f(2s(1-t)), \ 0 \le s \le \frac{1}{2} \\
f(2(1-s)(1-t)), \ \frac{1}{2} \le s \le 1
\end{cases}
$$
Similarly for the second case.

### The fundamental groupoid of $X$
The above information can be packaged into a category $\mathcal{C}$ with objects the elements of $X$, and morphisms $\mathrm{Hom}(x,y) =$ set of equivalence classes of paths from $x$ to $y$. 
The operation $*$ gives us composition of morphisms in this category and is associative.
The identity morphisms exist.

This category is a _groupoid_ since every morphism has an inverse and hence is an isomorphism.

###### This is called the fundamental groupoid of $X$.


---
# References
[[Homotopy of paths]]
[[Category Theory]]
[[Groupoids]]
