---
tags:
  - Note
---
202309261809

Tags : [[Algorithmic Coding Theory]]

---
# Local Decoding

For some applications, we can't afford to look at the entire codeword, e.g. if we have *Distributed Storage*, or in the following setting: We want to ask for the $i^{th}$ bit in an $n$ bit string, but we don't want them to know what $i$ is.
We want to decode in sub-linear time. $Q$ should be $o(n)$.

**Locally correctable code:** $C\subset \mathbb{F}_{q}^{n}$ is a $(\delta,Q)$-locally correctable code if there is an algorithm $A$ s.t. the following holds:
For all $w \in \mathbb{F}_{q}^{n}$ s.t. $\exists c \in C$ s.t. $\Delta(c,w)\le\delta n$ and $\forall i \in [n], A^{(w)}(i)$ makes at most $Q$ *oracle queries* to $w$.

If we have a deterministic algorithm, an adversary can ensure that there is no codeword satisfying the given parameters. So we appeal to *randomised algorithms*! We allow for a failure with low probability. So we want $A^{(w)}(i)=C_{i}$ with probability at least $1-\gamma$, **locally decodable codes**.

```ad-note
Any linear $LCC$ is also $LDC$.
```

| Q               | $n$ (as a function of $k$)                   |
| --------------- | -------------------------------------------- |
| 2               | $n = \Theta(2^{k})$                          |
| 3               | $k^{2}\le n\le e^{e^{\log(\log(n)^{0.99})}}$ |
| $O(\log(n))$    | $k \le n \le \text{poly}(k)$                       |
| $O(n+\epsilon)$ | $k\le n\le (1+\alpha^{k})$                   |

---

## Hadamard Code
For Hadamard Code, we have a $2-$query $LDC$, $2-$query $LCC$, and a $3-$query $LTC$.
It is an exponential length linear code $H:\mathbb{F}_{2}^{k}\to\mathbb{F}_{2}^{n}$, $n=2^{k}$.
How you map is, for $x\in\mathbb{F}_{2}^{k}$, you take the dot product of $x$ and $i$ in binary, and write the result at the $i^{th}$ index. More formally, $H(x)_{y}=\langle x,y\rangle$.
(It's like you're evaluating a linear map on $n$ points.)

The minimum distance is $n/2$. Local correction is only possible up to half of minimum distance.

**Lemma:** For every $\delta\in(0,\frac{1}{4})$, Hadamard code is a $(2,\delta,\frac{1}{2}-2\delta)$ $LCC$.
*Proof:* Suppose we are given a corrupted version of a codeword $H(x)$, say $\tilde{H}$ s.t. $\Delta(H(x),\tilde{H}(x))\le\delta n$.
To correct the symbol at $y\in\mathbb{F}_{2}^{k}$, the local correcter algorithm makes queries $\tilde{H}(x)$ at $z$ and $z+y$ for a uniformly random $z\in\mathbb{F}_{2}^{k}$.
With probability at least $1-2\delta$, $\tilde{H}(x)_{z}+\tilde{H}(x)_{z+y}=\langle x,z\rangle +\langle x,z+y\rangle=\langle x,y\rangle$.
And then just compute the parity of the two bits.


---
# References
