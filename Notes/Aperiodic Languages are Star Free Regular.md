---
tags:
  - Note
  - Incomplete
---
202411120011

Tags : [[Algebraic Automata Theory]]
# Aperiodic Languages are Star Free Regular
---
Using the Lemmas defined below;
- If $M$ is singleton, then only languages are $\emptyset$ and $\Sigma^*$
- There is only one aperiodic monoid of size 2, and the  only languages possible to accept using that are $A^*$ or its compliment where $A\subset \Sigma$. 
- For induction step, since star free languages are closed under union, we show for $L=h^{-1}(x)$ for some $x$.
	- if $x=0$ then we are done, we quotient the rest by $F(0)$
	- otherwise we find a $y$ such that $F(y)$ contains 2 more elements than $F(x)$ (by applying the final lemma twice) and $h^{-1}(x)$ can be descibed as star free expressions on these and other languages that can be described using smaller monoids. But $h^{-1}(y)$ can be recognized by a smaller monoid $H \setminus F(y)$
	- So we can write $h^{-1}(x)$ as a star-free regular language by induction


>[!lemma]
>For any $x$ in an aperiodic monoid, if $x = pxq$ then $x=px$ and $x=xq$. 

This is because there is an $N$ such that $a^N=a^N+1$ for all $a\in M$. So consider $p^Nxq^N=x$, now left multiplication by $p$ and $q$ can be factored trivially.

>[!lemma]
If there is a monoid $M$ and an ideal $I$ then there is a natural monoid $M \setminus I \cup \{ 0 \}$ which is a quotient. So if a language is recognized by $M$ as $h^{-1}(I)$ then it w ill be recognized by $M'$ as $g^{-1}(0)$.

If given a monoid $\mathcal M$, and a language that is recognized as $h^{-1}(x)$ for some element $x$, the language can be recognized by a smaller monoid as one can quotient by $F(x)$ which is its [[Forbidden Ideal of an element in a Monoid|Forbidden Ideal]].

>[!lemma]
>If $L = h^{-1}(I)$ for some ideal in $M$ then $L$ can be expressed using star-free expressions involving languages recognized by smaller monoids.

If $I=\emptyset$ then the language is empty and can be recognized by the trivial monoid.

If $|I| > 1$ then one can quotient the monoid by $I$ to get a smaller monoid that accepts the language.

otherwise let $A = \{ a\in \Sigma :\!\!|\!\!: h(a) \in I \}$, and let $L_{a} = \Sigma^* a \Sigma^*$, now we wanna cover the words in $L'=L \setminus \sum_{a\in A} L_{a}$.

Pick $w\in L$ and let $u$ be the minimal substring of $w$ in $L$.
- if $u = \epsilon$, then $1\in I$ so $M=I$ and language is $\Sigma^*$
- if $u = a$ the $w\in L_{a}$
- let $u = avb$ where $v$ is a word and let $y=h(n)$
	- The minimality states that neither $h(a)*y$ nor $y*h(b)$ are in $I$
	- $h(w_{1})*h(a)*y*h(b)*h(w_{2})\in I$ so $w_{1}avbw_{2}\in L$
	- So if $h^{-1}(y)$ can be described using smaller monoids we will be done.
	- Since $y\notin I, I \subseteq F(y)$ so there is at least 1 element in $F(y)$. If there is exactly 1 element in $F(y)$ then it is the 0 element so we have $h(a)*y=y$ but that would mean $y*h(b)$ is in $I$ which is a contradiction, so we are done. 
	- Now since the monoid is finite, one can describe the language as a union of finitely many tuple $(a,y, b)$ where $|F(y)| >1$. So we are done.

>[!lemma]
>$x= (Mx \cap xM) \setminus F(x)$

If $y$ is in the above language, $y = px = xq$ and $x = ayb$ then $y=aybq$. So $y=ay$ and similarly $y=yb$ so $y=ayb=x$.

>[!theorem]
>If $x\in M$ and is not idempotent. Then there exists $Y\subset M$ such that forall $y\in Y, F(x) \subsetneq F(Y)$ and $h^{-1}(x)$ can be represented as a star-free expression on  $h^{-1}(y)$ and other languages definable by smaller monoids.





---
# References
