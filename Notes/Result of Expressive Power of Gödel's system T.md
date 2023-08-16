202307261907

Type : #Note
Tags : [[Type Theory]]

---
# Result of Expressive Power of Gödel's system T
If $t$ is a closed term of the type $\text{Int}\to\text{Int}$, then it induces a function $|t|$ from $\mathbb N\to\mathbb N$
$$
|t|(m)=n\iff t\ \overline m\rightsquigarrow\overline n 
$$
And like wise a closed term of  the type $\text{Int}\to\text{Bool}$ induces a predicate on $\mathbb N$
$$
|t|(m)\text{ holds} \iff t\ \overline m\rightsquigarrow \text T
$$
The functions $|t|$ are clearly calculable and normalization theorem gives proof for the termination of all the algorithms obtained from $\text{T}$ .

To prove the reducibility of $t$, we need to be able to the reducibilities for $t$ and its subterms. So we should be able to write finite number of reducibilites, which can be written using Peano Axioms. And to be able to reason on this finite number of reducibilities using induction. Which can also be done using the Peano Axioms, so $|t|$ is totally provable in Peano Arithmetic

---
# References
[[Gödel's system T]]