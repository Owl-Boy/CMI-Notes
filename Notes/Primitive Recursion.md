202304011804

Type : #Note
Tags : [[Lambda Calculus]]

---
# Primitive Recursion

$f:\mathbb N^{k+1} \to \mathbb N$ is obtained by **Primitive Recursion** from the total functions $g:\mathbb N^{k}\to \mathbb N$ and $h:\mathbb N^{k+2}\to \mathbb N$ if 
$$
\begin{align*}
f(0,\vec n)&= g(\vec n)\\
f(i+1, \vec n)&= h(i,f(i,\vec n), n)
\end{align*}
$$

which is equivalent to the for loop
```
result = g(n1, n2, n3 ... nk) // f(0,n)=g(n)
for i in 1..n:
	result = h(i, result, n1, n2, n3 .. nk) //recursion
return result
```

Example of a non trivial function which can use primitive recursion in its definition is

The above `for loop` and recursion can sort be expressed in lambda calculus in the following way which isn't correct but can be fixed and gets the idea across

Given two lambda expressions for functions $h$ and $g$, we need to construct a lambda expression for a function which is defined in the above manner

$$
f(i,n). \text{if $i=0$ then $g(n_1,n_{2} \dots n_{k})$ else h(pred(i), f(pred(i)), n )}
$$
here we need to make sure we hvae the ability to do a a few things
- We need to have booleans, which we do
- We need to be able to have if conditions, which we do because of out defintion of booleans, its easy to model that
- We need to be able to do recursion....

To make it clear how we approach the third one, lets make the expression, closer to lambda calculus, 
$$
F:= \lambda i\ n_{1}\dots n_{k}. 
\text{IsZero}\quad i\quad 
    (G\; n_{1}\dots n_{k})\quad 
    (H\; 
        (\text{Pred}\quad i) 
        (F\quad (\text{Pred}\quad i)\quad n)
        n)    
$$
The only thing not fixed is that $F$ is used inside its definition. to make things easier, lets pull out $F$ 

$$
F:= \lambda f\ i\ n_{1}\dots n_{k}. 
(\text{IsZero}\quad i\quad 
    (G\; n_{1}\dots n_{k})\quad 
    (H\; 
        (\text{Pred}\quad i) 
        (f\quad (\text{Pred}\quad i)\quad n)
        n)) \quad 
F  
$$
now the part before $F$ has become a perfectly valid lambda expression so we can rewite it as 

$$
F:= CF
$$

---
# References
[[Functions Computable in Lambda Calculus]]