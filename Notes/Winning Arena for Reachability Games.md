---
tags:
  - Note
---
202403201203

Tags : [[Games on Graphs]]
# Winning Strategy for Reachability Games
---
>[!tldr] Goal
>***Elster*** wants to reach a particular node $x$ in the graph. We want to partition the arena into the winning region for ***Elster***($\mathcal A_E$) and ***Adler***($\mathcal A_{A}$).

To do the following, we will start with an empty $\mathcal A_E$ and will incrementally add elements to it till we are done.

We define the following function to increment the set.
```
pre(S : Set) -> Set {
    S' = []
    forall (v in V_E | v is adjacent to S)
        S'.add(v)
    forall (v in V_A | v is only adjacent to S)
        S'.add(v)
    return S'
}
```

^134833

>[!idea]
>This reads as, if the vertex belongs to ***Elster*** and is next to his arena then it belongs to the arena. And if the vertex belongs to ***Adler*** and is forced to go into ***Adler*** region then it belongs to ***Elster*** region.

The use the above idea in the next algorithm.

```
let A_E(0) = [x]
until A_E(i) stabilizes:
   A_E(i+1) = pre(A_E(i)) \/ A_E(i)
end until at n
return A_E(n)
```

^693834

If $\mathcal A_E(i)$ stabilised for $i=k$ we let $\mathcal A_E = A_E(k)$ and $\mathcal A_A = V \setminus A_E$.

The strategies related to the arena are discussed in [[Winning Strategy for Reachability Games]] 

---
# References
[[Strategy for Games on Graphs]]
[[Winning Arena for Büchi Games]]
[[Winning Strategy for Büchi Games]]
[[Winning Strategy for Reachability Games]]