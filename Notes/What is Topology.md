202301031001

Type : #Note
Tags : [[Topology]]

---
# What is Topology
```ad-note
title:
It is the study of topological properties of topological spaces.
```

**Topological Properties** are properties that can be expressed in terms of continuity.
[[Topological Spaces]] are sets which have some notion of nearness between elements.
- A [[Continuous Functions|continuous function]] $f:X\to Y$ is such that if $x,x'\in X$ are near each other implies $f(x),f(x')\in Y$ are near each other

One way to define the notion of distance is to make a function $d:X\times X \to \mathbb R$ which takes a pair of values and returns the _"Distance"_ between them, following some nice properties. This is called a metric space.
 
We care about this because
- Continuous Functions on  a domain $X$ will tell you about $X$ itself.
- There are spaces which carry a reasonable notion of **nearness** which are not metric spaces.
	- *Example:* Pointwise convergence of functions
	  $$
	  \begin{aligned}
	  \{f_n\} &:\mathbb R \to \mathbb R \text{ are pointwise convergent if }\\
	  g \text{ is a limit of } &\{f_n\} \text{ for each } t\in\mathbb R \text{ and } \lim\limits_{n\to\infty} f_n(t)=g(t) 
	  \end{aligned}$$
	  Here there is a notion of nearness on the space of functions which is not a metric

**Nearness:** If $U$ is open in $X,x\in U$, then all $y$ that are _sufficiently near_ to $x$ also satisfy $y\in U$.

---
# Related Problems

---
# References
