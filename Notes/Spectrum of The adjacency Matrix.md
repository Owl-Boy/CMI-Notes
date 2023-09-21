202308121508

Type : #Note
Tags : [[Algebraic Graph Theory]]

---
# Spectrum of The adjacency Matrix
The **Spectrum** of the adjacency matrix is the matrix that contains all pairs of eigenvalues and their multiplicity
$$
\text{Spectrum}(A)=\begin{pmatrix}\lambda_{1} & \lambda_{2} & \dots \\ m_{1} & m_{2} & \dots \end{pmatrix}
$$

For example
$$
\text{Spectrum}(J)=\begin{pmatrix}4 & 0 \\ 1 & 3\end{pmatrix}
$$
and
$$
\text{Spectrum}(I)=\begin{pmatrix}1 \\ 4\end{pmatrix}
$$
Using these we can find the eigenvalues of 
$$
\begin{bmatrix}0 & 1 & 1 & 1 \\ 1 & 0 & 1 & 1 \\ 1 & 1 & 0 & 1 \\ 1 & 1 & 1 & 0\end{bmatrix}
$$
by subtracting the eigenvalues of $J$ and $I$.

---
# References
[[Traces of Powers of Adjacency Matrices]]
[[Spectrum of a Cube Graph]]
[[Spectrum of the complement of a graph]]