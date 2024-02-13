---
tags:
  - Note
  - Incomplete
---
202401151001

Tags : [[coq]]
# Proof by Induction in Coq
---
Sometimes theorem require more than just a finite case analysis or can be completed with finite steps using rewrite rules.

The obvious solution is induction.
Consider the following definition of subtraction 
```coq
Definition minus (n : nat) (m : nat) : nat :=
  match n, m with
  | S n', S m' => minus n' m'
  |  _     _   => O
  end.
```

and now we want to prove the following:
```coq
Theorem minus_n_n:
  forall n:nat, n - n = 0.
```

We clearly require induction for this proof as the `simpl` keyword would be unhelpful as `n` can't be pattern matched. 
The proof for the above statement can be written in the following manner.

```coq
Theorem minus_n_n :
  forall n:nat, n - n = 0.
Proof.
  intros n. induction n as [|n' IH].
  - reflexivity.
  - simpl. apply IH.
Qed.
```
where `IH` is the induction hypothesis `n-n=0`

---
# References
