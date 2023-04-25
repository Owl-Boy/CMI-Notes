0. What is a discrete valuation on a field.  $v : K^{\times} \to \mathbb{Z}$ such that $v(a+b) \ge \min(v(a),v(b))$ and $v(ab) = v(a)+v(b)$.
1. This can be extented to whole of $K$ by defining $v(0) = \infty$. We follow the first definition in this lecture.
2. The ring $A := \{ x \in K \mid v(x) \ge 0\}$ is called the _valuation ring_ of $K$. 
3. What is an absolute value or multiplicative valuation on a field. Archimedean, Non archimedean.
4. Why is it called non archimedean?
5. Show examples as in the notes. Define p-adic absolute value on $\mathbb{Q}$. 
6. Can go from a valuation to an absolute value and vice versa. $v(x) = -\log(|x|)$
1. Relation between absolute value and additive valuations:
   A discrete (additive) valuation $\mathrm{ord} : K^{\times} \to \mathbb{Z}$  determines an absolute value by $|x| = e^{-\mathrm{ord}(x)}$
   An absolute value on $K$ determines an additive valuation (need not be discrete) on $K^{\times}$ by $\log_{e}|x| = -\mathrm{ord}(x)$
7. 
   ### Lemma:
   Absolute value is non archimedean iff it takes bounded values on $\{m \cdot 1 | m \in \mathbb{Z} \}$
	1. Corollary: If $\mathrm{char} K \neq 0$ then $K$ has only non archimedean abs values.

### Proposition:
```ad-note
title:
Let $\mid \cdot\mid$ be a non trivial non archimedean absolute value, and let $v(x) = -\log|x|$ (base $e > 1$). Then $v : K^{\times} \to \mathbb{R}$ satisfies:

(a) $v(xy) =v(x) + v(y)$

(b) $v(x+y) \ge \min(v(x),v(y))$

If $v(K^{\times})$ is discrete in $\mathbb{R}$, then $v$ is a multiple of a discrete valuation $\mathrm{ord}$ on $K^{\times} \twoheadrightarrow \mathbb{Z}$.
```

##### Proof:
Note that $v(K^{\times})$ is a subgroup of $\mathbb{R}$ under addition, and is discrete and hence is a lattice and so, $v(K^{\times}) = c \cdot \mathbb{Z}$ for some $c$. Now $\mathrm{ord} := c^{-1} \cdot v$ is an additive discrete valuation on $K^{\times} \twoheadrightarrow \mathbb{Z}$.

(there is a theorem that says a discrete subgroup of a real vector space is a lattice iff it is a discrete subgroup)

6. Say that the absolute value is discrete if the image of $K^{\times}$ is a discrete subgroup of $\mathbb{R}_{>0}$.
7. Let $v$ be a discrete valuation on $K$, then $$
A := \{ a \in K : v(a) \geq 0 \}
$$
is a PID with the unique maximal ideal $$
\mathfrak{m} := \{ a \in K : v(a) > 0 \}
$$
##### Proof:
Take an ideal $I$ of $A$, $I$ does not contain any element with valuation 0, since they are units of A. So, take the element $a$ with least valuation, this generates $I$. any element with equal valuation as that of $a$, is an associate of $a$. Now if $v(b) = qv(a) + r$ with $0<r<b$, we get that $v(b a^{-q}) = r > 0$ hence $ba ^{-q} \in A$, but has smaller valuation than $a$. Contradiction.
So this is a PID.

Easy to see that $\mathfrak{m}$ is the unique maximal ideal.

8. 
   ### Proposition 7.6
   ##### Proof:
   If $\mid\cdot\mid$ is discrete, then take $\pi \in \mathfrak{m}$ such that $\mid \pi\mid$ is maximum. Then take any $\pi_{1} \in \mathfrak{m}$ and let $\mid \pi\mid^{q+1} < \mid \pi_{1}\mid < \mid \pi\mid^{q}$.
   and so, $|\pi|<\mid \frac{\pi_{1}}{\pi^{q}}\mid < 1$ and so, $\frac{\pi_{1}}{\pi^{q}} \in \mathfrak{m}$ and has larger absolute value than $\pi$. Contradiction. So, $|\pi_{1}| = |\pi|^{q}$, this gives $\pi_{1} = \pi^{q} \cdot u$ where $u$ is a unit in $A$, hence $\pi_{1} \in (\pi) \implies \mathfrak{m} \subset (\pi) \implies \mathfrak{m} = (\pi)$.
   
   If $\mathfrak{m} = (\pi)$ then take any $\alpha \in K^{\times}$, let $|\pi|^{q+1} \leq |\alpha| \leq |\pi|^{q}$, then $\mid\frac{\alpha}{\pi^{q}}\mid < 1 \implies \frac{\alpha}{\pi^{q}} \in (\pi) \implies \alpha = \pi^{q+1}\beta$ where $\beta \in A$. This gives $|\alpha| \leq |\pi|^{q+1}$ This is a contradiction, hence $|\alpha| = |\pi|^{q}$ for some $q \in \mathbb{Z}$. Hence $\mid K^{\times}\mid =(|\pi|)$.

9. Topology induced by the p-adic absolute value is called the p-adic topology.
10. Proposition 7.8
11. Let $\mathrm{ord}$ be an additive valuation on $K$, then $\mathrm{ord}(a+b) \ge\min(\mathrm{ord(a)},\mathrm{ord(b)})$ with equality if $\mathrm{ord}(a) \neq \mathrm{ord}(b)$.
12. Similarly, $\mid a+b\mid \le \max(\mid a\mid,\mid b\mid)$ with equality if $\mid a\mid \neq \mid b\mid$.
13. If $x$ is closer to $b$ than it is to $a$, then $d(x,a) = d(b,a)$.$$
|b-a| = |b-x+x-a| = |x-a|
$$
14. Ostrowski's theorem
```ad-note
title:
Let $\mid\cdot\mid$ be a non trivial absolute value on $\mathbb{Q}$.
(a) If $\mid\cdot\mid$ is archimedean, then $\mid\cdot\mid$ is equivalent to $\mid\cdot\mid_{\infty}$
(b) Otherwise, it is equivalent to $\mid\cdot\mid_{p}$ for some prime $p$.
```
15. Lemma 7.18
```ad-note
title:
If $\mid\cdot\mid_{1}, \mid\cdot\mid_{2},\dots,\mid\cdot\mid_{n}$ are non trivial inequivalent absolute values of $K$, then there is an element $a \in K$ such that $$
\begin{cases}
\mid a\mid_{1}\ >1   \\
\mid a\mid_{i}\ < 1, \ i \neq 1 
\end{cases}
$$
```

16. Lemma 7.19
17. Theorem 7.20
18. Theorem 7.23
19. Absolute value on a field is continuous w.r.t. itself
20. An absolute value preserving function between fields is continuous.
21. COMPLETIONS IN NON ARCHIMEDEAN CASE
	Let $\mid \cdot \mid$ be a _discrete_ non archimedean absolute value on $K$. (Why discrete? we are only interested in the discrete case since $\mathbb{Q}_{p}$ has a discrete absolute value)
	This gives that $\mathfrak{m} = (\pi)$ for some $\pi \in K$ with largest value $<1$.
	The set of values $\mid K\mid = \{ c ^{m} | m \in \mathbb{Z}\} \cup \{ 0 \}$, $c = \mid \pi\mid$.
22. What does this AV look like on $\widehat{K}$? 
	Let $a \in \widehat{K}$ and let $a_{n} \to a$, Then $\mid a_{n}\mid \to \mid a\mid$, so $\mid a\mid$ is a limit point of $\mid K ^{\times}\mid$ and so $\mid a\mid = 0$ or $\mid a\mid \in |K ^{ \times}|$, but $\mid a\mid = 0 \implies a = 0$, hence $\mid \widehat{K} \mid = \mid K \mid$.
	So $\mid \cdot \mid$ is discrete on $\widehat{K}$ also.
23. Let $\mathrm{ord}$ be a normalised discrete valuation on $K ^{ \times}$ corresponding to $\mid \cdot\mid$ then it extends to a normalised discrete val on $\hat{K}$.
24. Given $a_{n} \to a$, $|a_{n}| \to |a|$ but $\mid \cdot \mid$ being discrete, $|a_{n}| = |a|$ for large enough $n$.
25. $\hat{A}$ is the closure of $A$. Since any cauchy sequence in $A$ has its limit point in $\hat{A}$. Any point in $\hat{A}$ has a cauchy sequence in $A$ converging to itself, $a_{n} \to a$, but $|a_{n}| = |a|$ for large $n$. and so, $\hat{A} \subset Cl(A)$
26. $\hat{\mathfrak{m}} = Cl(\mathfrak{m})$ 
27. For every $n$, $$\frac{A}{\mathfrak{m}^{n}} \to \frac{\hat{A}}{\hat{\mathfrak{m}}^{n}}$$
	Is an isomorphism.
##### Proof:
The function is $f(a+\mathfrak{m}^{n}) = a + \hat{\mathfrak{m}}^{n}$.
Note that $\mathfrak{m}^{n} = \{ a \in A \mid \ \mid a\mid \le \mid \pi\mid^{n} \} = \{ a \in A \mid \ \mid a\mid < \mid \pi\mid^{n-1} \}$ is open and closed as a subset of $A$. 
Now $\ker(f) = \{ a + \mathfrak{m}^{n} \mid a \in A, a \in \hat{\mathfrak{m}}^{n} \}$
Since $\mathfrak{m}$ is dense in $\hat{\mathfrak{m}}$, $\mathfrak{m}^{n}$ is dense in $\hat{\mathfrak{m}}^{n}$ ($\mathfrak{m}^{n} = (\pi) \subset A$, and $\hat{\mathfrak{m}}^{n} = (\pi) \subset \hat{A}$).
Since $a \in A$ and $a$ is a limit point of $\mathfrak{m}^{n}$, it must be in $\mathfrak{m}^{n}$ since it is closed in $A$.
This gives $\ker(f) = \{ 0 \}$.

Now, let $\hat{a} \in \hat{A}$, $\lim_{ n \to \infty }a_{n} = \hat{a}$,
This gives $a_{k} \in \hat{a} + \hat{\mathfrak{m}}^{n}$ for all large $k$. (Since $\hat{\mathfrak{m}}^{n}$ is an open set around 0).
Hence, $f(a_{k} + \mathfrak{m}^{n}) = a_{k} + \hat{\mathfrak{m}}^{n} = \hat{a} + \hat{\mathfrak{m}}^{n}$.
Hence, $f$ is surjective

28. Choose a set $S$ of representatives of $\frac{A}{\mathfrak{m}}$, and let $\pi$ generate $\mathfrak{m}$. Then each element of $\hat{K}$ is expressible as a cauchy series of the form $$
a_{-n}\pi^{-n} + \dots + a_{0} + a_{1}\pi + a_{2}\pi^{2}\dots, \ a_{i}\in S
$$
and such a representation is unique.

29. Let $K = \mathbb{Q}$, then $\hat{K} = \mathbb{Q}_{p}$, $A = \left\{  \frac{a}{b} \in \mathbb{Q} \mid p \nmid b, (a,b) = 1  \right\}$, $\mathfrak{m} = \left\{  \frac{a}{b} \in \mathbb{Q} \mid p |a; (a,b) = 1  \right\}$
30. Then the representatives for $A/\mathfrak{m}$ are just $0,1,\dots p-1$
31. In other words, $A / \mathfrak{m} \cong \mathbb{Z}/p\mathbb{Z}$.
32. $A = \mathbb{Z}_{(p)}$, $\mathbb{Z}_{p} := \hat{A}$. So, $\mathbb{Z}_{p}$ is the elements of $\mathbb{Q}_{p}$ with series expansion starting from non negative integers.
33. The maps $\mathbb{Z} /(p ^{n}) \to \mathbb{Z}_(p) /(p ^{n}) \to \mathbb{Z}_{p} /(p ^{n})$, which just takes $a + (p ^{n}) \mapsto a + (p ^{n}) \mapsto a + (p ^{n})$ are bijections.
34. Let $\alpha \in \mathbb{Z}_{p}$, because the map is bijective, for all $n$, there is an $a_{n}$, such that $\alpha \equiv a_{n} (p ^{n})$.
35. If $n < m$, $a_{n} \equiv a_{m} (p ^{n})$, hence $(a_{n})$ is a cauchy sequence. Let $a_{n} = c_{0} + c_{1}p + \dots c_{n-1}p ^{n-1} (\mathrm{mod} \ p^n)$, $0\le c_i<p-1$
36. Then $\alpha = \sum\limits_{ i=0}^{ \infty }c_{i}p ^{i}$
37. Conversely, If then $\alpha = \sum\limits_{ i=0}^{ \infty }c_{i}p ^{i}$, $0 \le c < p-1$, then $c_{0},c_{1},\dots$ is the unique sequence of integers such that 
    $\alpha \equiv \sum\limits_{ i=0}^{ n-1 }c_{i}p ^{i}\ \mathrm{mod} \ p^n$
- So basically, elements of $\mathbb{Z}_{p}$ have "compatibility" among the coefficients, and any truncation of the series gives mod p^n of that number
38. Any element $\alpha \in \mathbb{Q}_{p}$, can multiply it by high power of $p$ and bring it in $\mathbb{Z}_{p}$. hence, coefficients of $\mathbb{Q}_{p}$ elements also have compatibility.
39. Example 7.27
40. Show another definition of $\mathbb{Z}_{p}$, which is made by sequences where the nth term is from $\mathbb{Z}/p ^{n}\mathbb{Z}$.
41. Show that each such sequence is the same as a cauchy series in our previous definition and vice versa.
42. Let $f(X) \in A[X]$ and let $a_{0}$ be a simple (not multiple) root of $f(X)$ mod $\pi$. Then there is a unique root $a \in A$ of $f(X)$ with $a \equiv a_{0} \ \mathrm{mod} \pi$
43. Hensel's lemma
44. Use nakayama lemma for local rings
45. 