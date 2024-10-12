---
tags:
  - Note
---
202408281908

Tags : [[Concurrent Programming]]
# TAS Lock
---
TAS lock is an implementation of a lock that uses the *read-modify-write* instructions to work with hardware architecture that could otherwise reorder lock implementations and break them. 

```rust
struct TAS{
	state : Atom<bool>
}

impl Lock for TAS {
  fn lock(self) {
    wait_while(state.get_and_set(true))
    // This lock will stop waiting only when 
    // another process sets the lock to false
  }
  fn unlock(self) {
    state.set(false)
  }
}
```

The correctness of the lock comes from the fact that the state if false iff there is no thread in the critical section, each time a threads wants to get into one, it sets the state to false until it exists CS at which point another thread can enter the critical section.

>[!error] Expensive
>The problem with TAS lock is that it repeatedly uses the `get_and_set()` functions which is extremely expensive. This problem is improved with [[TTAS Lock]]

---
# References
