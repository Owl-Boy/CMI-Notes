---
tags:
  - Note
---
202408281908

Tags : [[Concurrent Programming]]
# TTAS Lock
---
A thread wanting to acquire the [[TAS Lock]] would intuitively keep reading the state until it turns `false` and will then attempt to acquire it, but the implementation does a `read_and_write` instead of a read. **TTAS Lock** fixes precisely that.

```rust
struct TTAS{ 
	state : Atom<bool> 
} 

impl Lock for TTAS { 
  fn lock(self) {    
    loop {
	  wait_while(state.get() = true)
	  if !state.get_and_set(true) { return } 
	  // only attempt once each time 
	  // another thread finishes
	}
  } 
	
  fn unlock(self) { state.set(false) } 
}
```

This algorithm greatly improves the performance over the simple [[TAS Lock]], but each time a process unlocks its thread, it can lead up to $n$ cache-invalidations. The average performance is further improved in [[Backoff Lock]]

---
# References
