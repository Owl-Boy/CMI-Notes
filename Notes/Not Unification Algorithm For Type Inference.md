202308282208

Type : #Note 
Tags : [[Type Theory]], [[Lambda Calculus]]

---
# Not Unification Algorithm For Type Inference

**Unification** is an algorithmic process for solving equations between symbolic expression.

It's famous use cases are **Logic Programming** and in making type systems for programming Languages, especially the Hindley Milner based **Type Inference** Algorithm. Here it is being used for type inference of simply typed lambda calculus.

This algorithm gives the most general type for a give lambda expression

```ad-warning
This is not the usual [[Unificate Algorithm For Type Inference|Unification Algorithm]]. I have figured it out based on my partial memory from whatever prof did in class.
```

The procedure involves assigning types, then finding constraints and solving them. 

I will use the following example to show the procedure 
$$
S::=\lambda xyz.xz(yz)
$$
## Example walk through
```
\xyz.xz(yz)
```

### Step 1
Explicitly write out all brackets are assign ad-hoc types to everything
```
\x.(\y.(\z.((xz)(yz))))    T
 x                         X
    \y.(\z.((xz)(yz)))     U
     y                     Y
        \z.((xz)(yz))      V
         z                 Z
            (xz)(yz)       W
             xz            P
             x             Q
              z            R
                 yz        S
                 y         L
                  z        M
```

### Step 2
Find out all the constraints 
```
X = Q
Y = L
Z = R = M
```

and all of the applications give the following  constraints
```
Y = Z -> S   (from yz : S)
X = Z -> P   (from xz : P)
P = S -> W   (from (xz)(yz) : W)
```

The abstractions give the constraints
```
V = Z -> W
U = Y -> V
T = X -> U
```

### Step 3
Solve the constraints
```
X = Z -> S -> W
U = (Z -> S) -> (Z -> W)
T = (Z -> S -> W) -> (Z -> S) -> Z -> W
```

And we have no constraints on $Z,S$ and $W$

This gives the type of the Lambda Expression on renaming the type variables
$$
S::=\quad \lambda xyz.xz(yz)\quad:\quad(\sigma\to\tau\to\theta)\to(\sigma\to\theta)\to\sigma\to\theta
$$

---
# References
[[Simply Typed Lambda Calculus Syntax]]
[[Curry-Style typing]]
[Northeastern University Notes On Type Inference](https://course.ccs.neu.edu/cs4410sp19/lec_type-inference_notes.html#%28part._.Unification%29)
[Cornell University Notes on Type Inference](https://www.cs.cornell.edu/courses/cs3110/2016fa/l/17-inference/notes.html)
[Wikipedia for Type Inference](https://en.wikipedia.org/wiki/Type_inference?useskin=vector#cite_note-Damas-and-Milner-1982-16)
[Wikipedia for Unification Algorithm](https://en.wikipedia.org/w/index.php?title=Unification_(computer_science)&useskin=vector#A_unification_algorithm)