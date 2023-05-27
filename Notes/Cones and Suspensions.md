202304121804

Type : #Note
Tags : [[Topology]]

---
# Cone
### Definition:
```ad-note
title:
The (unreduced) cone is defined to be the quotient space $$
\tilde{C}X := (X \times I)/(X \times \{1\})
$$
```
Let $j_{X} : X \to \widetilde{C}X$ by sending $x \to [(x,0)]$ where we use [] to denote equivalence classes in the quotient space $\widetilde{C}X$.

### Lemma 1:
```ad-note
title:
$\widetilde{C}X$ is a contractible space.
```
##### Proof:
We can contract $\widetilde{C}X$ to its vertex via the straight line homotopy $$
F_{s}([x,t]) := [x,(1-s)t+s]
$$
### Lemma 2:
```ad-note
title:
$j_X$ is a closed embedding
```
##### Proof:
Take a closed set $U$ in $X$, $j_{X}(U)$ is closed in $j_{X}(X)$ but $j_{X}(X)$ is closed in $\widetilde{C}X$, hence $j_{X}(U)$ is closed in $\widetilde{C}X$.

### Lemma 3:
```ad-note
title:
A map $f : X \to Y$ is null homotopic iff it extends over $\widetilde{C}X$.
```
##### Proof:
If $f$ is null homotopic, then there is a homotopy $H : X \times I \to Y$ to a constant map $c(x) := y_{0}$. Then $H_{1}(X) \subseteq \{ y_{0} \}$, so that the homotopy factors through the quotient $X\times I /X \times \{ 1 \}$ to give a map $\widetilde{f} : \widetilde{C}X \to Y$ that satisfies $\widetilde{f}\circ j_{X} = H_{0} = f$.
The 


---
# References
