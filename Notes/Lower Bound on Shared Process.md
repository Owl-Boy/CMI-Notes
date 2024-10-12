---
tags:
  - Note
---
202408220608

Tags : [[Concurrent Programming]]
# Lower Bound on Shared Process
---
All threads in a concurrent program with mutual exclusion can be considered to have 4 states
- *Quiescent*
- *Trying*
- *Critical Section*
- *Exiting*

The two important sections for mutual exclusion are *Trying* and *Exiting*. During each of the steps, the thread must communicate with other threads about its current "situation" to ensure mutual exclusion, this communications happens through shared memory.

In case of [[Lamport's Bakery Lock]], the shared memory is the flag list and label list, in case of [[Filter Lock]], the shared memory is the level list and the victim list.

>[!note] Both [[Lamport's Bakery Lock]] and [[Filter Lock]] use $O(n)$ shared memory locations

The Bakery lock is an elegant, fair and succinct solutions, but it is considered to be impractical due to its requirement for $O(n)$ memory overhead which can be really large. Turns out there is no better alternative.

>[!Theorem]
>There is no [[Deadlock-freeness|Deadlock free]] [[Mutual Exclusion]] algorithm for $n$ threads that uses fewer than $n$ shared variables.

In short, the problem is that a thread gives a signal about entering the critical section is communicated using a write in the shared memory locations. With very memory locations, there is a possibility of the location being overwritten.

>[!example] 2 threads and 1 shared memory location
>Given threads $p_1$ and $p_2$,
>- Whenever any of the threads want to enter the critical section, each of them must write to the shared memory, otherwise there will be a run where both threads can enter the critical section, violating mutual exclusion.
>- Given that both algorithms need to write  to the shared memory before entering the critical section, say $p_1$ and $p_2$ are both going to execute a command where they write to the memory
>	- Say $p_1$ starts, it writes to the memory, and if it proceeds until there are no more reads and write before entering  the critical section, it believes that it can enter the critical section safely and will proceed
>	- $p_2$ can then do its write, since the shared memory is now overwritten, $p_2$ does not know that $p_1$ is about the enter the critical section, and will hence proceed to the critical section which can cause a violation of mutual exclusion.

The general proof is discussed [[Proof for Lower Bound on Shared Processes|here]].

---
# References
[[Filter Lock]]
[[Lamport's Bakery Lock]]
[[Mutual Exclusion]]
[[Deadlock-freeness]]