202308231008

Type : #Note 
Tags : [[Algebraic Graph Theory]]

---
# Cayley Graphs
Let $\Gamma$ be a finite group and $S\subset\Gamma$ such that 
- $S\ne \emptyset$
- $1\notin S$
- $s\in S\iff s^{-1}\in S$
Then the *Cayley Graph* $G=\text{Cay}(\Gamma, S)$ has $V=V(G)=\Gamma$ and $x\sim y$ if $x^{-1}y\in S$

Let $G=\text{Cay}({\Gamma, S})$, then
- $E=\{(\alpha, \alpha s):\alpha\in\Gamma,s\in S\}$
- $G$ is [[Regular Permutation Groups|semiregular]]
- Let $\beta\in\Gamma$. Then $\rho_{\beta}:V(G)\to V(G)$ given by $\rho_{\beta}(x)=x\beta$ is an automorphism
- $\rho_{\gamma}\circ\rho_{\beta}=\rho_{\gamma\beta},\gamma\to\rho_{\gamma}$ is an isomorphism

## Theorem
**Statement:** Let $G=\text{Cay}(\Gamma, S)$ connected iff $S$ is a generator set for $\Omega$.
**proof:** Let $\langle S\rangle = \Gamma$. Then $\forall r\in\Gamma,r=s_{1}s_{2}\dots s_{r},s_{i}\in S\forall i$
$$
1 \xrightarrow{s_{1}}s_{1}\xrightarrow{s_{2}}s_{1}s_{2}\xrightarrow{s_{3}}\;\cdots\xrightarrow{s_{r}}\; s_{1}s_{2}\dots s_r
$$
Conversely, suppose $\langle S\rangle =\Gamma'\subsetneq\Gamma$ then $r\in\Gamma$ and $r\notin\Gamma'$. Then $\not\exists$ a path with the edge with labels in $S$ such that the path goes from $1$
 to $r$. which means $G$ is not connected.
## Theorem
**Statement:** Let $G$ be the [[Automorphism Group of a Graph#^8a19cf|Peterson Graph]]. Then $G$ is not a _Cayley Graph_
**Proof:**
Consider $\Gamma=\mathbb Z_{10}$
Since the degree of graph is $3$ $S=\{\alpha,\beta,\beta'\}$ and the only element that can be alpha is $+5$ 
Then there exists that path 
$1\sim\beta\sim\beta\alpha\sim\beta\alpha\beta^{-1}\sim\beta\alpha\beta^{-1}\alpha^{-1}=1$ which makes a cycle of $4$ which is a contradiction.
Hence $\Gamma=D_{5}$.
$|S|$ has to be 3 so we have $S=\{\alpha, \beta, \beta^{-1}\}$
Then consider $1\sim\beta\sim\beta\alpha\sim\beta\alpha\beta\sim\beta\alpha\beta\alpha=1$ which also creates a cycle of $4$ which is also a contradiction. Hence the _Peterson Graph_ cannot be a _Cayley Graph_

## Theorem
**Statement:** Given $(\Gamma, S)$, let $G=\text{Cay}(\Gamma, S)$. Then $\Gamma$ acts [[Sharp Transitively]] on $G$.
**Proof:**
Consider $(\beta, \gamma)\in E$  
$$
\begin{align*}
(\beta, \gamma)\in E &\implies \beta^{-1}\gamma\in S\\
&\implies (\alpha\beta)^{-1}(\alpha\gamma)\in S\\
&\implies \tilde \alpha(\beta)\tilde\alpha(\gamma)\in S
\end{align*}
$$
So $\tilde\alpha$ is an automorphism of $G$

## Theorem
**Statement:** Let $G$ be a connected graph and $\Gamma\subseteq \text{Aut}(G)$. Then the following are equivalent:
- $\Gamma$ acts [[Sharp Transitively]] upon $G$
- $G=\text{Cay}(\Gamma, S)$ for a suitable symmetric $S\subset T$ such that $S$ generates $\Gamma$
**Proof:**
($1\implies2$)
Let $\gamma_{i}\in\Gamma$ (unique) such that $\gamma_{i}(v_{1})=v_{i}$ 
$$
\begin{align*}
\text{Let } S^{+}&= \{s\in\Gamma\ :\ s(v_{1})\sim v_{1} \}\\
S^{-}&= \{s^{-1}\ :\ s\in S^{+}\}\\
S&= S^{+}\cup S^{-}
\end{align*}
$$
on vertex set $\Gamma$, define a graph where $\gamma_{i}\sim\gamma_{j}$ if $\gamma_{j}=\gamma_{i}s, s\in S$.

Then 
$$
\begin{align*}
\gamma_{i}\sim \gamma_{j}&\iff \gamma_{i}^{-1}\gamma_{j}\in S \\
&\iff v_{i}\sim (\gamma_{i}^{-1}\gamma_{j})v_{1}\\
&\iff \gamma_{i}(v_{1})=\gamma_{j}\\
&\iff v_{i}\sim v_{j} 
\end{align*}
$$

```ad-todo
break apart into different files
```



---
# References
[[Cayley-Graph-Examples]]