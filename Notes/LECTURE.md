
0. What is a discrete valuation on a field.  $v : K^{\times} \to \mathbb{Z}$ such that $v(a+b) \ge \min(v(a),v(b))$ and $v(ab) = v(a)+v(b)$.
1. This can be extented to whole of $K$ by defining $v(0) = \infty$. We follow the first definition in this lecture.
2. Example: P-adic valuation on Q v_p
3. The ring $A := \{ x \in K \mid v(x) \ge 0\}$ is called the _valuation ring_ of $K$. 
4. What is an absolute value or multiplicative valuation on a field. Archimedean, Non archimedean.
5. Example: P-adic abs val on Q.
6. Why is it called non archimedean?
7. Show examples as in the notes. Define p-adic absolute value on $\mathbb{Q}$. 
8. Can go from a valuation to an absolute value and vice versa. $v(x) = -\log(|x|)$
9. Relation between absolute value and additive valuations:
   A discrete (additive) valuation $\mathrm{ord} : K^{\times} \to \mathbb{Z}$  determines an absolute value by $|x| = e^{-\mathrm{ord}(x)}$
   An absolute value on $K$ determines an additive valuation (need not be discrete) on $K^{\times}$ by $\log_{e}|x| = -\mathrm{ord}(x)$
7. 
   ### Lemma:
   Absolute value is non archimedean iff it takes bounded values on $\{m \cdot 1 | m \in \mathbb{Z} \}$
	1. Corollary: If $\mathrm{char} K \neq 0$ then $K$ has only non archimedean abs values.

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
### Proposition 7.6 : | | discrete iff m is principal, which makes A a DVR (PID + local)
   ##### Proof:
   If $\mid\cdot\mid$ is discrete, then take $\pi \in \mathfrak{m}$ such that $\mid \pi\mid$ is maximum. Then take any $\pi_{1} \in \mathfrak{m}$ and let $\mid \pi\mid^{q+1} < \mid \pi_{1}\mid < \mid \pi\mid^{q}$.
   and so, $|\pi|<\mid \frac{\pi_{1}}{\pi^{q}}\mid < 1$ and so, $\frac{\pi_{1}}{\pi^{q}} \in \mathfrak{m}$ and has larger absolute value than $\pi$. Contradiction. So, $|\pi_{1}| = |\pi|^{q}$, this gives $\pi_{1} = \pi^{q} \cdot u$ where $u$ is a unit in $A$, hence $\pi_{1} \in (\pi) \implies \mathfrak{m} \subset (\pi) \implies \mathfrak{m} = (\pi)$.
   
   If $\mathfrak{m} = (\pi)$ then take any $\alpha \in K^{\times}$, let $|\pi|^{q+1} < |\alpha| < |\pi|^{q}$, then $\mid\frac{\alpha}{\pi^{q}}\mid < 1 \implies \frac{\alpha}{\pi^{q}} \in (\pi) \implies \alpha = \pi^{q+1}\beta$ where $\beta \in A$. This gives $|\alpha| \leq |\pi|^{q+1}$ This is a contradiction, hence $|\alpha| = |\pi|^{q}$ for some $q \in \mathbb{Z}$. Hence $\mid K^{\times}\mid =(|\pi|)$.
   
   Take an ideal $I$ of $A$, $I$ does not contain any element with abs value 1, since they are units of A. So, take the element $a$ with greatest abs val, this generates $I$. Why? Because any element with equal abs val as that of $a$, is an associate of $a$. Now if $|a|^{q+1} < |b|<|a|^q$ we get that $|ba^{-q}| < 1$ hence $ba ^{-q} \in A$, but has greater abs val than $a$. Contradiction.
   
   So this is a PID.

9. Abs value induce metric induce topology
10. Abs value equiv if they induce same topology
11. Q with p adic abs value, what is it? what does closeness look like here? 1,p,p^2,.... converges to 0
12. Equivalent abs values
13. Ostrowski
14. Completion of Q under p- adic abs value
15. Completions in non archimedean case
16. |K| = |$\hat{K}$| 
17. $\hat{A}$ is the closure of A, $\hat{\mathfrak{m}}$ is the closure of $\mathfrak{m}$, $\hat{\mathfrak{m}}^{n}$ is the closure of $\mathfrak{m}^{n}$.
18. $\hat{\mathfrak{m}} = (\pi) = \{ a \in \hat{K}\mid \ |a| \le |\pi| \}$
19.  For every $n$, $$\frac{A}{\mathfrak{m}^{n}} \to \frac{\hat{A}}{\hat{\mathfrak{m}}^{n}}$$
	Is an isomorphism.
##### Proof:
The function is $f(a+\mathfrak{m}^{n}) = a + \hat{\mathfrak{m}}^{n}$.
Note that $\mathfrak{m}^{n} = \{ a \in A \mid \ \mid a\mid \le \mid \pi\mid^{n} \} = \{ a \in A \mid \ \mid a\mid < \mid \pi\mid^{n-1} \}$ is open and closed as a subset of $A$. 
Now $\ker(f) = \{ a + \mathfrak{m}^{n} \mid a \in A, a \in \hat{\mathfrak{m}}^{n} \}$
Since $\mathfrak{m}$ is dense in $\hat{\mathfrak{m}}$, $\mathfrak{m}^{n}$ is dense in $\hat{\mathfrak{m}}^{n}$ ($\mathfrak{m}^{n} = (\pi^{n}) \subset A$, and $\hat{\mathfrak{m}}^{n} = (\pi^{n}) \subset \hat{A}$).
Since $a \in A$ and $a$ is a limit point of $\mathfrak{m}^{n}$, it must be in $\mathfrak{m}^{n}$ since it is closed in $A$.
This gives $\ker(f) = \{ 0 \}$.

Now, let $\hat{a} \in \hat{A}$, $\lim_{ n \to \infty }a_{n} = \hat{a}$,
This gives $a_{k} \in \hat{a} + \hat{\mathfrak{m}}^{n}$ for all large $k$. (Since $\hat{\mathfrak{m}}^{n}$ is an open set around 0).
Hence, $f(a_{k} + \mathfrak{m}^{n}) = a_{k} + \hat{\mathfrak{m}}^{n} = \hat{a} + \hat{\mathfrak{m}}^{n}$.
Hence, $f$ is surjective

20. Choose a set $S$ of representatives of $\frac{A}{\mathfrak{m}}$, and let $\pi$ generate $\mathfrak{m}$. Then each element of $\hat{K}$ is expressible as a cauchy series of the form $$
a_{-n}\pi^{-n} + \dots + a_{0} + a_{1}\pi + a_{2}\pi^{2}\dots, \ a_{i}\in S
$$
and such a representation is unique.

21. Use this to show how elements of $\mathbb{Q}_{p}$ look like

22. Let $K = \mathbb{Q}$, then $\hat{K} = \mathbb{Q}_{p}$, $A = \left\{  \frac{a}{b} \in \mathbb{Q} \mid p \nmid b, (a,b) = 1  \right\}$, $\mathfrak{m} = \left\{  \frac{a}{b} \in \mathbb{Q} \mid p |a; (a,b) = 1  \right\}$
23. Then the representatives for $A/\mathfrak{m}$ are just $0,1,\dots p-1$
24. In other words, $A / \mathfrak{m} \cong \mathbb{Z}/p\mathbb{Z}$.
25. $A = \mathbb{Z}_{(p)}$, $\mathbb{Z}_{p} := \hat{A}$. So, $\mathbb{Z}_{p}$ is the elements of $\mathbb{Q}_{p}$ with series expansion starting from non negative integers.
27. Given a element of $\prod \limits_{ n=1}^{ \infty } \mathbb{Z} /p ^{n} \mathbb{Z}$, with $a_{n+1} = a_{n}(\mathrm{mod} \ p ^{n})$, can change it into a series representation.
28. Conversely, If then $\alpha = \sum\limits_{ i=0}^{ \infty }c_{i}p ^{i}$, $0 \le c < p-1$, then $c_{0},c_{1},\dots$ is the unique sequence of integers such that 
    $\alpha \equiv \sum\limits_{ i=0}^{ n-1 }c_{i}p ^{i}\ \mathrm{mod} \ p^n$
- So basically, elements of $\mathbb{Z}_{p}$ have "compatibility" among the coefficients, and any truncation of the series gives mod p^n of that number
31. Any element $\alpha \in \mathbb{Q}_{p}$, can multiply it by high power of $p$ and bring it in $\mathbb{Z}_{p}$. hence, coefficients of $\mathbb{Q}_{p}$ elements also have compatibility.
32. Hensel's lemma
33. Nakayama lemma for local rings: 
    Let $A$ be a local ring and $\mathfrak{a}$ is a proper ideal of $A$. Let $M$ be a f.g. module over $A$, then $\mathfrak{a}M = M$ implies $M = 0$.