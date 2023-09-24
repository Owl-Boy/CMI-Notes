---
tags:
  - Note
---
202309231609

Tags : [[Timed Automata]]

---
# Expressive Power Of Event Clock Automata
![[Drawing 2023-09-23 16.46.35.excalidraw]]
- [[Event Recording Automata]] are weaker than [[Deterministic Timed Automata]] because the conversion process preserves determinism
- *EPL*$\not\subseteq$*ERL*
	- $L=\{aab\}$ where time diference between first and last letter is $1$. $L\in$ *EPL* but $L\notin$ *ERL*
-  *ERL*$\not\subseteq$*EPL*
	- $L=\{abb\}$ where time difference between first and last letter is $1$. $L\in$ *ERL* but $L\notin$ *EPL*
- *DTL* $\not\subseteq$ *EPL*
	- $L=\{abb\}$ where the last letter is accepted $1$ unit after the first one
- *EPL*$\not\subseteq$ *DTL*
	- $L=\{a^{k}b\}$, there is an $a$ such that the $b$ is accepted $1$ unit after it
- *DTL* $\not\subseteq$ *ECL*
	- $L = \{aaa\}$, the time difference between accepting the first and last $a$ is $1$
- *ECL*$\not\subseteq$*DTL*
	- As *EPL* $\not\subseteq$ *DTL*
- *ECL* $\not\subseteq$ *EPL* $\cup$ *ERL*
	- $L=\{aab\}\cup\{abb\}$ such time the time difference between first and last letters is $1$
- *ECL* $\subseteq$ *NDTL*

---
# References
