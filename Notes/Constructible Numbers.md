202305242105

Type : #Note
Tags : [[Algebra]]

---
# Constructible Numbers
```ad-note
title:
Given a length, which we call 1, a straight-edge and a compass, a real number (a length) is _constructible_ it can be constructed by forming successive intersections of 
- lines drawn through pairs of already constructed points
- circles drawn with centre a constructed point and radius a constructed length
```

### Lemma:
```ad-note
title:
Construcible numbers form a field.
```
###### Proof: 
Given $a,b$ constructible, obviously we can construct $a+b,-a$.
Note that given a point and a line, we can construct a line parallel to the given line and passing through the given point, and a line perpendicular to the given line and passing through the point.

Make a right triangle $ABC$ of perpendicular sides $AB = 1, BC = a$, mark a point $P$ along the side $BA$, such that $BP = b$, then make a line parallel to $AC$ passing through $P$, it cuts $BC$ at $Q$, $BQ = ab$.

Similarly, taking $BP = 1$ along $BC$, we get $BQ = \frac{1}{a}$ with $Q$ on $BA$.

### Lemma:
```ad-note
title:
If $c > 0$ is constructible, then so is $\sqrt{c}$.
```
###### Proof:
Draw a circle of radius $\frac{c+1}{2}$ with centre $\left( \frac{c+1}{2},0 \right)$, and a line passing through $(1,0)$ perpendicular to the $x-$axis. It intersects the circle at length $\sqrt[]{ c }$.

### Theorem:
```ad-note
title:
A number $\alpha$ is constructible iff it is contained in a field of the form $\mathbb{Q}[\sqrt{\alpha_1},\sqrt{\alpha_2},\dots,\sqrt{\alpha_n}]$ such that $\alpha_i \in \mathbb{Q}[\sqrt{\alpha_1},\sqrt{\alpha_2},\dots,\sqrt{\alpha_{i-1}}]$ and $a_i > 0$, for all $i$.
```

##### Proof:
All rationals are constructible, so by a simple induction, one direction of the theorem is clear.

Now suppose $\alpha$ is constructible.
Note that any construction using a given set of numbers $\{ \alpha_{1},\alpha_{2},\dots\alpha_{n} \}$ known to be already constructed, can be shown to belong to the field $\mathbb{Q}[{\alpha_1},{\alpha_2},\dots,{\alpha_n}][\sqrt[]{ e }]$ for some $e \in \mathbb{Q}[{\alpha_1},{\alpha_2},\dots,{\alpha_n}]$ (Use coordinate geometry and get that the intersection points of circles and lines come from quadratics.)

So we get a constructible number in this field extension, and hence the whole field extension consists of constructible numbers.
This shows that any constructible $\alpha$ is contained in a field of the required form.

### Corollary:
```ad-note
title:
If $\alpha$ is constructible, then $\mathbb{Q}(\alpha)$ is algebraic over $\mathbb{Q}$ and $[\mathbb{Q}(\alpha):\mathbb{Q}]$ is a power of 2.
```
###### Proof:
Since $\alpha \in \mathbb{Q}[\sqrt[]{ \alpha_{1} },\dots,\sqrt[]{ \alpha_{n} }]$, we get that degree of $\alpha$ divides $[\mathbb{Q}(\sqrt[]{ \alpha_{1} },\dots,\sqrt[]{ \alpha_{n} }) : \mathbb{Q}]$ which is a power of 2.

### Corollary:
```ad-note
title:
It is impossible to duplicate the cube or square the circle.
```
###### Proof:
Duplicating the cube is equivalent to constructing $\sqrt[3]{ 2 }$, but $[\mathbb{Q}(\sqrt[3]{ 2 }) : \mathbb{Q}] = 3$ is not a power of 2.
Squaring the circle is equivalent to constructing $\sqrt[]{ \pi }$. But $\sqrt[]{ \pi }$ is transcendental since $\pi$ is, hence $\mathbb{Q}(\pi)$ is not algebraic over $\mathbb{Q}$.

### Corollary:
```ad-note
title:
It is impossible to trisect an angle by ruler and compass constructions.
```
###### Proof:
Constructiblity of the angle is equivalent to that of its cosine.
Therefore to trisect $3\theta$, we need to know the solution to the equation, $$
\cos(3\theta) = 4 \cos ^{3}(\theta) - 3 \cos (\theta)
$$
For example, to construct $\cos(20^{\circ})$, we need a solution to $$
\frac{1}{2} = 4 x^{3}-3x
$$
Or equivalently, $8x^{3}-6x-1$. This is irreducible (check roots). Hence $\cos(20 ^{\circ})$ is not constructible.

---
### Theorem:
```ad-note:
title:
If the regular p-gon is constructible, then $p = 2^{2^k} + 1$, where $p$ is a prime.
```
###### Proof:
To construct a regular $p$-gon, it is necessary to construct the angle $\frac{2\pi}{p}$ and hence $\cos\left( \frac{2\pi}{p} \right)$.
Notice that $$
\cos\left( \frac{2\pi}{p} \right) = \frac{e ^{2\pi i/p} + e ^{-2\pi i/p}}{2}
$$
Hence, $\mathbb{Q} \subset \mathbb{Q}\left[ \cos\left( \frac{2\pi}{p} \right) \right] \subset \mathbb{Q}[e ^{2\pi i/p}]$.

The degree of the latter extension is 2 since,
$$
t^{2} - 2\cos\left( \frac{2\pi}{p} \right) t + 1 = 0
$$
is the minimal poly of $e ^{2\pi i/p}$ over $\mathbb{Q}\left[ \cos\left( \frac{2\pi}{p} \right) \right]$.
Thus, $\left[ \mathbb{Q}\left( \cos\left( \frac{2\pi}{p} \right) \right) : \mathbb{Q} \right] = \frac{p-1}{2}$. (See [[Cyclotomic Fields]])

Thus $\frac{p-1}{2} = 2^k$ with $k \ge 0 \implies p = 2^{k+1}+1 \implies 2^{2^n}+1$ (Fermat primes). 


---
# References
[[Fields]]
[[Field Extensions]]
[[Algebraic Extension]]
[[Cyclotomic Fields]]
