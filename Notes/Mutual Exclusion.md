---
tags:
  - Note
---
202408092108

Tags : [[Concurrent Programming]]
# Mutual Exclusion
---
>[!definition]
>The property of a block of code to only be executable by one thread of a time is called *Mutual Exclusion*

The standard way in which mutual exclusion is implemented is through locks.

```rust
trait Lock {
  lock() // before entering critical section
  unlock() // before leaving critical section
}

struct Counter {
  value : u32
  lock : Lock

  fn get_and_increment(&self) -> u32 {
	lock.lock() // enter critical sectoin
	
	let temp <- value  // in critical section
	value <- temp + 1   // in critical section

	lock.unlock() // leave critical section
	return temp
  }
}
```

## Implementation of Lock
This will be the first of three implementation of locks that will be discussed, The final and correct one can be found [[Starvation-freeness|here]].

```rust
struct LockOne {
  flag : [bool; 2];
  // threads have id 0 or 1 for the example
}

impl Lock for LockOne {
  fn lock(self) {
    let i <- get_thread_id()
    let j <- 1 - i // other thread
    flag[i] <- true
    wait_while (flag[j] = true)
    // wait till other flag becomes false
  }

  fn unlock(self) {
    let i <- get_thread_id()
    flag[i] <- false
  }
}
```

This implementation of lock makes sure that both the threads will not be active on the critical section of the code at the same time, the idea is as follows:
- Both threads want to access a critical section
- The thread that starts running first will lock the section for itself, and its flag will be set to true.
- The other thread sees that the flag is set to true and is unable to proceed until the first thread finishes executing and sets its flag to false.

This idea ensures mutual exclusion, but another problem pops up: *Deadlock*, which will be explained in detail [[Deadlock-freeness]] but the idea is as follows
- The first thread wants to execute the critical section, so it locks it, setting its flag as true.
- The Second thread does the same before the first thread executes the next line, now both flags are true.
- Both threads get stuck in the while loop in the lock as the other flag is true.

---
# References
