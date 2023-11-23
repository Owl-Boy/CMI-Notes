---
tags:
  - Note
  - Incomplete
---
202310191510

Tags : [[Algorithmic Coding Theory]]

---
# Local problems on codes
Algorithmic problems on codes that can be solved "locally":
- Locally testable codes (LTCs)
- Locally correctable codes (LCCs)
- Locally decodable codes (LDCs)

**Local testing:** (Is it a valid codeword or is it far from being a codeword? - Property testing)
Given a word $r\in\Sigma^{n}$, is it a valid codeword?
If it is a valid codeword, we should output True with probability 1.
If it's not a codeword, then probability that we output False should be at least $\frac{1}{4}\Delta(r,C)$.
(It's local because we will be reading $r$ by making at most $q$ oracle queries.)

---
Hadamard code is the standard example for local decoding but it has decreasing rate.
Local codes in the constant rate regime are constant-variable RM codes over large fields. They can achieve any rate $R< \frac{1}{2}$, constant distance, but number of queries is $O(n^{\log R})$.

LDCs/LCCs with constant rate regime have query complexity at least $\Omega(\log n)$.
LTCs, however, with constant rate, constant distance and constant query complexity exist. This was open for a while till Dinur's paper (talk in Simon's Institute).

---
RM codes with $m=1$ are just RS codes.
RS codes were so good, then why move to RM codes? RM codes, for $m\geq 2$ have $R< \frac{1}{2}$. But RS codes have increasing alphabet size. So we increased $m$ to decrease the alphabet size. This is one of the motivations for RM codes.
Also, increasing $m$ endows the code with 'local' properties.(??)

Restriction of a $d-$degree multivariate polynomial to a line is a degree $d$ univariate polynomial.


---
# References
[[Local Decoding]]