202304041604

Type : #Note
Tags :[[Topology]]

---
# Deformation Retracts
```ad-info
title:Idea
1. $S ^{1} \to \{ p \}$, $p \in S ^{1}$ is a retraction
2. $(x,y,z) \mapsto (x,y,|z|)$ is a retraction $S ^{2} \to S ^{2}_{+}$
3. $x \mapsto \frac{x}{|x|}$ on $\mathbb{R}^{2} \setminus \{ 0 \} \to S ^{1}$
4. The map that shrinks a mobius strip to its central circle $S ^{1}$
   $X = I \times I / (0,y) \sim (1,1-y)$ is a square with opposite sides twisted and identified. 
   $H : X \times I \to X$
   $H((x,y),t) = (x, \frac{1}{2}t + y(1-t))$ is the homotopy from $id_{X}$ to the retraction.

- In the last two examples, $id_{X}$ can be deformed continuously in $X$ to get the retraction map, contrary to the first two examples.

```

### Definition:
```ad-note
title:
Let $A \subset X$. $A$ is a **deformation retract** of $X$ if the map $id_X$ is homotopic to a map that carries all of $X$ into $A$, such that each point of $A$ remains fixed during the homotopy.
```
- $H : X \times I \to X$ s.t. $H(x,0) = x$, $H(x,1) \in A$ $\forall \ x \in A$, and $H(a,t) = a$ for all $a \in A$ $\forall \ t \in [0,1]$.
- $H$ is called a deformation retraction of $X$ onto $A$, $r : X \to A$, $r(x):= H(x,1)$ is a retraction.

#### Example:
1. $\mathbb{R}^{n}\setminus \{ 0 \} \to S ^{n-1}$
   $H(x,t) = t \frac{x}{|x|} + (1-t)x$ 

### Lemma 1:
```ad-note
title:
Let $h,k : (X,x_{0}) \to (Y,y_{0})$ be cts s.t. $h,k$ are homotopic to each other under $H$, and $x_{0} \to y_{0}$ throughout the homotopy,
i.e, the image of $x_{0}$ = $y_{0}$ for each function $H|_{X \times \{ t \}}$. Then $h_{*}$ and $k_{*}$ are equal to each other.
```
##### Proof:
To show: $h_{*}([f]) = k_{*}([f])$
$\iff [h \circ f] = [k \circ f] \iff h \circ f \simeq_{p} k \circ f$
$$
I \times I \xrightarrow{f \times id} X \times I \xrightarrow{H} Y
$$
So, $H \circ (f \times id)$ is a homotopy between $h \circ f$ and $k \circ f$. Path homotopy because $f$ is a loop at $x_{0}$, and $H$ maps $\{ x_{0} \} \times I \to \{ y_{0} \}$.

### Lemma 2:
```ad-note
title:
$h,k : X \to Y$ cts map. $h,k$ are homotopic under homotopy $H$, say $h(x_0) = y_0$, $k(x_0) = y_1$.

Then $\alpha(t) = H(x_0,t)$ is the path defined by $H$ from $y_0$ to $y_1$ and $\hat{\alpha} : \Pi_1(Y,y_0) \to \Pi_1(Y,y_1)$ then $k_* = \hat{\alpha}(h_*)$
```
##### Proof:
Consider $I \times I \xrightarrow{F} X \times I$ by concatenating: 
1. $(x_{0},1) \to (x_{0},t)$ path
2. loop $f$ in $X \times \{ t \}$
3. $(x_{0},t) \to (x_{0},1)$
for each $t \in I$.
$$
I \times I \xrightarrow{F} X \times I \xrightarrow{H} Y
$$
$H \circ F$ is a path homotopy from 
$$
\bar{\alpha}*(h \circ f)* \alpha  \ \ \ \ \text{to}  \ \ \ \ e *(k \circ f)*e
$$

### Lemma 3:
```ad-note
title:
If $r : X \to A$ is a deformation retract, $i : A \hookrightarrow X$ is the inclusion then $i_* : \Pi_1(A,x_0) \to \Pi_1(X,x_0)$ is an isomorphism.
```
##### Proof:
Let $H$ be the homotopy defined by the deformation retract, so that $H(x,0) = x$, $H(x,1) \in A$, $H(a,t) = a$, for all $a \in A$.
Then if $r : X \to A$ is the retraction and $i : A \to X$ is the inclusion.
Then $r_{*}\circ i_{*} = id_{\Pi_{1}(A)}$.
We know $i \circ r = H|_{X \times \{ 1 \}}$ is homotopic to $id_{X} = H|_{X \times \{ 0 \}}$. Therefore, $i_{*} \circ r_{*} = id_{\Pi_{1}(X)}$. Hence they are inverses of each other.


#### Examples:
1. $S ^{1}$ has the same $\Pi_{1}$ as $S ^{1} \times I$ the cylinder, mobius band, $B ^{2}\setminus \{ 0 \}, \mathbb{R}^{2} \setminus \{ 0 \}, S \times B ^{2}$
2. Figure eight space is a deformation retract of $\mathbb{R} ^{2} \setminus\{ 2 \ points \}$ and also of $S ^{1} \times S ^{1} \setminus \{ 1 \ point \}$.
3. The theta shape : $S ^{1} \cup (\{ 0 \} \times [-1,1]) \subseteq \mathbb{R}^{2}$. Also a deformation retract of $\mathbb{R}^{2} \setminus \{ 2 \ points \}$, so the $\Pi_{1}(\mathrm{figure \ eight}) = \Pi_{1}(\mathrm{\theta \ shape})$


---
# References
[[Retractions]]
[[Fundamental Group]]
[[Homotopy of paths]]
[[S^1]]

