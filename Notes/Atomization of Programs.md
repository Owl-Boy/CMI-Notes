---
tags:
  - Note
---
202408092108

Tags : [[Concurrent Programming]]
# Atomization of Programs
---
As given in the example, our program for our [[Motivation for Concurrency Theory#The Counter|Counter]] has a "danger zone" or a "critical zone" that is problematic to run in parallel and hence atomization of chunks of programs are important.

Atomization different sections of the programs take an important part in safe allocation of resources to different threads. So we want our implementation of Atomiztion to follow these properties
- [[Mutual Exclusion]] : The critical section is executed by one threat a time
- [[Deadlock-freeness]] : At least one thread eventually executes the critical section
- [[Starvation-freeness]] : Each thread gets to execute the critical section eventually since it starts its lock.

Locks are the standard way to implement this atomization in code. Two correct implementation of locks is given in [[Starvation-freeness]]

---
# References
