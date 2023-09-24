202303291503

Type : #Note
Tags : [[Lambda Calculus]]

---
# Pairs in Lambda Calculus
Pair are a collection of two values considered together.
To construct a useful definition of pairs, we require a method to pull out components of a pair to use them separately. 
A good candidate for a choosing function would be somewhat similar to the [[Church Booleans]] as $TRUE$ takes in two inputs and returns the first one and $FALSE$ takes in two inputs and returns the second one.
This idea is actually enough to provide a working description of pairs as 
$$
PAIR:=\lambda ab.(\lambda v.vab)
$$
Where $v$ is supposed to be a **Church Boolean**.

The pair function take in two arguments are returns a function which in a sense stores the two inputs, it wait for a selector function when it will later return one of the values 

So while using the booleans as selector functions, we can use the following aliases

$$
FIRST:= TRUE,\;\;\; SECOND:=FALSE
$$

```ad-info
title: infix notation
we can write $PAIR(a,b)$ as $(a, b)$
and we can write the first and second function in following way 
$(a,b).1 = a$
$(a,b).2 = b$
```


---
# References
[[Church Numerals]]
