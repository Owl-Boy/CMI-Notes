---
tags:
  - Example
---

202405161018

tags : [[Conformance Checking]]

# Greedy Cost Bounded Model Repair for Sequential Time Petri Nets with Delay Only Distance
---
>[!question] The Problem
>Given a Sequential Time Petri Net $N$ (or equivalently a Linear Causal process), a log $L$ of trances and a budget $\beta$. What are the optimal edits that can be made to $N$ under the given budget to minimise the distance of the model from the log?


>[!note] Details
>- The *fitness measure* considered here is the maximum delay-only distance of the model from the log, where having a lower distance means a higher fitness, hence we would like to deal with the log entries that are the furthest away from the model. 
>- Valid edits: The edits on the petri nets involve taking the interval `[at, bt]` corresponding to the transitions `t` and changing to `[at+d, bt]`  or `[at, bt+d]` with cost `d`.

First we find an upper bound on the improvements that can be made under a given budget.

>[!theorem] Theorem: Given the above problem with budget $\beta$ we can change the fitness by at most $\beta$. 
>We distribute the budgets over edits on multiple transitions if required. 
>For each transition
>- If `closest(s, [a, b])` is `s` itself, then the distance for this transition is $0$ and cannot be improved.
>- If `s > a` then we can increase `a` by at most the budget assigned for the transition, similarly for `s < b`, hence for each transition edit, the fitness measure will improve at most by the budget for the transition
>
>Thus the total fitness change will be at most $\beta$.

If there are multiple log traces that are furthest away from the model, then dealing with just one of them is not enough as it will not change the fitness, hence all such traces must be simultaneously handled.

Which also implies that we should prioritise edits that improve multiple log traces at once.

## Algorithm
The Algorithm Follows the following steps
- ***Finding a set of Candidates runs in Petri Net***
	- We only need to look at the alignment for each run in the log, then we recompute the alignments again using the given ones, improving those improves the overall fitness of the model.
- ***Finding the Furthest Log Traces in the Above Set***
	- These are the only ones that affect the fitness of the model, hence we only need to improve these. The traces that are already in the log, need not be considered at all.
- ***Finding the Transitions that need to be Edited for Maximum Improvement in Fitness***
	- This can be done by figuring out which transitions effect the distances from which log traces and using linear programming to find the best one.
- ***Editing the transitions***
	- this needs to be done tell there is a new log trace that joins the set of furthest log traces, and the above steps need to be re-done.
- ***Repeat until the Fitness becomes Perfect or we run out of Budget***

### Maximal Trace Candidates
Using the helper functions discussed in [[Maximal Traces for Linear Time Petri Nets for Delay Only Distance]], we can build the following functions to get the list of alignments.

```
INPUT
L : list (traces) -- set of log traces
F : Linear Time Petri Net Flow Function

OUTPUT
A : list (traces) -- set of all alignments

FUNCTION all_alignments(L, F) := 
    let C = alignment_candidates(L, F)
    return filter_max(C, F)
```

### Finding the intervals that can be changed


---
# Related
[[Purely Timed Alignment Problem for Linear Time Petri Nets for Delay Only Distance]]
[[Formalising Precision and Fitness for Time Petri Nets]]
[[Maximal Traces for Linear Time Petri Nets for Delay Only Distance]]