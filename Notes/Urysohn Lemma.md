202303211003

Type : #Note
Tags : [[Topology]]

---
# Urysohn Lemma
```ad-info
This lemma roughly states that given two disjoint closed subsets of a normal space, we can separate them by real valued functions.
```

```ad-note
title: Statement of the lemma
Let $A,B$ be disjoint closed subsets of a normal space $X$. Then there exists a continuous map $f: X \to [0,1]$ such that $f(x) = 0$ for all $x \in A$ and $f(x) = 1$ for all $x \in B$.
```
##### Proof:
A dyadic number is a rational number of the form $\dfrac{a}{2^{n}}$, where $a,n$ are integers with $n \ge 0$. Then it is easy to check that these numbers are dense in $\mathbb{R}$.

We shall construct an open subset $U_{r}\subseteq X$ for each dyadic number $r\in[0,1]$, with $A \subset U_{r} \subset X  \setminus B$. Such that for each pair $p<q$ of dyadics in $[0,1]$, we have that $Cl(U_{p}) \subset U_{q}$.

Let $U_{1} = X \setminus B$. Then since $X$ is normal, there is a nbhd around $A$, call this $U_{0}$, such that $Cl\left( U_{0} \right) \subset U_{1}$.
Similarly, we get another open set $U_{\frac{1}{2}}$ such that $Cl(U_{0}) \subset U_{\frac{1}{2}} \subset Cl\left( U_{\frac{1}{2}} \right) \subset U_{1}$.

Now let $n \ge 2$.
Assume we have constructed the required subsets for all $r$ in $[0,1]$ of the form $\dfrac{b}{2^{n-1}} = \dfrac{2b}{2^{n}}$.
So we need to constuct $U_{\frac{2n+1}{2^{n}}}$, again use normality, and get $$
Cl\left(U_{\frac{2b}{2^{n}}}\right) \subset U_{\frac{2n+1}{2^{n+1}}} \subset Cl\left( U_{\frac{2n+1}{2^{n}}} \right) \subset U_{\frac{2n+2}{2^{n}}} 
$$
Hence, by induction, we construct $U_{r}$ for all dyadic $r$ in $[0,1]$.
Now let $U_{r} = \phi$ for $r < 0$. and $U_{r} = X$ for $r > 1$.

Now let $x \in X$, we define $$
D(x) := \{ r\ \mathrm{dyadic} : x \in U_{r} \}
$$
Since $x \notin U_r$ for $r < 0$, and $x \in U_{r}$ for $r>1$, $D(x) \neq \phi$ and it is bounded below by 0. So $$
f(x) := \inf D(x)
$$
exists and lies in $[0,1]$.
Now see that $f(x) = 0$ for $x \in A$, and $f(x) = 1$ for $x \in B$.

To show that $f$ is continuous, first observe that if $x \in Cl(U_{r})$ then $f(x)\le r$.
And also, if $x \notin U_{r}$, then $f(x) \geq r$.

Now let $x \in X$, pick a nbhd $(c,d)$ of $f(x)$. Take dyadic numbers $p,q$ such that $c < p <f(x)< q < d$. 
This means that $x \notin Cl(U_{p})$ but $x \in U_{q} \implies x \in U := U_{q} \setminus Cl(U_{p})$.
But then for any $y \in U$, $y \notin U_{p}$, and so $f(y) \geq p$. Also since $y \in U_{q}$, $f(y)\le q$. This gives $f(U) \subset (c,d)$.
Hence $f$ is continuous.


---
# Related Problems
[[Urysohn Metrization Theorem]]

---
# References
[[Normal Spaces]]
[[Closure and Interior and Limit Points]]
[[Continuous Functions]]

