202303111503

Type : #Note
Tags : [[Differential Equations]]

---
# Linear Systems
```ad-note
title:
ODEs where dependence on phase is linear. 
For example,
$$ \dot{x} = kx \leftrightarrow x(t) = x(0)e^{kt}$$
$$
\dot{x} = p(t)x(t) + q(t)
$$
```

## Existence and uniqueness for 1st order Linear systems
```ad-note
title:
Let $I \subseteq \mathbb{R}$, be an interval and 
$$
\mathcal{A} : I \to M_{n}(\mathbb{R})
$$
$$
\mathcal{b} : I \to \mathbb{R}^{n}
$$
be continuous on $I$.
Let $(t_{0},x_{0}) \in I \times \mathbb{R}^{n}$. Then the IVP 
$$\dot{\bar{x}}(t) = \mathcal{A}(t) + \mathcal{ b}(t); \ \bar{x}(t_{0}) = x_{0} 
$$
has a unique solution on $I$.
```
##### Proof:
1. WLOG assume that $I$ is compact. Since if not, then we can take a sequence $I_{n}$ of compact subsets of $I$, which converge to $I$, such that on each of the $I_{n}$'s the solution is unique, and then the solution on $I$ is given by patching together the solutions on these $I_{n}$'s.
2. Take $I = [\alpha,\beta]$. Define 
$$ v : I \times \mathbb{R}^{n} \to \mathbb{R}^{n}$$
$$ (t,\bar{x}) \to A(t)\bar{x} + b(t)$$
3. Check that $v$ satisfies the conditions of local existence and uniqueness thm (Maximal interval of existence theorem), i.e., check that $v$ is continuous and is lipschitz w.r.t. $x$.
4. To apply the theorem, we need open domain, so we extend $I$ to $I_{\eta} = (\alpha-\eta,\beta+\eta)$ for some $\eta > 0$, 
   $$
\widetilde{A}(t) := 
\begin{cases}
A(\alpha) & \mathrm{if} & \alpha-\eta < t \le \alpha; \\
A(t) & \mathrm{if} & \alpha<t<\beta;\\ 
A(\beta) & \mathrm{if} & \beta \le t < \beta + \eta
\end{cases}
$$
Similarly for $\widetilde{b}$.
5. We have $\widetilde{v} : I_{\eta} \times \mathbb{R}^{n} \to \mathbb{R}^{n}$. $$
\widetilde{v}(t,\bar{x}) = \widetilde{A}(t)\bar{x}+ \widetilde{b}(t)
$$
being lipschitz with respect to $x$, now apply the local existence and uniqueness theorem which gives a unique solution on a maximal interval $(\omega_{-}, \omega_{+})$.
6. Show that $(\omega_{-},\omega_{+}) = I_{\eta} \implies \phi_{max}|_{I}$ is unique solution of the given IVP.
   For $t \in [t_{0},\omega_{+})$, we have (here $M = \sup\limits_{s \in I} |b(s)|$, and $\mid\mid \widetilde{A}(s)\mid\mid \le L$ for all $s \in I$)
   $$
   \begin{align}
\phi_{max}(t) &= x_{0} + \int\limits_{t_{0}}^{t} \widetilde{v}(s,\phi_{max}(s))\, ds\\ \\
&=  x_{0} + \int \limits_{t_{0}}^{t}(\widetilde{A}(s)\phi_{max}(s) + \widetilde{b}(s)) \, ds \\
\implies |\phi_{max}(t)|&\le |x_{0}| + \int \limits_{t_{0}}^{t}\mid\mid \widetilde{A}(s)\mid\mid \mid \phi_{max}(s)\mid \, ds + M(t-t_{0})\\
&\le |x_{0}| + L \int\limits_{t_{0}}^{t} \mid \phi_{max}(s)\mid \, ds + M(t-t_{0})\\

\end{align}
   $$
7. Take $K = |x_{0}| + M(t-t_{0})$, then using [[Gronwall's Inequality]], we get $|\phi_{max}(t)| \le K e^{L(t-t_{0})} \ \forall t \in [t_{0},\omega_{+})$, hence it is bounded.
   But we know $(t,\phi_{max}(t))$ escapes every compact subset of $I_{\eta} \times \mathbb{R}^{n}$ as $t \to \omega_{+}$, hence $\omega_{+} = \beta+\eta$, similarly $\omega_{-} = \alpha-\eta$.
   Therefore, $\phi_{max}$ exists on $I$ and is the unique solution to the required IVP. 
---
# Related Problems

---
# References
[[Gronwall's Inequality]]
[[Maximal Interval of Existence]]


