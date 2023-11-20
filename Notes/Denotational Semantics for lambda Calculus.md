---
tags:
  - Note
---
202310201610

Tags : [[Lambda Calculus]]

---
# Denotational Semantics for Lambda Calculus

```ad-note
title:Denotational Semantics
*Denotational Semantics* is an approach for formalizing syntactic expressions by constructing mathematical objects that describe the meaning of an expression.
```

The purpose is to assign a _value_ to every _expression_ in the language.
Here
- An _expression_ is a syntactic object built using the rules of the language
- A *value* is a mathematical object

We define  the function $\mathbf{Eval}$ that takes *expressions* to *values*.

```ad-seealso
Here we use a variant to lambda calculus that contains some built in functions and constants.
```
---
## The $\textbf{Eval}$ function
We define $\mathbf{Eval}$ in the following way.

- We can define expressions that do not have a normal form, i.e expressions that do not terminate  as follows .
	- $\textbf{Eval}\textlbrackdbl\; E\;\textrbrackdbl =\; \perp$
- Given an expression $E$, we need to assign values to its free variables by defining an *environment* $\rho$ which has definitions for free variables
	- $\mathbf{Eval}\textlbrackdbl\; x\;\textrbrackdbl\;\rho =\rho\; x$
- Given an application of 2 expressions, we will have that the first expression will evaluate to a function, that takes in the evaluation of the second expression as an argument.
	- $\textbf{Eval}\textlbrackdbl \;E_{1}\;E_{2}\;\textrbrackdbl=(\textbf{Eval}\textlbrackdbl \;E_{1}\;\textrbrackdbl)\;(\textbf{Eval}\textlbrackdbl \;E_{2}\;\textrbrackdbl)\;$
- Given an abstraction, we can say that its evaluation is the same as the evaluation of the inner expression if we overwrite the definition of the bound variable with input that is supposed to be applied to the expression
	- $\textbf{Eval}\textlbrackdbl \;\lambda x.E\;\textrbrackdbl\;\rho\;a=\textbf{Eval}\textlbrackdbl\;E\;\textrbrackdbl\;\rho[x:=a]$
- We can sort of use a Haskell like syntax to give evaluation for built-in functions 
	- $\mathbf{Eval}\textlbrackdbl\;*\;\textrbrackdbl\; a\;b=a\times b$ 
		- Here we give the syntactic $*$ a corresponding mathematical object which is the multiplication function, although we need to complete the definition by adding all possible arguments

Considering all that we get the following definition for $\mathbf{Eval}$
$$
\begin{align*}
&\mathbf{Eval}\textlbrackdbl\;E\;\textrbrackdbl&&=\;\perp&&\text{If $E$ does not terminate}\\
&\mathbf{Eval}\textlbrackdbl\;x\;\textrbrackdbl\;\rho&&=\rho\;x&&\text{Defining by the enviroment}\\
&\mathbf{Eval}\textlbrackdbl\;E_{1}\;E_{2}\;\textrbrackdbl&&=(\mathbf{Eval}\textlbrackdbl\;E_{1} \;\textrbrackdbl)\quad(\mathbf{Eval}\textlbrackdbl\;E_{2} \;\textrbrackdbl)&&\text{Evaluate spearately}\\
&\mathbf{Eval}\textlbrackdbl\;\lambda x.E \;\textrbrackdbl\;\rho\;a&&=\mathbf{Eval}\textlbrackdbl\;E \;\textrbrackdbl\;\rho[x:=a]&&\text{Overwrite environment}\\
&\mathbf{Eval}\textlbrackdbl\;\text{Some inbuilt value}\;\textrbrackdbl&&&&\text{Defined like haskell}\\
\end{align*}
$$
Ideally the environment should always be mentioned, but I will not write it for clarity

---
# References
[[Lambda Calculus Syntax]]
[[Lambda Calculus Introduction]]
[[Enriched Lambda Calculus]]