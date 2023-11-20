---
tags:
  - Note
  - Incomplete
---
202311162011

Tags : [[Timed Automata]]
# Region Automata Alternate Definition
---
Given a [[Timed Automata Alternate Definition|Timed Automata]] we define a *region automata* $\textbf{R}_A$ as 
$\textbf{R}_{\mathcal A} = \langle Q, X, T, \kappa,\lambda\rangle$ such that
- $Q=L\times R_{\mathcal A}$
- $\kappa((l,\tau))=\mathcal I(l)$
- $\lambda((l,r))=\mathcal L(l)$
- $X$ is the same set of clocks
- $T\subseteq Q\times \text{cell}(R_\mathcal A) \times E\times \mathcal 2^X\times Q$, so $(l,r)\xrightarrow{\text{cell}(r''),e,Y}(l',r')$ exists if
	- $\text{cell}(r)$ is the smallest guard which contains $r$
	- $(l,r)\xrightarrow{\text{cell}(r''),e,Y}(l',r')$ exists if 
		- There exists $e=l\xrightarrow{g, Y}l'$ 
		- $(l,\nu)\xrightarrow{\tau,e}(l',\nu')$ with 
			- $\nu\in r$ 
			- $\nu+\tau\in r''$
			- $\nu'\in r'$
We recover the usual [[Region Automata]] by replacing $\text{cell}(r''),e,Y$ with just $e$.

For each concrete run $\varrho$ in $\mathcal A$, we have $\iota(\varrho)$ which is its unique image in $\textbf R_\mathcal A$
## Some Important Properties
### Path Correspondence
Every finite path $\pi((l,\nu),e_{1}\dots e_{n})$ in $\mathcal A$ there is a corresponding finite set of paths $\pi(((l,[\nu]),\nu),f_{1}\dots f_{n})$ in $\textbf R_\mathcal A$.
Each path is decided by the choice of regions traversed.

### There are bisimulation properties

### Non Blocking
If $\mathcal A$ is non blocking, then so is $\textbf R_{\mathcal A}$.


---
# References
- [[Timed Automata Alternate Definition]]
- [[Region Automata]]