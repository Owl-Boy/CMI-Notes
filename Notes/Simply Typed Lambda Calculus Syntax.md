202308281408

Type : #Note 
Tags : [[Type Theory]] [[Lambda Calculus]]

---
# Simply Typed Lambda Calculus Syntax
The types of the terms are simple propositions and implications,  **Context Free Grammar** for types is 
$$
\begin{matrix}\Phi & := & p & | & \varphi\longrightarrow\psi\end{matrix}
$$

And there are two styles of typing lambda calculus:
- Curry Style:![[Curry-Style typing#^f4b8ba]]
- Church Style:![[Church-Style typing#^111a8d]]
The two styles are equally powerful.

And we have the typability rules:
$$
\begin{matrix}(\text{Ax}) & \Gamma,x:\tau\vdash x:\tau \\ (\text{App}) & \frac{\Gamma\vdash M:\sigma\to\tau\quad\quad\Gamma\vdash N:\sigma}{\Gamma\vdash MN:\tau} \\ (\text{Abs}) & \frac{\Gamma, x:\sigma\vdash M:\tau}{\Gamma\vdash\lambda x.M:\sigma\to\tau}\end{matrix}
$$

^f1c6a3

Some important questions related to this are:
- Is a term **Typable?**
- Can we compute a principle type, if the term is typable: **Type Inference**
- Given a Type, are there terms that belong to this type: **Type Inhabitance**


Examples:
Curry Style:
![[Curry-Style typing#^84a06b|Curry Style]]

Church Style:
![[Church-Style typing#^acb5f4]]

---
# References
[[Not Unification Algorithm For Type Inference]]