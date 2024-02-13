---
tags:
  - Note
---
202401041501

Tags : [[Automata Theory]]
# $\omega$-Regular Languages
---
$\omega$-regular languages is the set of languages that can be written in the as follows 
$$
L = \bigcup_{i\in[n]} U_{i}\cdot V_{i}^\omega 
$$

Where $U_{i}$ and $V_i$ are regular languages

>[!tip] Intuition
>These are supposed to be infinite version of regular languages

---
## Closure Properties
Omega Languages are closed under the following:
- Union
- Intersection
- Complementation
- Right Concatenation with a Finite Regular Language
- $\omega$-closure of a language that does not contain the empty string.

Proof for some of these properties are a bit involved and are discussed here:
[[Closure Properties of Büchi Automata and Omega-regular languages]]

---
# References
[[Language of Infinite words]]
[[Set of Languages accepted by Büchi Automata are exactly Omega-Regular]]