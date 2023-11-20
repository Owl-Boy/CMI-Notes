---
tags:
  - Note
  - Incomplete
---
202311141511

Tags : [[Algorithmic Coding Theory]]

# Applications of Error Correcting Codes
---

## [[Group Testing problem|Group Testing problem]]
There are $N$ people, $n$ have some disease, say CoViD. We want to test the people for the disease, and the tests are costly. $n\ll N$. The naive way would be to draw a sample from each of them, and test each sample separately, which is costly.
So another way to approach this is *'pooled testing'*, i.e. you pool samples together, and test them in groups.

## [[Sparse recovery-compressed sensing |Sparse recovery-compressed sensing]]
$x \in\mathbb{C}^{n}$ vector is $L-$*sparse* (# non zero entries $=L$)
The goal is to design a *measurement matrix* $M_{(m\times n)}$ s.t. given $y=Mx$, we can uniquely reconstruct $x$. $m$ should be as small as possible.

## **Streaming algorithms**
Data is coming in a stream: $x_{1},x_{2},\dots,x_{t}\in U$ (universe), $|U|=n$.
We want to do *frequency counts* $f_{i}=\#i$ appears in the stream
We don't want to store the frequency vector, because it can be huuuugeeeeeeee, if $n$ is large, although that would solve the problem.
Here it would be easier to multiply the frequency vector, $f_{v}$ by a 'short, fat matrix', $\phi$ and store the small vector instead.

---
# References
[[Error Correcting Codes]]