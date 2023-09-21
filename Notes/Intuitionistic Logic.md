202308141408

Type : #Note
Tags : [[Logic]], [[Type Theory]]

---
# Intuitionistic Logic
```ad-success
title: Suresh
$2+5 = 3\times6$
```

The logic interpretation was first developed as BHK - Interpretation which stands for Brouwer, Heyting and Kolmogorov which probably independently made contributions to it.

```ad-note
title: syntax
The Main syntax of the language of intuitionistic logic is
$$
\begin{matrix}\perp & | & (\phi\to\psi) & | & (\phi\land\psi) & | & (\phi\lor\psi)\end{matrix}
$$
along with short hand notations
$$
\begin{align*}
\lnot \phi &= (\phi\to\perp)\\
\phi\leftrightarrow\psi &= (\phi\to\psi)\land(\psi\to\phi)\\
\top &= \perp\to\perp\\
\end{align*}
$$
```
*Intuitionistic Logic* was made for _Constructivist Mathematics_, so instead of basing our logical statements on **Truth**, we base them on **Constructions**. 

- A construction of $\varphi_{1}\land\varphi_{2}$ consists of a construction of $\varphi_{1}$ and a construction of $\varphi_{2}$.
- A construction of $\varphi_{1}\lor\varphi_{2}$ consists of a an indicator $i\in\{1,2\}$ and a construction of $\varphi_{i}$ 
- A construction of $\varphi_1\to\varphi_2$ is a function that transforms every construction of $\varphi_1$ to a construction of $\varphi_2$ 
- There is no construction for $\perp$ 

The language of Intuitionistic Logic was later simplified in a language called [[Natural Deduction]]

Where as [[Heyting Algebra]] and [[Kripke Models]] are some of the ways to proved semantics to **Intuitionistic Logic**.


---
# References
Algebraic Semantics of Logic: [[Lattice]]