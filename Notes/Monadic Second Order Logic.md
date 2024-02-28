---
tags:
  - Note
  - Incomplete
---
202402120102

Tags : [[Logic]]
# Monadic Second Order Logic
---

*Monadic Second Order Logic (MSO)* is an extension to [[First Order Logic]] that allows quantification over sets of elements in addition to individual elements. This also makes it a fragment of [[Second Order Logic]] which allows quantification over subsets of finite products of a universe (can also be thought of us non-unary relations).

It's called "monadic" because it only allows quantification over unary predicates (sets).

Since it subsumes [[First Order Logic|FO]], it is *undecidable*

## Grammar
$$
\begin{matrix}
\phi & := & \lnot \phi & | &\phi \land \phi & |&\phi \lor \phi & | & \phi \implies \phi \\
& |& \forall x. \phi & | & \forall X.\Phi & |&\exists x.\phi & | & \exists X.\phi  \\
 & | & t=t & |  & r(t\dots t) & |  & X(t) \\
\end{matrix}
$$
where $x$ is a first order quantified variable and $X$ is a second order quantified variable and 
$$
\begin{matrix}
t & := & x & | & f(t\dots t)
\end{matrix}
$$

## Example
$$
\exists X \left( \forall x \, (X(x) \rightarrow \exists Y \, (Y(x) \land \forall y \, (Y(y) \rightarrow (x = y))) \right)
$$
This formula states that
	There exists a set $X$ such that, for element of the set, there is a singleton set $Y$ that contains it.

This formula is not definable in [[First Order Logic|FO]] as it talks about sets.
This example also shows that *MSO* is **more expressible** than *FO*.

---
# References
[[Büchi Automata for Monadic Second Order Logic]]