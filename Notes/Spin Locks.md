---
tags:
  - Note
  - Incomplete
---
202408281808

Tags : [[Concurrent Programming]]
# Spin Locks
---
>[!error] Welcome to the Real World
>Both compilers and hardware reorder instructions to improve performance. Unfortunately, most compiler and hardware optimisations are designed for sequential systems, which are designed in a way that the hardware semantics can be ignored while designing software. This does breaks down really quickly for concurrent systems. 
>
>For example, [[Starvation-freeness#Peterson Lock|Peterson Lock]] can no longer guarantee [[Mutual Exclusion]] under such reorderings. 

Hardware Manufacturers provide *barrier* instructions which stop the hardware and compiler from reorder instructions across the *barrier*. But they significantly slow down (kills the cache?) the processor so it should not be used carelessly.

To get around that issue, hardware manufacturers provide atomic "read-write-modify" instructions such as `get_and_set()` and `compare_and_set()` which execute atomically. These functions can be used to synchronise instructions and are much cheaper to use than barriers, hence it may be a sensible idea to design locks around these instructions.

The following are a set of locks that follow:
- [[TAS Lock]]
- [[TTAS Lock]]
- [[Backoff Lock]]

---
# References
