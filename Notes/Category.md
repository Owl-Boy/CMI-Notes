---
tags:
  - Note
  - Incomplete
---
202410070210

Tags : [[Category Theory]]
# Category
---
A *Category* consists of: 
- A collection of objects
- A collection of morphisms
so that:
- Each morphism has specified domain and co-domain objects
	- The notation $f:X \to Y$ states that the morphism $f$ has the co-domain $X$ and the domain $Y$.
- Each object has a designated *identity morphism* : $1_{X}:X\to X$
- For each pair of morphism $f,g$ for which the co-domain of $f$ is equal to the domain of $g$ i.e:
$$
f: X \to Y, \quad g: Y \to Z\quad\quad \rightsquigarrow\quad\quad gf : X \to Z
$$
This data is subject to the following axioms:
- For any morphism $f:X\to Y$ we have $1_{X}f=f 1_{Y}=f$.
- Compositions of morphism is associative

---
# References 
[[Examples of Categories]]