---
tags:
  - Note
---
202403051003

Tags : [[Theory of Computation]], [[Complexity Theory]]
# Elementary Functions
---
*Elementary Functions* are the smallest set of functions that satisfy the following properties:
- It contains the $\textbf{ZERO}$ functions.
- It contains the successor function $\textbf{S}$.
- It contains projection functions
- It contains subtraction function.
- It is closed under composition
- It is closed under bounded summation and bounded multiplication

These are also equivalent to [[Primitive Recursion|primitive recursive functions]] if we replace Primitive recursion with finite depth recursion.

---
## ELEMENTARY
The set of *Elementary Functions* can also be cleanly written as the complexity class $\textbf{ELEMENTARY}$ in terms of complexity classes in the following way.
$$
\textbf{ELEMENTARY} = \textbf{P} \cup \textbf{EXP} \cup \textbf{2-EXP} \cup \cdots
$$
Where $\textbf{n-EXP}=\textbf{DTIME}\left(2^{2^{2^{.^{.^{.^n}}}}}\right)$ where the power tower has height $n$.

---
## Properties
>[!theorem]
>If $f$ is elementary, then there exists a $k$ such that $f$ is bounded by $2 \uparrow\uparrow k$.

*Proof*: Just a case-bash induction
- $x+1\leq2^x$
- $x-y \leq \max(x, y)$
- $x+y\leq 2(\max(x, y)) \leq 2^{\max(x, y)+1}\leq 2^{2^{\max(x, y)}}$
- $xy \leq (\max(x, y))^2\leq 2^{2\max(x, y)}\leq 2^{2^{2^{\max(x, y)}}}$ 
- For closure under composition, let the function be $h(\mathbf{x})=f(g_{1}(\mathbf{x}),g_{2}(\mathbf{x})\dots g_{m}(\mathbf{x}))$ and we have $g_i(\mathbf{x})\leq b_{k_{i}}(\max(\mathbf{x}))$ and $f(\mathbf{x})< b_{l}(\max(\mathbf{x}))$.  Let $k = \max(k_{1}\dots k_m)$Then we have the following $$
  \begin{align}
    h(\mathbf{x}) &\leq b_{l}(\max(g_{1}(\mathbf{x})\dots g_{m}(\mathbf{x})))  \\
    &\leq b_{l}(\max(b_{k_{1}}(\max(\mathbf{x}))\dots b_{k_{m}}(\max(\mathbf{x})))) \\
    &\leq b_{l}(b_{k}(\max(\mathbf{x}))) \\
    &\leq b_{l+k}(\max(\mathbf{x}))
  \end{align}
  $$
- For Closure under bounded addition. Let $g(\mathbf{x}, y)=\sum_{z\leq y} f(\mathbf{x}, z)$ and $f(\mathbf{x}, z)< b_{k}(\max(\mathbf{x}, z))$. then 
  $$
  \begin{align}
    g(\mathbf{x}, y) &\leq \sum_{z\leq y}b_{k}(\max(\mathbf{x}, z)) \\ 
    &\leq y\cdot b_{k}(\max(\mathbf{x}, y)) \\
    &\leq ( b_{k}(\max(\mathbf{x}, y)))^2 \\
    &\leq b_{k+2}(\max(\mathbf{x}, y))

  \end{align}
  $$
- For Closure under bounded multiplication. Let $g(\mathbf{x}, y)=\prod_{z\leq y}f(\mathbf{x}, z)$ and let $f(\mathbf{x}, z)< b_{k}(\max(\mathbf{x}, z))$ Then
  $$
  \begin{align}
    g(\mathbf{x}, y) &\leq \prod_{z\leq y} b_{k}(\max(\mathbf{ x}, z)) \\
    & \leq b_{k}(\max(\mathbf{ x}, y))^{\max(\mathbf x, y)} \\
    & \leq 2^{b_{k-1}(\max(\mathbf{ x}, y))+\max(\mathbf{x}, y)} \\
    & \leq 2^{2^{2^{\max(b_{k-1}(\max(x, y)), \max(x, y))}}} \\
    & \leq 2^{2^{2^{b_{k-1}(\max(x, y))}}} \\
    & \leq b_{k+1}(\max(x, y))
  \end{align}
  $$
Hence proved.

---
# References
