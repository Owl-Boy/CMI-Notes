202308161908

Type : #Note
Tags : [[Algorithmic Coding Theory]]

---
# Measurement of Redundancy in a code
The measurement of redundancy in a code is done using two related metrics, those being **Dimension** and **Rate**.
## Dimension of a code
The dimension $k$ of a code is defined as:
$$
k=\log_{q}(|C|)
$$
where
$q=|\Sigma|$
$|C|$ is the set of data words.
This can be thought of as size of the vector that can correspond to all the code words where each entry can be one of $q$ characters.

## Rate of a code
The rate of the code is the average amount of information being carried by each character of the code.
This is defined as 
$$
R=\frac{k}{n}
$$
where $k$ is the dimension of the code and $n$ is the size of the code.

The intuitive explanation would be that, you need $k$ characters to carry all the information required, but you are using $n$, hence each character carries $\frac{k}{n}$ of the information it would have carried without redundancies.

A high rate implies less redundancies.

---
# References
