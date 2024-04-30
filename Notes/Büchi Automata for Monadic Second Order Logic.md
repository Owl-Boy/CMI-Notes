---
tags:
  - Note
aliases:
  - Buchi's Theorem
---
202402271202

Tags : [[Logic]], [[Automata Theory]]
# Büchi Automata for Monadic Second Order Logic
---
 >[!faq] Why
 >Automata theoretic approaches work really well with model checking problems which inherently belong to the domain for Logic. This is the first example of Automata being used to decide whether a logical formula is satisfiable for not.
  
Automata and regular expressions verify a logical formula over a string, hence we need a logic over Strings and we build an automata that runs on the string as defined [[Strings in Logic|here]].
Given a Monadic Second Order Logic we will construct a Büchi Automata. Starting with the innermost subformulae and building up to the entire sentence.

 ---
## Büchi's Theorem
>[!theorem] Büchi's Theorem
>A language is $\omega$-regular if and only if it is definable in monadic second order logic. 
>Furthermore, there are algorithms associating every Büchi Automata $\mathfrak A$ with an MSO formula $\varphi$ such that $L(\mathfrak A)=L(\varphi)$ and vice versa
### Forward Direction
This part is easy, we just simulate a Büchi Automata in Second order logic.
Let $\mathfrak A= \{ S, \Sigma, s_{I}, \Delta, F \}$. Assume $S=[m]$ and $S_I=1$ Then the following sentence defines the language recognized by $\mathfrak A$:
$$
\varphi := \exists X_{1}\dots \exists X_{m}(\text{unique} \land \text{init}\land \text{trans}\land \text{acc})
$$
Where $\text{unique, init, trans, acc}$ and $nonempty$ are the following formulas.
- The intended meaning of the set $X_s$ is the set of indices of the word where the automata is in the state $s$ before reading the letter at the position. The formula unique says that at each point the automata is in exactly one position : $$\text{unique}:=\forall x\left(\bigvee_{s\in[m]} X_{s}x \land \bigwedge_{1 \leq s<s'\leq m}(\lnot X_{s}x\land\lnot X_{s'}x)\right)$$
- The formula $\text{init}$ says that the run starts at the initial state:$$\text{init}:=\forall x(\forall y\ x\leq y \to X_{1}x)$$
- The formula $\text{trans}$ encodes the transition set $\Delta$: $$\text{trans}:=\forall x \forall y\left(\text{next }(x,y)\to\bigvee_{s,a,s'\in\Delta}(X_{s}x \land P_{a} x\land X_{s'}y)\right)$$ where the $\text{next}(x,y)$ is $x \leq y \land \nexists z(x\leq z \land z\leq y)$ 
- The formula $\text{acc}$ is the acceptance condition, which is that good states are visited infinitely many often. $$\text{acc}:=\forall x\exists y \left(x \leq y \land \lnot(x=y) \land \bigvee_{a\in F}P_{a} y\right)$$
### Backward Direction
This is the harder part. Here we have to make an automata for a given formula. Here we have the ability to quantify sets and points. That means while making automata for the subformulae, we would have to fix an interpretation for all the bound variables.

To make life easier, we assume that the formulas are in a Prenex-normal form, which is where all the quantifiers are in the beginning of the formula. Moreover the MSO quantifiers are mentioned before the FO quantifers.
>[!example] Prenex normal form
>$$
>\exists X \exists x \exists y(x\in X \land y \in X)
>$$
>is in prenex normal form while the following is not.
>$$
>\exists X (\exists x\ x\in X \land \exists y\ y\in X)
>$$

#### Dealing with Free Variables in Subformulae
- Monadic Second order variable
	- For each MSO quantifier $\exists X$ we change the language $\Sigma$ with $\Sigma\times \{ \top,\bot \}$. 
	- A given string in this alphabet gives us a string in the original alphabet and an interpretation for the MSO set, specifically the indices where the second component of the alphabet is $\top$ is exactly the set $X$ for an interpretation.
	- In the end the language will be $\Sigma\times \{ \bot, \top \}^n$ if there are $n$ quantified variables.
- First Order variables
	- We replace every First Order Quantifier with MSO quantifiers, this will be discussed in more detail in the section for Relations
	- The following gives the new of set formulas after getting rid of FO quantifiers
		- $\varphi := x \le y$ then $\varphi^*:=\text{le}(X, Y)$
		- $\varphi:=P_a x$ then $\varphi^*:=\text{symb}_{a}(X)$
		- $\varphi:= Z x$ then  $\varphi^*:=\text{sub}(X, Z)$
		- $\varphi:= \exists x\ \chi$ then $\varphi^*:=\exists X(\text{singl}(X) \land \chi^*)$
		- $\varphi := \forall x\ \chi$ then $\varphi^*:=\forall X(\text{singl}(X) \to\chi^*)$
		- $*$ distributes over MSO quantifier and propositional connectives

#### Logical connectives
Given automata $A, B$ for formulae $\varphi, \psi$. The formulae for applying the logical connectives to $\varphi$ and $\psi$ directly correspond to closure properties of [[Omega-Regular Languages]].
- $\varphi \land \psi$ has the automata $A\cap B$ 
- $\varphi \lor \psi$ has the automata $A\cup B$
- $\lnot\varphi$ has the complement of the automata for $A$.

#### Relations
Since we got rid for all first order quantification, we need to change the relations slightly before building automata for them. 

We will also add new relations which will be the only places where first order quantifiers will be used. This special use case is easy to deal with and build automata for.

- $\text{singl}(X) := \exists y(Xy \land \forall z(X z\to z=y))$
	- This formula says that the set $X$ has just $1$ element. I.E there will be exactly 1 index where where the component corresponding to $X$ will be $\top$.
	- This will be used along with an MSO existential quantifier to simulate FO quantification
	- ![[singl Buchi MSOL.excalidraw|200]]
- $\text{symb}_{a}(X):=\forall x(Xx \to P_{a}x)$
	- This formula says that whenever the component of the letter corresponding to $X$ will be $\top$, the first component will be $a$.
	- This will be used instead of $P_a$ directly
	- ![[symb Buchi to MSOL.excalidraw|300]]
- $\text{le}(X, Y) := \forall x, y((Xx \land Yy)\to x \leq y)$
	- This formula states that every element in $X$ is less that every other element in $Y$.
	- This will be used instead of $\le$ directly.
	- ![[le Buchi to MSOL.excalidraw|200]]
- $\text{sub}(X, Y):= \forall z(X z\to Yz)$
	- This formula states that $X$ is a subset of $Y$.
	- This will be used to simulate $x\in X$.
	- ![[Sub buchi to MSOL.excalidraw|170]]

#### Existential Quantifiers
We only deal with Existential quantifiers because universal quantifier can be written in terms of existential quantifiers in the following manners
$$
\forall x \varphi \iff \lnot \exists x(\lnot\varphi)
$$
Given an MSO formula $\varphi$ that has a free variable $X$ and an automata $A$ for that, we construct an automata for $\exists X\ \varphi$ by simply projecting the component corresponding to $X$ out of the alphabet. 

This can be interpreted as, whenever we check if a number belongs to the set and take a decision based on that, we will now pick both the options non-deterministically. If there will be an existing run, that decisions in that will correspond to the correct quantification of the set.

---
# References
[[Büchi Automata]]
[[Monadic Second Order Logic]]