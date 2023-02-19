202211150011

Type : #Note
Tags : [[Theory of Computation]]

---
# Turing Machine Configuration
The configuration of the turing machine is the triple $Q\times\{y\sqcup^\omega|y\in\Gamma^*\}\times\mathbb N$ which is the current state, the current content of the tape and the position of the pointer.
It is generally represented by $(p, z, n)$ 

The start configuration on the input $x\in\Sigma^*$ is the configuration $(s, \dashv x\sqcup^\omega, 0)$.

We can define the next configuration relation $\xrightarrow[M]{1}$ as
$$
\begin{equation}
(p, z, n) \xrightarrow[M]{1}
\begin{cases}
(q, s^n_b(z), n-1)&\text {if }\delta(p,z_n)=(q, b, L)\\
(q, s^n_b(z), n+1)&\text {if }\delta(p,z_n)=(q, b, R)\\
\end{cases}
\end{equation}
$$

and we can define the _transitive closure_ of $\xrightarrow[M]{*}$ of $\xrightarrow[M]{1}$ as
- $\alpha \xrightarrow[M]{0}\alpha$
- $\alpha \xrightarrow[M]{n+1}\beta$ if $\alpha\xrightarrow[M]{n}\gamma\xrightarrow[M]{1}\beta$ for some $\gamma$
- $\alpha \xrightarrow[M]{*}\beta$ if $\alpha\xrightarrow[M]{n}\beta$ for some $n\ge0$

The machine _accepts_ an input $x\in \Sigma^*$ if 
$$
(s, \dashv x\sqcup^\omega, 0)\xrightarrow[M]{*}(t, y, n)
$$

The machine _rejects_ an input $x\in \Sigma^*$ if 
$$
(s, \dashv x\sqcup^\omega, 0)\xrightarrow[M]{*}(r, y, n)
$$

If a machine rejects or accepts an input, it is said to _halt_ on the input, as with a PDA, it might not halt in which case it is said to _loop_. If a Turing Machine halts on all its inputs it is called _total_.

$L(M) = \{x\in\Sigma^*| M \text { accepts } x \}$ 
A set of strings is called 
- Recursivly Enumerable (R.E.) if it is $L(M)$ for some turing machine $M$
- Co R.E. if its complement is (R.E.)
- Recursive, if it is $L(M)$ for a total turing machine.

For [[ww where w is any word |example]] $\{ww|w\in \{a, b\}^*\}$ is a recurisve set.

---
# Related Problems

---
# References
[[Turing Machines]]
