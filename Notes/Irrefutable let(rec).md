---
tags:
  - Note
  - Incomplete
---
202311071911

Tags : [[Programming Languages]]
# Irrefutable let(rec)
---
**Irrefutable let(rec)** expressions are expressions that cannot return a $\text{FAIL}$ when evaluated.
[[Patterns#Sum Constructors|Sum Patterns]] and [[Patterns#Constants|Constant Patterns]] are the only cases where $\text{FAIL}$ can be produced, hence we define **Irrefutable let(rec)s** as
>[!note] Definition
>A pattern $p$ is said to be irrefutable if it is 
>1. either a variable $v$
>2. or a product pattern $(t p_1, \dots p_r)$ where each $p_i$ is irrefutable

---
# References
[[Conformality Transformation on let(rec) expressions]]