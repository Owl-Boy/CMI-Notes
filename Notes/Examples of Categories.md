---
tags:
  - Example
---

202410070303

tags : [[Category Theory]]

#  Examples of Categories
---
A family of mathematical objects assemble together along with the relations between  them to form a category, these are broadly of two times

## Concrete 
A category is called concrete if the members of the family it wants to represent are represented by its object, like:
- $\mathbf{Set}$ has sets as its objects and functions, with specified domain and co-domain as its morphisms
- $\mathbf{Top}$ has [[Topological Spaces]] as its objects and continuous functions as its morphisms
- $\mathbf{Set}_{*}$ and $\mathbf{Top}_{*}$ have pointed sets and pointed topological spaces as its objects and continuous functions that take one special point to another as its morphisms
- $\mathbf{Group}$ has [[Groups]] as its objects and Group Homomorphisms as its morphisms
- $\mathbf{Ring}$ has [[Ring|Rings]] as objects and [[Ring Homomorphism]] as morphisms
- $\mathbf{Field}$ as [[Fields]] as its object and Field Homomorphisms as morphisms
- $\mathbf{Mod}_{R}$ has modules over the ring $R$ as its object and module homomorphisms as its morphisms.
- $\mathbf{Meas}$ has [[Measure of a Set|Measureable Spaces]] as objects and [[Measurable Functions]] as morpisms
- $\mathbf{Graph}$ has Graphs as objects and graph homomorphisms as morphisms
- $\mathbf{Man}$ has smooth manifolds as objects and smooth functions as morhpisms
- $\mathbf{Poset}$ has Partially Ordered Sets as morphisms and monotonous functions as homomorphisms

And more...

## Abstract Categories
These are categories where mathematical objects aren't directly encoded as objects of a category, for example:

- For a ring $R$, the category $\mathbf{Mat}_{R}$ has natural numbers as objects and matrices over $R$ as morphisms where a matrix $M$ of order $a \times b$ is represented as $f_{M}:a \to b$, and compositions represents matrix multiplication.
- A group $G$ is defined by the category $\mathbf{BG}$ where there is just one object and each element of the group is a morphism and product between elements is represented by composition
- A poset $(P, \leq)$ can be represented by a category where $P$ can be the set of objects and there is a morphism from $x \to y$ iff $x \leq y$.
- Any set can be represented by a category where the sets is the collection of objects and the morphisms are the identity morphisms.
- $\mathbf{Htpy}$ has topological spaces are objects but homotopy classes as morphisms.

---
# Related
