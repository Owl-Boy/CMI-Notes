---
tags:
  - Example
---

202310292137

tags : [[Programming Languages]]

#  Ordering Equations in Uniform Definitions
---
>[!note] Theorem
>If a definition is [[Uniform Definition of Haskell Functions|uniform]], changing the order of the equations does not change the meaning of the definitions.

^fd86df

**Proof:**
There are 3 rules that are to be applied to simplify the definitions, we induct on the number of variable in the first argument to the [[Match Function for Enriched Lambda Calculus|match function]]:
- [[Empty Rule for Match Function]]
	- Empty Rule is only applied on singleton sets of equations, hence any change of ordering trivially does not change the last step. This is the base case for our induction
- [[Variable Rule for Match Function]]
	- Applying variable rule returns a match function with the size of the variable list reduced by one. 
	- Consider a different ordering of equations, applying the variable rule now gives the above result but in a different, order. 
	- By induction we can say that these will have these definitions will have the same meaning.
- [[Constructor Rule for Match Function]]
	- For the constructor rule, the ordering between two element that have different constructors for the first variable does not matter, as they will be taken to different branches of the case statement.
	- To show that the ordering does not matter even with the same constructor we apply the constructor rule. Since we are looking at equations that use the same constructor, we only need to look at one branch. We then apply the variable rule for the new variables added. And we get a set of equations with strictly less terms.
	- We change the original ordering of equations and do the same set of operations. Now by induction we get that changing the order preserves meaning.
	- Since we have already proved this for variable rule, we can look at the result before we started applying the variable. 
$\square$

---
# Related
[[Uniform Definition of Haskell Functions]]
[[Match Function for Enriched Lambda Calculus]]
