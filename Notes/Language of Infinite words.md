---
tags:
  - Note
---
202401041201

Tags : [[Automata Theory]]
# Language of Infinite words
---
An Infinite word is an infinite sequence of letters

>[!note] Useful Notation
>- $\omega$ is used to denote infinite words.
>- $\Sigma^\omega$ is the set of all infinite words over the alphabet $\Sigma$
>- $\Sigma^\infty = \Sigma^*\cup\Sigma^\omega$ 
>- Given a Language $U\subseteq \Sigma^*$
>	- $U^\omega = \{u_1u_2\dots\;|\;u_i\in U\setminus\{\epsilon\}\}$ 
>	- $\text{lim}(U) = \{a_1a_2\dots\;|\;\exists^\omega i\;a_1\dots a_i\in U\}$
>	- $U\cdot\Sigma^\omega = \{u\cdot a_1a_2\dots\;|\;u\in U,a_i\in\Sigma\}$

---
# References
[[Büchi Automata]]
[[Omega-Regular Languages]]