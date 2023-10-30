---
tags:
  - Example
---

202310292154

tags : [[Programming Languages]]

#  Independence of meaning from changing the order on the left hand side implies uniform definition
---

>[!note] Theorem
>If the left-hand sides of a definition are such that the order of equations does not matter (regardless of the right hand side or condition parts of the equations), the definition is uniform
>

^b54fe4

We prove this by induction on number of variables to be pattern matched.
- [[Empty Rule for Match Function]]
	- Empty rule always picks the first equation in the set and falls through if it evaluates to $\text{FAIL}$.
	- If there are more than one definitions, consider the case where neither of them evaluate to $\text{FAIL}$, and are different, in that case ordering them will change the meaning and hence the set of equations can have at most 1 element.
	- By definition of [[Uniform Definition of Haskell Functions|uniform definitions]] we get the base case of induction
- [[Variable Rule for Match Function]]
	- If the set of equations follow the variable pattern, we apply the *variable rule* to get a set of uniform equations(by induction) and get that the set of equations was uniform
- [[Constructor Rule for Match Function]]
	- If the set of equations follow the constructor pattern, we apply the constructor pattern and then apply the variable rule repeatedly (can be 0) to get rid of all newly introduced variables.
	- If the original order of equations did not change the meaning of the function, then the order for this set will not matter either, so the new set of equations is uniform by induction.
	- Given that we have proved that if we apply the variable rule to get a set of uniform equations then the original set of was also uniform, we get that just after applying the constructor rule we get that for each constructor we get a set of uniform equations
	- This proves that the original set of equations was uniform
- [[Mixture Rule for Match Expression]]
	- This happens when the some of the elements of the set of equations match the variable patterns and some match the constructor pattern.
	- If we have a function that discard the first argument entirely, and gives some output, the order matters, because if the first equation follows the variable pattern or constructor pattern decides if the program terminates.
	- Hence there if we have to use the mixture rule, then the order of the left hand side matters hand hence the hypothesis fails.
$\square$ 

---
# Related
[[Uniform Definition of Haskell Functions]]
[[Ordering Equations in Uniform Definitions]]