---
tags:
  - Note
  - Incomplete
---
202403061803

Tags : [[Theory of Computation]]
# Random Access Machines
---
A *Random Access Machine (RAM)* models a computer with one accumulator (dedicated area for evaluating arithmetic expressions) and the instructions cannot edit themselves.

A *RAM* consists of
- A read-only input tape
- A write-only output tape
- An infinite sequence of Registers indexed by natural numbers
- Accumulator ($R_0$) - Its the first register used for computation.
- [[Program for RAM]]

The alphabet used in a *RAM* is $\mathbb{Z}$.

A *RAM* is trivially [[Turing Machines#^71be18|Turing Complete]]

>[!tip] Motivation
>In a *RAM* one can access any memory location(register) in constant time, and the nature of it having one accumulator makes it much closer in design to real-world machines that a typical [[Turing Machines|Turing Machine]]. This makes thinking about algorithms in a *RAM* much more natural.

---
# References
[[Program for RAM]]