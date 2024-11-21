---
tags:
  - Note
  - Incomplete
---
202411121911

Tags : [[Category]]
# Functors
---
>[!quote] John Baez "Quantum Quandries: A Category-Theory Perspective"
>... Every sufficiently good analogy is yearning to become a functor.


>[!definition]
>A *Functor* $F : C \to D$, between categories $C$ and $D$ consists of the following objects
>- An object $Fc\in D$, for each $c\in C$.
>- A morphism $F f: Fc \to Fc'$ for each morphism $f: c \to c'$, so that the domain and codomain of $Ff$ are equal to $F$ applied on domain and codomain of $f$ respectively
>These objects need to satisfy the following *functoriality axioms*
>- For any composable pair $f, g$ in $C$, $Fg \cdot Ff =F(g \cdot f)$
>- For each object $c$ in $C, F(1_{c})=1_{F_{c}}$.

>[!lemma]
>Functors preserve isomorphism





---
# References
[[Examples of Functors]]