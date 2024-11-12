---
tags:
  - Note
  - Incomplete
---
202411112311

Tags : [[Monoid Theory]]
# Ideals in a Monoid
---
>[!definition]
>Given a monoid $\mathcal M = \langle M, *, 1\rangle$, an ideal $I \subsetneq M$ is a set of elements such that, if any element is multiplied to $I$, the result remains inside $I$, i.e
>$$
>M * I * M = I
>$$

If one gives a [[Preorder]] on Monoids of the form $a \leq b$ iff $\exists y,z(y*a*z=b)$, that is, things can be multiplied to $a$ to get $b$, then Ideal become all downward closed set. Thus we get the following

>[!lemma]
>Given two ideals $I_{1}, I_{2}$ the set $I_{1} \cap I_{2}$ is an ideal and is necessarily non-empty

The set is an ideal because it will also necessarily be downward closed. It will be non-empty because $I_{1} * I_{2} \subset I_{1} \cap I_{2}$.

Also if the monoid contains a co-unit element $0$ then the singleton containing that will also be an ideal.

---
# References
[[Forbidden Ideal of an element in a Monoid]]
[[Monoids]]