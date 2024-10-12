---
tags:
  - Note
  - Incomplete
---
202402121502

Tags : [[coq]]
# WHILE programs
---
While Programs are a stripped down version of C that we will be verifying using hoare logic

## Syntax
### Arithmetic Expressions
$$
\begin{matrix}
e & ::= & n & | & x & | & e+e & | & e-e & | & e*e & | & e / e
\end{matrix}
$$
### Boolean Expressions
$$
\begin{matrix}
b  & ::= & e=e & | & e \neq e & | & e \leq e & | & e \geq e \\
 & | & \lnot b & | & b \land b & | & b \lor b & | & \top\;\;|\;\perp
\end{matrix}
$$

### Commands
$$
\begin{matrix}
 &  & \text{(identitiy)} &  & \text{(assign)} &  & \text{(sequencing)} \\
c  & ::= & \text{SKIP} & | & x := e & | & c;c &  \\
 & | & \text{if }b \text{ then }c \text{ else }c & | & \text{while }b \text{ do } c \text{ end }
\end{matrix}
$$
## Semantics
### State
This is a total(or partial) function from expressions to different domains, like $\mathbb{N}$ for arithmetic expressions and $\mathbb{B}$ for boolean expressions.

Informally it is the collection of values and the program counter at any point during the execution of the program.

The way we deal with the semantics of the program evolving is by giving a relation between the 'pre-state' and 'post-state' of each expression.o
### Semantics for Expressions
This is done in the obvious manner
$$
\begin{align}
[\![n]\!]s &= n \\
[\![e_{1}+e_{2}]\!]s &= [\![e_{1}]\!]s + [\![e_{2}]\!]s \\
[\![e_{1}*e_{2}]\!]s &= [\![e_{1}]\!]s * [\![e_{2}]\!]s \\
[\![e_{1}-e_{2}]\!]s &= [\![e_{1}]\!]s - [\![e_{2}]\!]s \\
\left[ \![e_{1} / e_{2}]\! \right]s &= 
[\![e_{1}]\!]s / [\![e_{2}]\!]s & \text{if $e_{2}$ is not $0$}
\end{align}
$$

### Semantics for Command
These are supposed to be functions from states to states.
#### Big Step Semantics
$$
\begin{align}
s -\!\!\![\text{SKIP}]\!\!\!\rightarrow s &&\text{Identitiy}
\end{align}
$$
$$
\begin{align}
\frac{[\![e]\!]s = n}{s-\!\!\![x:= e]\!\!\!\rightarrow s[x \mapsto n]}&& \text{Assignment}
\end{align}
$$
$$
\begin{align}
\frac{s -\!\!\![c_{1}]\!\!\!\rightarrow s_{1}\quad\quad s_{1} -\!\!\![c_{1}]\!\!\!\rightarrow s_{2}}{s_{1} -\!\!\![c_{1};c_{2}]\!\!\!\rightarrow s_{2}}&&\text{Sequencing}
\end{align}
$$
$$
\begin{align}
\frac{[\![b]\!]s = \top \quad\quad s-\!\!\![c_{1}]\!\!\!\to s'}{s -\!\!\![\text{if }b \text{ then }c_{1} \text{ else }c_{2}]\!\!\!\to s'}&&\text{If-true}
\end{align}
$$
$$
\begin{align}
\frac{[\![b]\!]s = \bot \quad\quad s-\!\!\![c_{2}]\!\!\!\to s'}{s -\!\!\![\text{if }b \text{ then }c_{1} \text{ else }c_{2}]\!\!\!\to s'}&&\text{If-false}
\end{align}
$$

$$
\begin{align}
\frac{[\![b]\!]s = \top \quad\quad s-\!\!\![c_{1}]\!\!\!\to s'\quad\quad s'-\!\!\![\text{while }b \text{ do }c_{1}]\!\!\!\to s''}{s -\!\!\![\text{while }b \text{ do }c_{1}]\!\!\!\to s''}&&\text{While-true}
\end{align}
$$
$$
\begin{align}
\frac{[\![b]\!]s = \bot}{s -\!\!\![\text{while }b \text{ do }c_{1}]\!\!\!\to s}&&\text{While-true}
\end{align}
$$
#### Small Step Semantics
$$
\begin{align} \\
\langle \epsilon,s\rangle &\to s \\
\langle \text{SKIP};\rho, s\rangle &\to \langle \rho,s\rangle \\
[\![e]\!]s=n\Big|\langle x := n;\rho, s\rangle&\to\langle\rho, s[x \mapsto n]\rangle \\
\langle (c_{1};c_{2};)\rho, s\rangle &\to \langle c_{1};(c_{2};\rho), c\rangle \\
[\![b]\!]s = \top\Big|\langle \text{if }b\text{ then }c_{1}\text{ else }c_{2};\rho,s\rangle &\to \langle c_{1};\rho, s\rangle \\
[\![b]\!]s = \bot\Big|\langle \text{if }b\text{ then }c_{1}\text{ else }c_{2};\rho,s\rangle &\to \langle c_{2};\rho, s\rangle \\
[\![b]\!]s=\bot \Big|\langle\text{while }b\text{ do }c;\rho,s\rangle &\to \langle \rho, s\rangle\\
[\![b]\!]s=\top \Big|\langle\text{while }b\text{ do }c;\rho,s\rangle &\to \langle c;\text{while }b\text{ do }c; \rho, s\rangle
\end{align}
$$

---
# References
