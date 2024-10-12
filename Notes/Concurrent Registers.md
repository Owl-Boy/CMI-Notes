---
tags:
  - Note
  - Incomplete
---
202409180009

Tags : [[Concurrent Programming]]
# Concurrent Registers
---
Concurrent programming models begin with threads, which is a sequential process that runs in parallel with other threads. These process communicate with each other by using *shared memory*.

These shared memory location are called *registers*. 
We would want to start building the more concurrency friendly registers from the weaker ones and we have a couple of metrics, the first one is the count of threads that can read and write the register and the are
- **SRSW**: Single reader single writer
- **MRSW**: Multiple readers single writer
- **MRMW**: Multiple readers multiple writers

Another metric that used to talk about concurrent register is the type of value it can store, because boolean values are much easier to deal with than any other multi valued type.

The last and final useful metric is how "safe" or "well behaved" the register is and there are 3 level of that
- Safe:
	- A `read` call that does not overlap with a write call returns the value written by the last `write`
	- A `read` call that does overlap with a write call returns any value within the valid values of the register.
- Regular:
	- A regular register is safe
	- If a `read` overlaps with one or more `write` calls, then it can return either the last previously written value, or the value of any of the write calls it overlaps with
- Atomic:
- 

---
# References
