202308101608

Type : #Note
Tags : [[Algorithmic Coding Theory]]

---
# Error Correcting Codes
Let $c\in\Sigma^{n}$ be a code and $t\ge 1$ is an integer.
$C$ is a $t-$error correcting code if $\exists$ a decoding function $\text{Dec}$ such that for every message $m\in [|C|]$(data words)
$$
(\text{Dec}\circ Ch\circ\text{Enc}) = id
$$

where $Ch$ is an [[Hamming Distance#^88a6ce|t-error channel]] 

The above process is
$$
\text{data word} \longmapsto \text{Encoding Function} \longmapsto {Error Channel} \longmapsto {Decoding Function}
$$

---
# References
[[Hamming Codes]]