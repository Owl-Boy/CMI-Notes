202210062110
  
  Type : #Note
  Tags : [[Calc]]
  
  ---
# Tensor Algebra
> [!note] Tensor Algebra
> 
To any Vector space $V$, we can associate a _Tensor Algebra_ $\mathcal{T}(V)$, called the Tensor Algebra "over" $V$


We set $\mathcal{T}^0(V) = \mathbb{R}, \mathcal{T}^1(V) = V^*,$ similarly
$$
\mathcal{T}^k(V) =\text{set of all multilinear maps }T: \underbrace{V\times\dots\times V}_\text{k times}\to\mathbb{R}
$$
we set 
$$
\mathcal{T}^*(V) = \oplus_k\mathcal{T}^k(V) \text{  
 (algebraic direct sum of vector spaces)}
$$
and the elements above are of the form $(T^0,T^1\dots)$ where all but finitely many are zero.

Elements of $\mathcal{T}^0$ multiply to k-tensors as scalars, otherwise given $S\in\mathcal{T}^l(V),\ T\in\mathcal{T}^m(V)$ we define the _Tensor product_ $S\otimes T$ as

$$S(v_1,v_2\dots v_l)\cdot T(w_1,w_2\dots w_m) = S\otimes T(v_1,v_2\dots v_l,w_1\dots w_l)
$$
OR
$$
	S\otimes T =_{def} (S_0T_0,\ S_0T_1+S_1T_0,\ S_0T_2+S_1T_1+S_2T_0\dots)
$$

Thus $\mathcal{T}^k(V)\times \mathcal{T}^l(V) \to \mathcal{T}^{k+l}(V)$ is a bilinear map which is associative and noncommutative. Hence $\mathcal{T}^*(V)$ is an $\mathbb{R}$-algebra($\mathbb{R}$ is a subring).

---
# Related Problems
[[Calc - Problem Session - 7 Oct]]

---
# References
[Ramdas's Notes](https://moodle.cmi.ac.in/pluginfile.php/27842/mod_resource/content/13/CalculusNotes.pdf)
[[Exterior Algebra]]