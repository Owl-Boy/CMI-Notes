---
tags:
  - Note
  - Incomplete
---
202405141605

Tags : [[Model Repair and Conformance Checking of Time Aware Models (MOC)]]
# Model Repair and Conformance Checking of Time Aware Models
---
The research is going to about Time Aware models. Since Petri nets are a fairly general and powerful enough model, also fairly convenient to use to model concurrency, the project will deal with [[Time Petri Net]].

Given a TPN $N$ and a log $L$ we will do conformance checking on these two to measure two criteria : Fitness and Precision as define in [[Formalising Precision and Fitness for Time Petri Nets]]. 

For the sake of simplicity we will start with specific 

Specifically with the help of [[Alignments (Conformance Checking)|Alignments]] and [[Anti-Alignments (Conformance Checking)|Anti-Alignments]], we can find specific instances of runs that would demand a change to the model. 

Once we have these, we would like to edit our TPN in such a way that the modified language would include the alignment and anti-alignment, this change will mostly be done by editing static interval function of the petri net to include runs with different time intervals.

We would also like to consider that there is a cost to edits, hence we would like to make efficient edits

Baby steps:
- sequential case
- acyclic case
- confusion free case


---
# References
