---
tags:
  - Note
  - Incomplete
---
202311041711

Tags : [[Programming Languages]], [[Lambda Calculus]]
# Pattern Matching to Ordinary Lambda Calculus
---
Here we remove the pattern matching used in [[Enriched Lambda Calculus]].

For [[Variable Rule for Match Function|variable pattern]] we don't have to do anything. For the Other patterns we can do the following

- [[Constant Pattern to Lambda Calculus]]
- [[Product Constructor Pattern Matching to Lambda Calculus]]
- [[Sum Constructor Pattern Matching to Lambda Calculus]]

---
## Reducing the Number of Built-in Functions
The trouble with the above 3 steps is that they introduce a lot of built in functions for each constructor.

The idea is to give each constructor a tag, and have a general function that takes in the tag and arity of the constructor as in input to return a function which acts the same. This is the simplification that we get

- $s$ (sum constructor) is replaced with $\text{PACK-SUM-d-r}_{s}$
- $\text{UNPACK-SUM-s}$ is replaced with $\text{UNPACK-SUM-d-r}_{s}$
- $t$ (product constructor) is replace with $\text{PACK-PRODUCT-d-r}_{t}$
- $\text{UNPACK-PRODUCT-t}$ is replaced with $\text{UNPACK-PRODUCT-d-r}_{t}$
- $\text{SEL-t-i}$ is replaced with $\text{SEL-r}_{t}\text{-i}$
where
- $r_{s}$ is the arity $s$
- $d$ is the structure tag of $s$
- $r_{t}$ is the structure tag of $t$

---
## Summary
![[Pasted image 20231104183228.png]] ^1331d9

---
# References
[[Enriched Lambda Calculus]]
[[Patterns]]