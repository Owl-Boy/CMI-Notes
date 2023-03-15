202303150503

Type : #Note
Tags : [[Lambda Calculus]]

---
# Church Numerals
The most common way of defining numerals in lambda calculus is the definition given by *Alonzo Church*, which is also called the **Church Numerals**, which are defined as repeated application of a function of a value.

The Church Numerals are defined as 
$$
\begin{aligned}
0&= \lambda fx.x\\
1&= \lambda fx.f\ x\\
2&= \lambda fx.f\ (f\ x)\\
3&= \lambda fx.f\ (f\ (f\ x))\\
&\vdots
\end{aligned}
$$

We can define a $\text{SUCC}$ function which finds the successor of a given church numeral by 
$$\text{SUCC}:=\lambda\;nfx.\;f(n\;f\;x)$$

which add one $f$ behind the chain of applied $f$s

We can define $ADD$ function by composing $m$ compositions of $f$ with $n$ compositions of $f$ to get a $m+n$ composition of $f$s as
$$ADD:=\lambda \;mnfx.\; m\;f\;(n\;f\;x)$$
Or it can be defined as applying the $\text{SUCC}$ function $m$ times on $n$ as 
$$\text{ADD}:=\lambda\;mn.\;m\;\text{SUCC}\;n$$

We can define Multiplication as repeated addition as
$$\text{MULT}:=\lambda\;mn.\;m\;(\text{PLUS }n)\;0$$
Exponentiation is rather easy
$$
\text{EXP}:=\lambda mn.\; n\;m
$$
The predecessor function $\text{PRED}$ is rather complicated but will be simplified using [[Pairs in Lambda Calculus|pairs]].
for now, lets say it exists
Then we can define subtraction as
$$SUB:=\lambda \;mn.\;n\text{ PRED }m$$

---

# References
[[Church Booleans]]