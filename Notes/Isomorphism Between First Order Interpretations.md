---
tags:
  - Note
---
202309221209

Tags : [[Logic]]

---
# Isomorphism Between First Order Interpretations
```ad-note
title: Motivation
Let $R=\{<\}, F=\emptyset$
Consider two structures, one where $S=\mathbb{Q}\cap(0,1)$ and one where $S=\mathbb{Q}\cap(0,\infty)$
Then we cannot have any **First Order Formula** which is valid for one of the model and not for the other one, hence that is not strong enough to differentiate between the two models.

Here we show that the two models are isomorphic.
```


Let $\mathcal I_{1} = \{\mathcal{M}_{1},\sigma_{1}\}$ and $\mathcal I_{2} = \{\mathcal M_{2},\sigma_{2}\}$
Then we say that the above two [[Semantics of First Order Logic#Interpretation|interpretations]] **isomorphic** if there exists a bijection $\tau:S_{1}\to S_{2}$ such that:
- For every $r\in R$ we have $(e_{1},e_{2}\dots e_{n})\in r^{\mathcal M_{1}}$ iff $(\tau(e_{1}),\tau(e_{2})\dots \tau(e_{n}))\in r^{\mathcal M_{2}}$ 
- For every $f\in F$ we have $\tau(f^{\mathcal M_{1}}(e_{1},e_{2}\dots e_n))=f^{\mathcal M_{2}}(\tau(e_{1}),\tau(e_{2})\dots\tau(e_{n})))$
- For every $c\in C$ we have $\tau(c^{\mathcal M_{1}})=c^{\mathcal M_{2}}$
- For every $x\in Var$ we have $\tau(\sigma_{1}(x))=\sigma_{2}(x)$

```ad-question
title:Lemma
If $\mathcal I_{1},\mathcal I_{2}$ are isomorphic, then for every formula $\varphi$, $\mathcal I_{1}\models\varphi$ iff $I_{2}\models\varphi$.

*Proof:* Induction on structure of $\varphi$
```



---
# References
[[Syntax of First Order Logic]]
[[Semantics of First Order Logic]]