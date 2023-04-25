202304171104

Type : #Note
Tags : [[Algebra]]

---
# The fundamental theorem of Galois Theory
### Theorem 1 (Artin):
```ad-note
title:
Let $E$ be a field and $H$ be a finite group of automorphisms of $E$. If $[E : E^H]$ is finite then $E /E^H$ is a galois extension and $\mathrm{Gal}(E/E^H) = H$
```

##### Proof:
Take $\alpha \in E$, let $S_{\alpha} := \{ \sigma(\alpha) : \sigma \in H \}$.
Let $h_{\alpha}(X) = \prod \limits_{\beta \in S_{\alpha}} (X-\beta)$. The coefficients of $h_{\alpha}$ are in $E^H$, since applying any $\sigma \in H$ to $h_{\alpha}$, we get $h_{\alpha}$ itself.
Now take any $f \in E ^{H}[X]$ with $\alpha$ as a root, we can see that $\sigma(\alpha)$ is also a root of $f$ for all $\sigma$, hence $h_{\alpha} | f$. Thus, $h_{\alpha}$ is the min poly of $\alpha$ over $E ^{H}$, with $deg(h_{\alpha})\le |H|$.
Thus $E /E ^{H}$ is a separable and normal extension. Thus, $E /E ^{H}$ is galois (since it is finite as well).

Now since $E /E ^{H}$ is separable, by Primitive element theorem, $E = E ^{H}(\alpha)$.
Now, $|\mathrm{Gal}(E /E ^{H})| = [E : E ^{H}] =[E ^{H}(\alpha): E ^{H}] = \mathrm{deg}(h_{\alpha}) = |S_{\alpha}| \le |H|$.
But $H \le \mathrm{Gal}(E /E ^{H})$, hence $H = \mathrm{Gal}(E /E ^{H})$.

### Theorem 2 (Artin):
```ad-note
title:
Let $E$ be a field and $H$ be a finite group of automorphisms of $E$. Then $[E:E^H]$ is finite.
```
##### Proof:
From the proof of theorem 1 above, we know that $\alpha$ is separable over $E ^{H}$ for all $\alpha \in E$, with degree bounded by $|H|$.
Let $\alpha$ be such that $[E^H(\alpha) : E^H]$ be maximum. We claim that $E^H(\alpha) = E$, this will finish the proof.
Let $\beta \in E$, then $E ^H(\alpha,\beta)$ is separable over $E^H$ since both $\alpha$ and $\beta$ are.
Hence by primitive element theorem, $E^H(\alpha,\beta) = E^H(\gamma)$ whose degree over $E^H$ is at most $[E^H(\alpha): E^H]$. Which gives $[E^H(\alpha ,\beta) : E^H] = [E^H(\alpha) : E ^{H}] \implies E ^{H}(\alpha ,\beta) = E^H(\alpha)$. Thus, $\beta \in E^H(\alpha)$ for all $\beta \in E$, hence $E = E^H(\alpha)$.

### Theorem 3 (Galois):
```ad-note
title:
Let $L /K$ be a finite Galois extension with $G = \mathrm{Gal}(L /K)$. Then the mappings $F \mapsto \mathrm{Gal}(L /F)$ and $H \mapsto L^H$ are inverses of each other and satisfy the following properties when $H$ and $F$ correspond:
1. $|H| = [L:F]$ and $[F:K] = [G:H]$
2. two intermediate fields $F$ and $F'$ with corresponding subgroups $H$ and $H'$ are isomorphic over $K$ iff $H$ and $H'$ are conjugate subgroups of $G$.
3. $F /K$ is galois iff $H$ is a normal subgroup of $G$, and $\mathrm{Gal}(F/K) \cong G/H$.
```
##### Proof:
To show that the mappings in question are inverses of each other, we need to show that $F ^{\mathrm{Gal}(L /F)} = F$ and $\mathrm{Gal}(L /L ^{H}) = H$.
The first equality follows from the theorem 3 and theorem 1 of [[Galois Extensions]].
The second equality follows from theorem 1 and 2 above.

1. $[L : L ^{H}] = |\mathrm{Gal}(L /L ^{H})| = |H|$ (By theorem 1 above). 
   $[G:H] = |G| /|H| = [L : K] /[L:L ^{H}] = [L ^{H} : K] = [F : K]$.
2. First we show that $F$ and $F'$ are $K-$isomorphic iff $F' = \sigma(F)$ for some $\sigma \in G$.
   Note that if $F' = \sigma(F)$ then the restriction of $\sigma$ to $F$ is the required isomorphism between them.
   Now suppose $\phi : F \to F'$ is a $K$ isomorphism. Since $F /K$ is separable, by primitive element theorem, we get $F = K(\gamma)$. Since $\phi$ fixes $K$, $\phi(\gamma)$ is a conjugate of $\gamma$ over $K$. So by theorem 4 of [[Galois Correspondence]], we get $\phi(\gamma) = \sigma(\gamma)$. Since $\sigma$ and $\phi$ agree on $K$ and $\gamma$, they agree on $F$, and hence $\phi = \sigma|_{F}$ so $F' = \phi(F) = \sigma(F)$.
   
   Now for all $\tau \in G$, we get 
$$
\begin{align*}
\tau \in \mathrm{Gal}(L /\sigma(F)) &\iff \tau(\sigma(a)) = \sigma(a) \ \forall \ a \in F \\ 
&\iff \sigma^{-1}(\tau(\sigma(a))) = a \ \forall \ a \in F \\
&\iff \sigma^{-1}\tau \sigma \in \mathrm{Gal}(L /F) \\
&\iff \tau \in \sigma H \sigma^{-1}
\end{align*}
$$
This gives us $H' = \sigma H \sigma^{-1}$.

3. Since $F /K$ is separable, it is galois iff it is normal. But the $K-$conjugates of any element in $F$ are its orbit under $\mathrm{Gal}(L /K)$, hence $F /K$ is normal iff $\sigma(F) \subset F$ for all $\sigma \in G$. Since $\sigma(F)$ and $F$ have the same degree over $K$, the inclusion holds iff equality holds. So
$$
\begin{align*}
F /K \text{ is normal} &\iff \sigma(F) = F \ \forall \ \sigma \in G \\ 
& \iff \sigma H \sigma^{-1} = H \ \forall \ \sigma \in G\\ 
& \iff H \triangleleft G
\end{align*}
$$
   Now restricting elements in $\mathrm{Gal}(L /K)$ to $F$ defines a map from $\mathrm{Gal}(L /K) \to \mathrm{Gal}(F /K)$. The kernel of this map is obviously $\mathrm{Gal}(L /F)$. This gives an injection $\mathrm{Gal}(L /K) /\mathrm{Gal}(L /F) \hookrightarrow \mathrm{Gal}(F /K)$, the domain has size $[G : H] = [F : K] = |\mathrm{Gal}(F /K)| =$ size of codomain. Hence, the above injection is a surjection too and $\mathrm{Gal}(F /K) \cong \mathrm{Gal}(L /K) / \mathrm{Gal}(L /F)$.
   
### Theorem:
```ad-note
title:
Let $L/K$ be finite Galois and $F$ and $F'$ be intermediate fields with corresponding subgroups $H$ and $H'$.
(a) $\mathrm{Gal}(L /FF') = H \cap H'$ and $\mathrm{Gal}(L/F \cap F') = \langle H, H'\rangle$, where $\langle H, H'\rangle$ denotes the subgroup of $\mathrm{Gal}(L/K)$ generated by $H$ and $H'$. 

(b) $F \subset F'$ if and only if $H' \subset H$, in which case $[F' : F] = [H : H']$. 
```
##### Proof. 
For (a), we use the inclusion-reversing nature of the Galois correspondence. The composite field $FF'$ is the smallest field containing both $F$ and $F'$ in $L$, so its corresponding subgroup $\mathrm{Gal}(L/FF ')$ is the largest subgroup of $\mathrm{Gal}(L/K)$ contained in $H$ and $H'$, so it is $H \cap H'$. 

The argument for the other equation is similar. For (b), the equivalence of the inclusions comes from the Galois correspondence. Moreover, we then have $[F': F] = [L : F]/[L : F'] = |H|/|H'| = [H : H']$. 

---
# References
[[Primitive Element Theorem]]
[[Separable Extensions]]
[[Normal Extensions]]
[[Galois Extensions]]
[[Galois Correspondence]]
