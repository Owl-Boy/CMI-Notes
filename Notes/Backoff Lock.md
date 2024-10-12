---
tags:
  - Note
aliases:
  - Exponential Backoff
---
202408281908

Tags : [[Concurrent Programming]]
# Backoff Lock
---
The [[TTAS Lock]] can cause $n$ cache invalidations every time a thread exits its critical section, this becomes an issue when there are very frequent attempts to get the lock by a lot of threads, it would be ideal for threads to reduce the frequency attempts if the number of threads goes up which is captured by the following idea

## Exponential Backoff
Between every failed test and set and the next, we randomly choose a number from `[0 .. limit]` and sleep for that long before proceeding and double the limit each time. More failed attempts, which usually correspond to a lot of threads trying to fight for the lock would drop the frequency of attempts and the randomness will let threads attempt at different times.

```rust
struct Backoff {
  state : Atom<bool>
  limit : int
  range : (start:int, 
           end:int)
}

impl Backoff {
  fn new(start, end) -> Self {
    Self{
      state : false,
      limit : start
	  range : (start, end)
    }
  }

  fn backoff() {
    let delay <- random [1..limit]
    limit <- min(end, 2 * limit)
    sleep(delay)
  }
}

impl Lock for Backoff {
  fn lock(self) {    
    loop {
	  wait_while(state.get() = true)
	  if !state.get_and_set(true) { return }
	  else { backoff() } 
	  // only attempt once each time 
	  // another thread finishes
	}
  } 
	
  fn unlock(self) { state.set(false) }
}

```


>[!error] Drawback
>The performance of this lock is very architecture dependent and needs fine tuning, so is not very portable.

---
# References
