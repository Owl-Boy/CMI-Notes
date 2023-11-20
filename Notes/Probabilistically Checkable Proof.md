---
tags:
  - Note
  - Incomplete
---
202311201611

Tags : [[Advanced Algorithms]]
# Probabilistically Checkable Proof
---
$x:$ $n-$bit input
$y:$ certificate
$c:$ completeness
$s:$ soundness

Verifier $V$ uses $r(n)$ random bits, reads $q(n)$ bits of $y$.

If $x$ is a 'yes' instance, then for some $y$, $V$ accepts $x$ with probability $\geq c$.
If $x$ is a 'no' instance, then for any proof $y$, $V$ accepts $x$ with probability $\leq s<c$.

```ad-important
**PCP theorem:** $NP=PCP_{1, \frac{1}{2}}(O(\log n),k)$ for some constant $k$.
```

$PCP_{c,s}(r(n),q(n))$

*Hastad's PCP:* $NP=PCP_{1-\epsilon, \frac{1}{2}+\delta}(O(\log n),3)$ and verifier checks if the three bits have odd or even number of $1$s.




---
# References
[Williamson-Shmoys]