202301181801

Type : #Note
Tags :

---
# Continuous Functions
```ad-info
title: Idea
The idea is to convert the eqsilon delta definitions for metric spaces to topology, with closeness between points is represented by being in a common open set
```
Let $(X, \mathcal T_X)$ and $(Y, \mathcal T_Y)$ be $2$ Topological Spaces and let $f:X\to Y$ be a Topological Space be a function between them. We say $f$ is continuous if $f^{-1}(V)\in \mathcal T_X$ for every $V\in \mathcal T_Y$.

This is a Global Definition, a Local Definition will be given later
**Examples:**
- If a function from $\mathbb R\to \mathbb R$ is continuous in the _Calculus Sense_, then it is continouous in the _Topological Sense_.
- The projection functions from $\mathbb R^{2}\to \mathbb R$ are continuous
- Any function from a discrete space to a topological space is continouous
- Any function from any topological space to the _trivial_ topology is continuous
- Any _Constant_ function from any topological space to any other topological space is continuous
- If $f:X\to Y$ and $g:Y\to Z$ are continuous then $g\circ f:X\to Z$ is continuous
- The identitiy function from $\mathbb R\to\mathbb R_l$ is not continuous, but the identitiy function from $\mathbb R_{l}\to\mathbb R$ is continuous

__equivalent statements for continuous functions:__ 
- Pre images of _open_ sets are _open_, i.e $f^{-1}(V)\in \mathcal T_X$ for all $V\in\mathcal T_Y$ 
- Pre images of _basic open_ sets are _open_, i.e $f^{-1}(V)\in \mathcal T_X$ for all $V\in\mathcal B$ 
- Pre images of _sub-basic open_ sets are _open_, i.e $f^{-1}(V)\in \mathcal T_X$ for all $V\in\mathcal S$

---
# Related Problems

---
# References
[[Homeomorphisms]]