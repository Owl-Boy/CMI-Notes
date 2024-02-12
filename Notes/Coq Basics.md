---
tags:
  - Note
  - Incomplete
---
202401131401

Tags : [[Programming Languages]], [[Type Theory]], [[coq]]
# Coq as Functional Programming Language
---

*Coq* is an interactive theorem prover that is built on top of a subset of *OCaml* called *Galena*.

## Datatypes and Functions
```coq
Inductive Day: Type :=
  | monday
  | tuesday
  | wednesday
  | thursday
  | friday
  | saturday
  | sunday.
```

This is an enumerated data type equivalent to `data` in *haskell* or `enum` in *rust*.
We can also define datatypes using other types, like 
```coq
Inductive rgb : Type
  | red
  | green
  | blue.
Inductive color : Type
  | black
  | white
  | primary (p : rgb)
```

We define functions of datatypes in the following manner:
```coq
Definition next_weekday (d: day) : day :=
  match d with
  | monday => tuesday
  | tuesday => wednesday
  | wednesday => thursday
  | thursday => friday
  | friday => monday
  | saturday => monday
  | sunday => monday
  end.
```
We need a special keywords for functions that are recursive

```coq
Fixpoint mult (n m : nat) : nat :=
  match n with 
  | O => O
  | S n' => plus m (mult n' m)
  end.
```

## Important Keywords
- `Theorem/Lemma/Example...`: Definition of a proposition
- `Proof`: To give a proof for a proposition defined by above statement.
- `Compute`: Evaluates an expression.
- `Check`: Gives the type of an expression.
- `Admitted`: Stop trying to prove the theorem and assume it to be true.
- `Abort`: Step trying to prove the theorem and assume it to be false.
## As a Theorem Prover
Consider the following 
```coq
Check next_weekday tuesday.
(* ==> wednesday : day *)
```

We can define and prove a simple check of 
```coq
Example nxt_wdk_aft_tue: 
  (next_weekday tuesday) = wednesday.
Proof. simpl. reflexivity. Qed.
```

The above example claims that the next weekday after a `tuesday` is a `wednesday`.
The proof takes two steps
- `simpl` - simplifies the expression
- `reflexivity` - check of both expressions around the equality match.

## Modules
breaking code into modules for organization is nice
```coq
Module Playground.
  Definition foo : rgb := blue.
End Playground.

Definition foo : bool := true.

Check Playground.foo . (* ==> rgb *)
Check foo . (* ==> bool *)
```

## Defining Notation
We can make our own notation for to make code look pretty

```coq
Notation "x + y" := (plus x y)
  (at level 50, left associativity):nat_scope.
```

---
# References
[[Basic ways to prove things using coq]]