---
tags:
  - Assignment
---

# SVA Assignment 0
Name: Shubh Sharma

## Section 1
Skip :p 

## Section 2
### b

#### 1
```py
A = Bool('A')
B = Bool('B')
C = Bool('C')

solve(
	Implies(A, Or(Not(B), Not(C))),
	Implies(B, Implies(A, Not(C))),
	Implies(C, And(A, B))
)
```

#### 2
One possible solution to the given set formulas would be
- `A` :=`True`
- `B` :=`True`
- `C` :=`False`

### a
#### 1
The sets satisfying the above formula are
```
[
	[
		x0 := 0
		x1 := 1
		y0 := 1
		y1 := 0
	],
	[
		x0 := 1
		x1 := 1
		y0 := 1
		y1 := 0
	],

]
```

Intuitively, we will have that `y0` will be `1` if and only if `x1` will be `1`, so we have those constraints. `y1` is fixed so we can let `x0` to be anything.

Sooooo, `x` represents numbers greater than or equal to `2`
#### 2
The $\text{QBF}$ representations of the above would be

$$
\exists x_{0} x_{1} y_{0} y_{1} \in \mathbb{B}, y_{0} \land (\lnot y_{1} \land x_{1} \iff y_{0})  
$$

Z3 gave the second solution when I checked the model.

## Section 3

### 1

```py
x0 = Int(' x0 ')
x1 = Int(' x1 ')
y0 = Int(' y0 ')
y1 = Int(' y1 ')
z1 = Int(' z1 ')
r1 = Int(' r1 ')
r2 = Int(' r2 ')

solve(
	r1 != r2, # Unsat Condition
	r2 == y0*y0, # Second Code
	And(         z1 == y0 ,
		And(     y1 == x0 ,
			And( x1 == z1 ,
				 r1 == x1*x1 )))
)
```

Z3 says that this is not satisfiable.

### 2
#### a
The changed formula would be 

$$
\begin{align}
\forall i, j(i&\leq 10 \\
\land i &\geq 0 \\
i &\ne 0 \implies (i+j \ne j)) 
\end{align}
$$


#### b
The correctness of this transformation comes from referential transparency. The transformation will always be correct if `a[j]` is not changed. Since the value of `a[j]` remains unchanged, each time we assign that value to something else, we don't need to do the less efficient lookup through the list `a`. Hence looking it up once and storing it up in a variable for efficient access is correct.