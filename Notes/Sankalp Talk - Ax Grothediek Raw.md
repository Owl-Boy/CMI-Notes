## Basics
```ad-note
title: theory
A *Theory* is a collection of true *sentences* about certain *structures* that staisfy some axioms.
```
> [!note] theore
> A _Theory_ is a collection of true _sentences_ about cretain _structures_ that satisfy some axioms.


[[First Order Logic]] is a good *Language* to frame these sentences in.

## Compactness
Given a language $\mathcal L$ , and theory $\mathcal T$ and a sentence $\phi$.
We say $T\vdash\phi$ means that $\phi$ can be proven using $T$.

We say $\phi$ is a consequenc of $T$ if all models of $T$ satisfy $\phi$ 

Godel's completeness theorem states:
$$
\mathcal T \vDash \phi \iff \mathcal T\vdash\phi
$$
```ad-note
title: Compactness
If $\mathcal T$ is a theory such that every finite subset is satisfiable, then $T$ is satisfiable
```

this is called compactness because we can say that the in the power set of $T$, the collections of all subsets of $\mathcal T$ that contain $\varphi$ is an open set. Then we just have that the space is compact. This relates to the [[Stone's Representation Theorem]].

In the language of rings, the definable sets are varieties.

## Theory of Algebraically Closed Fields
The language is the language of Ring theory $\langle \cdot,+,0,1\rangle$ 
Axioms
- $\exists 0$
- $\exists 1$
- $\forall a_0\dots a_{n} \exists x (x^n +a_{1}x^n-1 \dots a_{0}=0)$

```ad-note
title: Theorem
Any two uncountable algebraically closed fields of the same characteristic are isomorphic $\iff$ Their cardinality is the same.
```

A theory $\mathcal T$ is called $\kappa-$categorical if all models of size $\kappa$ are isomorphism

```ad-note
title:Theorem
Algebraically Closed Fields of a given characteristic are complete.
That is all models satisfy sentences, or non of the models satisfy the sentences.
```

```ad-note 
title:theorem
Every injective polynomial mapping from $\mathbb C^n$ to $\mathbb C^n$ is also surjective.
```
 The point is you write the above statement in the language, say $\Phi_{n,d}$ states that for a fixed $n$ and $d$
 Now 
```ad-todo
Read the Lecture notes.
```
