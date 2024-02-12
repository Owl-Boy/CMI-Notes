---
tags:
  - Note
  - Incomplete
---
202401131501

Tags : [[coq]]
# Basic ways to prove things using Coq
---

## Proof by Simplification
If we have datatypes and functions that precisely define the behaviour in some particular ways, so if we want to prove say.. that the given function computes the give some particular thing, we can check that by actually computing it.
This is can be specified to *coq* using the keyword `simpl`.

Another important keyword that can be used in `reflexivity`, which checks if two sides of an equation are the same.

```coq
Theorem plus_0_n : 
  forall (n : nat), 0 + n = n.
Proof.
  intros n. simpl. reflexivity.
Qed.
```

## Proof by Rewriting
After having a bunch of equality like theorems, we can used that for rewriting statements in other proofs.

This can be done where we have proved a conversion from one way to write something, to another write it, without necessarily giving a way to compute it.

```coq
Theorem plus_id : 
  forall (n m : nat), n = m -> n + n = m + m.
Proof.
  intros n m H.
  rewrite -> H.
  reflexivity.
Qed.
```

## Proof by Cases
Sometimes its easier, and sometimes its not possible to work without a case analysis. The `destruct` keyword in the following way

```coq
Theorem plus_1_neq_0:
  forall n: nat, n + 1 =? 0 = false.
Proof.
  intros n.
  destruct n as [| n'] eqn:E.
  - reflexivity.
  - reflexivity.
Qed.
```

The `[| n' ]` is a intro pattern and talks about what variable needs to be added in each case.

We add 2 cases and each case comes with 2 equations
`n = 0` and `n= S n'`

---
# References
[[Proof by Induction in Coq]]