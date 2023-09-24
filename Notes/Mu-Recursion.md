202304011804

Type : #Note
Tags : [[Lambda Calculus]]

---
# Mu-Recursion
$f:\mathbb N^{k}$ is obtained by  $\mu-$recursion from $g:\mathbb N^{k}\to \mathbb N$ if 
$$
\begin{equation}
f(\vec n)= 
    \begin{cases}  
        i & \text{if $g(i,\vec n)=0$ and $\forall j<i,g(j,n)>0$} \\
        \text{undefined}  & \text{otherwise}
    \end{cases}
\end{equation}
$$

This method is equivalent ot the while loop
```
i=0
while g(i, n1 .. nk) > 0:
	i = i+1
return i
```


---
# References
[[Functions Computable in Lambda Calculus]]
