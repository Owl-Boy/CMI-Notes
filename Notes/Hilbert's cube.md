202303241103

Type : #Note
Tags : [[Topology]]

---
# Hilbert's cube
```ad-note
title:
The hilbert cube is defined as the product $$ H := \prod \limits_{ n=1}^{ \infty }\left[ 0,\frac{1}{n} \right] $$
with the product topology.
```

We consider two metrics on $H$, one is the uniform metric $\rho$:
$$
\rho(x,y) = \sup \limits_{ n\geq 1}|x_{n}-y_{n}|
$$
Another is the $\ell^{2}$ metric $d_{2}$ given by: $$
d_{2}(x,y) = \left( \sum\limits_{ n=1}^{ \infty } (x_{n}-y_{n})^{2} \right) ^{1/2}
$$
### Proposition:
```ad-note
title:
The uniform metric and the $\ell^{2}$ metric induce the same topology on $H$ as the product topology. In other words, $H$ is metrizable.
```
##### Proof:
Denote by $\tau_{H}$ the product topology on $H$, $\tau_{d_{2}}$ be the metric topology induced by $d_{2}$, and $\tau_{\rho}$ be the metric topology induced by $\rho.$
We will show that $\tau_{H} \subset \tau_{\rho} \subset \tau_{d_{2}} \subset \tau_{H}$.
Take any basic open set in $H$, call it $U$. $U = \prod\limits_{ n=1}^{ \infty }B_{n}$ where finitely many $B_{n}$ are open subsets of $\left[ 0,\frac{1}{n} \right]$ and the rest being full spaces. Fix a point $x \in U$, then for each $x_{n}, \exists r_{n}$ such that $B(x_{n},r_{n}) \subset B_{n}$. Take those $r_{n}$'s corresponding to the $B_{n}$'s that are not full spaces, and take their minimum, call it $r$. Then $B_{\rho}(x,r) \subset U$.
This shows $\tau_{H} \subset \tau_{\rho}$.

Now take a ball $B_{\rho}(x,r)$. See that $B_{d_{2}}(x,r) \subset B_{\rho}(x,r)$. This shows $\tau_{\rho} \subset \tau_{d_{2}}$.

Let $B_{d_{2}}(x,r)$ be a ball in $d_{2}$ metric, then $B_{d_{2}}(x,r) = \prod\limits_{ n=1}^{ \infty }B_{n}$ where only finitely many $B_{n}$'s are not the whole space. Then we know that the remaining $B_{n}$'s are open in $\left[ 0, \frac{1}{n} \right]$. And so, $B_{d_{2}}(x,r)$ is open in $\tau_{H}$.

### Proposition:
```ad-note
title:
The space $$\prod\limits_{ n=1}^{ \infty } [0,1] = [0,1]^{\omega}$$
is metrizable.
```
##### Proof:
Note that $[0,1]^{\omega}$ is homeomorphic to $H$. Since $[0,1]$ is homeomorphic to $\left[ 0, \frac{1}{n} \right]$.

#### NOTE: 
The uniform metric defined on $[0,1]^{\omega}$ is just the pulled back version of the uniform metric on $H$.

---
# References
[[Product topology]]
[[Metric Topology]]
[[Uniform Topology]]

