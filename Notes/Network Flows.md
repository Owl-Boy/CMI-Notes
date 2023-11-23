---
tags:
  - Note
  - Incomplete
---
202310181410

Tags : [[Advanced Algorithms]]

---
# Network Flows
$G=(V,E)$ directed graph
$s,t\in V$, $s:$ source, $t:$ sink
$c(u,v)\ge 0\ \forall(u,v)\in E$

**Flow:** An assignment $f(u,v)$ $\forall (u,v)\in E$ s.t.
- $f(u,v)\le c(u,v)\ \forall (u,v)\in E$ 
- $f(u,v)=-f(v,u)$
- $\sum\limits_{u:(u,v)\in E}f(u,v)=\sum\limits_{w:(v,w)\in E}f(v,w)$ $\forall v\in V\setminus \{ s,t \}$

Value of a flow $f=|f|=\sum\limits_{v:(s,v)\in E}$

### Algorithm
While $\exists s-t$ path $P$ in $G_{f}$
{
Set up a flow $f'$ along $P$, $|f'|$ as large as possible.
Find *residual graph* $G_{f'}$.
$G_{f}=G_{f'},f=f+f'$
}
Return $f$

**Residual graph $G_{f}$:** For each edge $(u,v)\in E$ s.t. $f(u,v)>0$, $G_{f}$ has an edge $(v,u)$ and $c(v,u)=f(u,v)$.

**To prove:**
1. A flow $f'$ in $G_{f}$ iff $f+f'$ is a flow (Exercise.)
2. The flow output by the edge is a max-flow

$s,t$ cut: A partition of $V$ into $S$ and $T$

---
# References
