202303150403

Type : #Note
Tags : [[Lambda Calculus]]

---
# Church Booleans
By convention, the defintions of `TRUE` and `FALSE` used (also called **Church Booleans**) is 
$$
\begin{align*}
\text{TRUE}&:= \lambda xy.x\\
\text{FALSE}&:= \lambda xy.y
\end{align*}
$$
and with these two defintions, we can definte the following logical opeators easily
$$
\begin{align*}
\text{AND} &:= \lambda ab.aba\\
\text{OR} &:= \lambda ab.aab\\
\text{NOT} &:= \lambda p. p \text{ (FALSE)  (TRUE)}
\end{align*}
$$

This can now be used in defining *predicates*, which are functions that return a boolean value. For example the $\text{ISZERO}$ predicate, which returns $\text{TRUE}$ if an input number is then [[Church Numerals]] $0$ and returns $\text{FALSE}$ otherwise, can be written as
$$
\text{ISZERO} := \lambda n.n\; (\lambda x.\text{ FALSE })\; \text{ TRUE} 
$$
and the *predicate* $\text{LEQ}$ 
$$
\text{LEQ} := \lambda mn. \text{ ISZERO } (\text{ SUB }m\;n)
$$
where $\text{SUB}$ is defined in [[Church Numerals]]

---
# References
[[Church Numerals]]