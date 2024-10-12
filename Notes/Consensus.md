---
tags:
  - Note
---
202409262009

Tags : [[Concurrent Programming]]
# Consensus
---
>[!note]
>Not all synchronisation instructions are created equal. It might not be possible to write some data structures and programs with a given subset of instructions. One possible hierarchy  is given by *Consensus numbers* which is explained below.

>[!question] Consensus
>There are $n$ threads and each thread is assigned an "input value" from a finite domain $D$. They are given "primitives" and a set of "synchronisation functions" using which they can communicate with each other.
>
>Each thread also has a *decide* function that it uses when it wants to complete its computation by picking a value from $D$. The goal is for all the threads to decide on the same value.

>[!definition] Consensus Number
>A given set of "synchronisation instructions" have their consensus number as $n$ if, in a system of more than $n$ threads, it is impossible to implement a [[Bounded Wait-freeness|wait-free]] or [[lock-free]] object using the instructions provided. 

---
# References
