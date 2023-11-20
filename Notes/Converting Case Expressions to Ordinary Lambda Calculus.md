---
tags:
  - Note
  - Incomplete
---
202311051411

Tags : [[Programming Languages]], [[Lambda Calculus]]
# Converting Case Expressions to Ordinary Lambda Calculus
---
[[Translating Haskell Programs to Lambda Calculus]] introduces a lot of case expressions. Here we give a conversion from *Case Expressions* to *Ordinary Lambda Calculus*.

As with [[Patterns|Constructor Patterns]] there are two types of *Case Expressions*

## Case-expressions involving Product Type
The general case expression of product type is of the form
```haskell
case v of
    t v1 v2 ... vr = E1
```

Since the constructor is degenerate, there is no need to check for nested patters so we can directly convert it to

```haskell
case v of            === UNPACK-PRODUCT-t (\v1 ... vr.E1) v
    t v1 ... vr => E1
```

---
## Case-expressions involving Sum Type
If the constructors are of sum-type then the *case-expression* would look like
```haskell
case v of
    s1 v1 ... vr1 => E1
    ...
    sn v1 ... vrn => En
```
which can be converted in the following way
```haskell
case v of
    s1 v1 ... vr1 => E1
    ...
    sn v1 ... vrn => En
===
CASE-T v (UNPACK-SUM-s1 (\v1...vr1.E1) v)
         ...
         (UNPACK-SUM-sn (\v1...vrn.En) v)
```
where `CASE-T`selects one of its $n$ arguments based in which constructor matches.

---
## Converting Case-expressions to let-expressions
[[let-expressions in Enriched Lambda Calculus|let-expressions]] can be implemented much more efficiently than lambda abstractions

### Product Type
The following transformation can be used in case of product type
```haskell
case v of           ===  let v1 = SEL-t-1 v
	t v1...vr => E1          v2 = SEL-t-2 v
	                         ...
	                         vr = SEL-t-r v
	                     in E1
```
which is an equivalent translation as the previous one which can be confirmed by simplifying the let expressions as discussed in [[let(rec)-expressions to Ordinary Lambda Calculus]].

### Sum Type
A similar idea as the previous one can be used to convert sum types
```haskell
case v of
    s1 v1 ... vr1 => E1
    ...
    sn v1 ... vrn => En
===
CASE-T v (let v1 = SEL-SUM-s1-1 v
              ...
              vr1 = SEL-SUM-s1-r1 v
          in E1)
         ...
         (let v1 = SEL-SUM-sn-1 v
              ...
              vrn = SEL-SUM-sn-rn v
          in En)
```
This does increase the complexity of the expression, but it achieves the important objective of eliminating lambda abstractions, which means that this will run significantly faster on all but the simplest scenarios

---
# References
[[Converting Enriched Lambda Calculus to Ordinary Lambda Calculus]]