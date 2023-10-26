---
tags:
  - Note
---
202309211509

Tags : [[Logic]]

---
# Semantics of First Order Logic
To give meaning to our formulas, we first fix a set $S$, which we call the **Universe**. And we then interpret our formulas in terms what we have in the universe. To do that we have an interpretation function $\iota$. Together they make a **First Order Structure**.

```ad-quote
title:History: Tarskian Semantics
In 1935, Alfred Tarski attempeted for formulate a new theory of _Truth_ in order to resolve the Liar's paradox.

The idea to formulate linguistic theoreis without paradoxes like the Liar's paradox, it is generally necessary to distinguish the language that one is talking about (Semantics/object language) with the language one is using to talk (Syntax/ metalanguage).

Tarski's thoery of truth demanded that the object language must be contained in the meta language. For example 
- 'Snow is white' is true if and only if snow is white.
seem trivial because the object language is the same as the metalanguage and is called a 'T' sentence.
- 'Schnee ist weiß' is true if and only if snow is white.
has its object language is German, and metalanguage is English. 

The original formulation involved in inductive definition and only applied to formal languages, like **First Order Logic**.
```


## First Order Structures
Given a [[Syntax of First Order Logic#First Order Languages|First Order Language]] $L$, A **First Order Structure** $L$ is a pair $\mathcal M=(S,\iota)$ where $S$ is a _non-empty_ set and $\iota$ a function defined over $R\sqcup F\sqcup C$ such that
- For each relation symbol $r\in R$ with arity $n$, we have $\iota(r)\subseteq S^{n}$
- For each function symbol $f\in F$ with arity $n$, we have $\iota(f):S^{n}\to S$
- For each constant $c\in C$ we have $\iota(c)\in S$.

For more readability we denote $\iota(x)$ as $x^{\mathcal M}$. That we have enough structure for our **First Order Formulas** we can build an interpretation for it. This corresponds to *Evaluations* for propositional logic

## Interpretation
An **Interpretation** of $L$ is the tuple $\mathcal I=(\mathcal M,\sigma)$ where $\mathcal M$ is a **First Order Structure** and $\sigma:Vars\to S$ is an assignment of elements of $S$ to variables.

Given any $\sigma$, we denote by $\sigma[x_{1}\to s_{1},\dots x_{n}\to s_{n}]$ the modified assignment $\sigma'$ where 
$$
\sigma'(x) = \left\{
\begin{align*}
\text{corresponding }s_{i}&&x\in\{x_{1},x_{2}\dots x_{n}\}\\
\sigma(x) &&\text{otherwise}
\end{align*}
\right.
$$
Similarly $\mathcal I[x\to s]=(\mathcal M,\sigma[x\to s])=I'$

Now, Given an interpretation $\mathcal I$, each term $t$ over $L$ maps to a unique element in $S$.
- If $t$ is a constant $c\in C$, $t^{\mathcal I}=c^{\mathcal M}$.
- If $t$ is a variable $x\in Var$, $t^{\mathcal I}=\sigma(x)$
- If $t$ is of the form $f(t_{1}, t_{2}\dots t_{n})$ where $f\in F$, then $t^{\mathcal I}=f^{\mathcal M}(t_{1}^{\mathcal I},t_{2}^{\mathcal I}\dots t_{n}^{\mathcal I})$

## Satisfactory Interpretation
A **Satisfactory Interpretation** corresponds to *Satisfying valuation* for *propositional logic*.
We say $\mathcal I\models \varphi$ ($\mathcal I$ satisfies $\varphi$) if
- $\mathcal I\models t_{1}\equiv t_{2}$ if $t_{1}^{\mathcal I} = t_{2}^{\mathcal I}$
- $\mathcal I\models r(t_{1}\dots t_{n})$ if $(t_{1}^{\mathcal I}\dots t_{n}^{\mathcal I})\in r^{\mathcal M}$
- $\mathcal I\models\lnot\varphi$ if $\mathcal I\not\models\varphi$
- $\mathcal I\models \varphi\lor\psi$ if $\mathcal I\models\varphi$ or $\mathcal I\models\psi$
- $\mathcal I\models \exists x\ \varphi$ if there is an element $s\in S$ such that $\mathcal I[x\to s]\models\varphi$ 

And as usual, we say a formula is _satisfiable_ if there exists a satisfactory interpretation for it. And a formula is *valid* if all Interpretations satisfy it.

## Free Variables
The _Quantifiers_ change the behavior of variables they interact with. For both $\exists$ and $\forall$ the variables they "bind" become independent of the **Interpretation**. Hence for any Interpretation $(\mathcal M, \sigma)$, $\sigma$ needs to only assign to the free variables. We build a function $FV$ that gives the set of free variables in a formula, it can be defined as
- If $\varphi$ is the atomic formula $r(t_{1}\dots t_{n})$ $FV(\varphi)$ is the set of variables in $\{t_{1}\dots t_{n})\}$
- If $\varphi$ is $t_{1}\equiv t_{2}$ then $FV(\varphi)$ is the set of variables in $\{t_{1}, t_{2}\}$
- $FV(\varphi) = FV(\lnot\varphi)$
- $FV(\varphi\lor\psi)=FV(\varphi)\cup FV(\psi)$
- $FV(\exists x\ \varphi)=FV(\varphi)\setminus \{x\}$

And Considering them we have the following:
If $\sigma$ and $\sigma'$ agree on $FV(\varphi)$ then $(\mathcal M,\sigma)\models \varphi$ iff $(\mathcal M,\sigma')\models \varphi$

## Logical Consequence
**Logical Consequence** has the same meaning as that in *Propositional logic*. Given a set $X$ of first order equations. We say $X\models \varphi$ if for every $\mathcal I$ such that $\mathcal I\models X$ we have $\mathcal I\models \varphi$.

---
# References
[[First Order Logic]]
[[Syntax of First Order Logic]]