---
tags:
  - Note
---
202310251710

Tags : [[Programming Languages]]

---
# Constructor Rule for Match Function

## Example
After evaluating the example in the [[Match Function for Enriched Lambda Calculus|main note]] using the [[Variable Rule for Match Function|Variable Rule]] once, we get

```haskell
demo =
  \u1. \u2. \u3. 
    match [u2, u3]
          [ ( [[],     ys],     (A u1 ys)  ),
            ( [(x:xs), []],     (B u1 x xs)),
            ( [(x:xs), (y:ys)], (C u1 x xs y ys)) ]
          ERROR
```

This this an obvious situation where we should involve $\text{case-}$expressions, on solving this using the *Constructor rule* we get

```haskell
demo =
  \u1. \u2. \u3. 
    case u2 of
      []      => 
          match [u3]
                [( [ys], (A u1 ys) )]
	            ERROR
	  (u4:u5) => 
	      match [u4, u5, u3]
				[( [x, xs, NIL], (B u1 u4 u5)),
				[( [x, xs ,(y:ys)], C u1 u4 u5 y ys)]
				ERROR
```
which on applying variable rule in both places becomes.

```haskell
demo =
  \u1. \u2. \u3. 
    case u2 of
      []      => 
          match []
                [( [], (A u1 u3) )]
	            ERROR
	  (u4:u5) => 
	      match [u3]
				[( [NIL], (B u1 u4 u5)),
				[( [(y:ys)], C u1 u4 u5 y ys)]
				ERROR
```

---
## Constructor Rule
The *Constructor Rule* deal with the situation where given sum type, all options are constructors of the type, we can use $\text{case-}$expressions to write them while eliminating one of the variables used.

The call of *Match* for constructor rule will have the form
```haskell
match (u:us) (qs1 ++ ... ++ qsk) E
```
where each `qsi` has the form 
```
[ (((ci psi1'):psi1), Ei1),
  ...
  (((ci psim'):psim), Eim)] 
```
that is, its list of constructor pattern matches for the first argument, rest of the pattern and the expressions, for the constructor $c_{i}$.

Then the above expressions is evaluated to
```haskell
case u of
  c1 us1' => match (us1' ++ us) qs1' E
  ...
  ck usk' => match (usk' ++ us) qsk' E 
```
where each `qsi'` is of the from 
```
[ ((psi1' ++ psi1), Ei1),
  ...
  ((psim' ++ psim), Eim) ]
```
that is, for each branch of the case, the new variables used in the constructor are also added , but only via the variable rule.

--- 
## Optimisation
As seen in the [[Constructor Rule for Match Function#Constructor Rule|above section]]. The expression $E$ is repeated several times, this can cause a huge blow up of the compiled file size if $E$ is huge. To deal with that we use $\text{FAIL}$ and $\triangleright$ and rewrite the above definition in the following way

![[Optimisations for Overlapping Patterns#^11a949]]

discussed with and example in [[Optimisations for Overlapping Patterns]].

---
## Termination
The [[Variable Rule for Match Function|Variable]] and [[Empty Rule for Match Function|Empty]] Rules terminate in a single step, the termination of this rule is not obvious, although not too hard.

Say a type has $n$ constructors and the maximum number of parameters for a given constructor is $m$.
Then after applying the rule, the patterns(say we have $x$ patterns) are split into $n$ branches of the cases statement, so the number of patterns does not increase. 
For each pattern the number of variables used in them increase at most by $m$, but all increase can be dealt with using the variable rule.
We now still have $x$ patterns, but after applying the variable rules to remove the new variables at most $m$ times for each pattern, we are now left with $x$ patterns with one less variable in them.

This entire process took 1(making the case conditions) + mx(getting rid of new variables) steps to complete the procedure and we end up with $n$ branches. 

Hence the pattern match will terminate.

---
# References
- [[Empty Rule for Match Function]]
- [[Variable Rule for Match Function]]
- [[Match Function for Enriched Lambda Calculus]]
- [[Mixture Rule for Match Expression]]