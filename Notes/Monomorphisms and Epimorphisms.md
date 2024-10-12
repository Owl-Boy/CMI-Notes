---
tags:
  - Note
---
202410101910

Tags : [[Category Theory]]
# Monomorphisms and Epimorphisms
---
>[!definition]
>A morphism $f$ is called a *monomorphism* if for any parallel morphisms $h, k:w \rightrightarrows x$ we get $fh = fk \Rightarrow h=k$.
>
>A morphism $f$ is called a *epimorphism* if for any parallel morphisms $h, k: y \rightrightarrows z$ we get $hf = kf\Rightarrow h=k$.

A monomorphism or an epimorphism in a category $C$ correspond to an epimorphism and monomorphism in $C^\text{op}$.

In adjective form, we say that a morphism is either *monic* or *epic* to say that it is a monomorphism or an epimorphism respectively, denoted by $\rightarrowtail$ and $\twoheadrightarrow$.

>[!example] Special Case
>Suppose $x \xrightarrow s y \xrightarrow r x$ are morphisms so that $rs = 1_{x}$. Then $s$ is called a *right inverse* or *section* of $r$ and $r$ is called the *left inverse* or *retraction* of $s$. The object $x$ is called a *retract* of $y$ (also look [[Retractions]]).
>
>In this case $s$ is always a monomorphism and is called a *split-monomorphism* and dually, $r$ is always an epimorphism and is called a *split epimorphism*.


---
# References
[[Duality]]
[[Retractions]]
