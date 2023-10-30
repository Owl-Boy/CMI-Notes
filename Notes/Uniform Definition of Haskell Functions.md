---
tags:
  - Note
---
202310291510

Tags : [[Programming Languages]]
# Uniform Definition of Haskell Functions
---

One of the more complicated rules for evaluating [[Match Function for Enriched Lambda Calculus|match]] is the [[Mixture Rule for Match Expression|mixture rule]]. This is also the only rule because of which it is not possible to change the order between non-identical pattern matches.

The subclass of definitions that allows are worth studying for two reasons.
- It makes it easier to reason pattern matching functions. 
	- One instance being the [[False Assumptions easy to make about Patterns]]
- They are easier to compiler because they guarantee to avoid certain kinds of inefficiencies.

---
## Uniform Definitions
>[!info] Definition
>A set of equations is called uniform if one of the following three conditions hold.
>1. Either all equations begin with the variable pattern and applying the [[Variable Rule for Match Function|variable rule]] yields a uniform definition
>2. All equations begin with the constructor pattern, and applying the [[Constructor Rule for Match Function|constructor rule]] yields new sets of equations that are also uniform
>3. all equations are have an empty list of patterns, so the [[Empty Rule for Match Function|empty rule]] apply and there is at most one equation in the set.

That is, a set of rules that can be compiled without using the [[Mixture Rule for Match Expression|mixture rule]] and if the [[Empty Rule for Match Function|empty rule]] is only applied to sets containing 0 or 1 equation.

---
## Reasoning about Uniform Definitions

There are two nice theorem's related to **uniform definitions**
![[Ordering Equations in Uniform Definitions#^fd86df]]
and
![[Independence of meaning from changing the order on the left hand side implies uniform definition#^b54fe4]]

These two theorems make the definition of functions much more intuitive as it helps us evade the easy to make [[False Assumptions easy to make about Patterns]] while writing programs as termination of the argument is not always in the mind of someone programming in the language.

---
## Implementing Uniform Definitions
There 3 problems that occur with non uniform definitions
- Resulting case expression may examine a variable more than once.
- Compiler must used modified constructor rule to avoid duplicating right hand side of equations
- The resulting expression may contain $\triangleright$ and $\text{FAIL}$. Implementing such expressions efficiently requires additional simplification rules and special ways of implementation.

---
# References
[[Match Function for Enriched Lambda Calculus]]
[[Patterns]]