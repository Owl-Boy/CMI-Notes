202309070909

Type : #Note 
Tags : [[Lambda Calculus]], [[Type Theory]]

---
# Newman's Lemma
```ad-note
title: Lemma
$$
\text{SN + WCR = CR}
$$
```

Newman's Lemma states that [[Strong Normalization Theorem]] and *Weak Church Rosser Theorem* Implies the *Church Rosser Theorem*

The proof is using *WCR* and $\nu$ value of lambda terms which reduces strictly on reductions.

### Proof
The proof is by induction on $\nu$ value of lambda term.

Given a lambda term $L$ and $\nu(L)=k$. And given that Church Rosser Theorem is valid for all terms $L'$ where $\nu(L')<k$. Say $L$ reduces to $L_{1}$ and $L_{2}$. We have $2$ cases

**Case 1:** The first reduction in $L\rightsquigarrow L_1$ and $L \rightsquigarrow L_{2}$ is the same.
We have $L\to_{\beta}L'$ and $L'\rightsquigarrow L_1$, $L'\rightsquigarrow L_2$. We have by induction $L_{1}\rightsquigarrow F$ and $L_{2}\rightsquigarrow F$(Church Rosser on $L'$). This proves Church Rosser for $L$.
![[Drawing 2023-09-07 13.20.36.excalidraw|250]]

**Case 2:** The first reduction in $L\rightsquigarrow L_{1}$ is different from $L\rightsquigarrow L_{2}$ 
we have $L\to_{\beta}L_{l}\rightsquigarrow L_{1}$ and $L\to_{\beta}L_{r}\rightsquigarrow L_{2}$. 
Applying Weak Church Rosser Theorem for $L$ we get $S$ such that $L_{l}\rightsquigarrow S$ and $L_{r} \rightsquigarrow S$. 
Then by induction, applying Church Rosser Theorem for $L_{l}$ and $L_{r}$ we get $R_{1}, R_{2}$  such that 
$$
\begin{align*}
L_{1} \rightsquigarrow R_{1} &\text{ and } S\rightsquigarrow R_{1} &\text{Church Rosser on $L_{l}$}\\
L_{2} \rightsquigarrow R_{2} &\text{ and } S\rightsquigarrow R_{2} &\text{Church Rosser on $L_{r}$}\\
\end{align*}
$$
Since $\nu(L_{l})<\nu(L)>\nu(L_{r})$.

Then we apply Church Rosser Theorem on $S$ as $\nu(S)<\nu(L)$ we get $L'$ such that $R_{1}\rightsquigarrow L'$ and $R_{2}\rightsquigarrow L'$.
![[Drawing 2023-09-07 13.22.15.excalidraw|250]]

The base cases for our induction are the Normal Terms for which Church Rosser is trivially True. And we will always reach Normal Terms because of [[Strong Normalization Theorem]].

---
# References
[[Strong Normalization Theorem]]