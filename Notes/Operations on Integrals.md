---
tags:
  - Note
---
202409200009

Tags : [[Measure Theory]]
# Operations on Integrals
---
#### Restriction to a $\sigma$-field
$(\Omega, \mathcal{A}, \mu)$ is a measure space and $\mathcal B \subseteq \mathcal{A}$ be sub-$\sigma$-field. For $B\in\mathcal B$ we put $\nu(B)=\mu(B)$, then $(\Omega,\mathcal B, \nu)$ is a measurable space. A $\mathcal B$-measurable function $f$ is $\nu$-integrable iff it is $\mu$-integrable, and $\int f \, d\mu=\int f \, d\nu$. 

Even if $\mu$ is $\sigma$-finite, $\nu$ might no be.

#### Restriction to a set
$(\Omega, \mathcal{A},\mu)$ is a measure space and $\Omega_{0}\in \mathcal{A}$ with $\mu(\Omega_{0})>0$. Let $\mathcal B = \{ A\cap \Omega_{0} :A \in \mathcal{A} \}=\{ B \in\mathcal{A} : B\subseteq \Omega_{0}\}$. 
For $B\in \mathcal B$ put $\nu(B)=\mu(B)$. Then $(\Omega_{0},\mathcal B, \nu)$ is a measure space. A $\mathcal B$-measurable $f$ is $\nu$-integrable iff the function $f^*=f$ on $\Omega_{0}$ and $f^*=0$ on $\Omega_{0}^c$ is $\mu$-integrable and then $\int f \, d\nu=\int f^* \, d\mu$. 

If $\mu$ is $\sigma$-finite, so is $\nu$.

#### Density
$(\Omega, \mathcal{A}, \mu)$ is a $\sigma$-finite measure space and $\varphi > 0$ is a measurable function. Then $\nu(B)=\int \varphi I_{B} \, d\mu$ is a $\sigma$-finite measure on $\mathcal A$. The measure $\nu$ is finite iff $\varphi$ is $\mu$-integrable. Further, $f$ is $\nu$-integrable iff the product $\varphi f$ is $\mu$-integrable and $\int f \, d\nu = \int \varphi f \, d\mu$.

#### Change of Variables
$(\Omega, \mathcal{A},\mu)$ is a measurable space and let $(\Omega', \mathcal B)$ be a measurable space and $T:\Omega \to \Omega'$ be a measurable function.

Put $\nu(B)=\mu(T^{-1}(B))$ for $B\in\mathcal B$. Then $(\Omega',\mathcal B, \nu)$ is a measure space. A $v$-measurable function is integrable iff $g=f\circ T$ is $\mu$-integrable and then $\int f \, d\nu=\int f\circ T \, d\mu$

---
# References
