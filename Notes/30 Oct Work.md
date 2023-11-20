---
tags: Remove
---
L- language
D be a non empty set
A is the universe
A D-structure would be [[Semantics of First Order Logic#First Order Structures|First Order Structure]]
but relations are take stuff to D

A valuation takes stuff to the universe like it normally does
D will be given structure like [[Heyting Algebra]] or [[Boolean Algebra]], but the structure needs to complete

$r:A^x\to D$
$[[\bot]]=0$
$[[\phi \land \psi]]=[[\phi]]\sqcap [[\psi]]$
$[[\phi \lor\psi]]=[[\phi]]\sqcup[[\psi]]$
$[[\psi\to\psi]]=[[\phi]]\implies[[\psi]]$
$[[\exists x \phi]]_{\rho}= \sup\{[[\phi]]_{\rho'}\}$
where rho rewrites x. for all rewriting of x
$[[\forall x \phi]]_{\rho}= \inf\{[[\phi]]_{\rho'}\}$

Then we proved some of the formulas are not valid in first order intuitionistic logic, examples were given in the book

Then we showed soundness