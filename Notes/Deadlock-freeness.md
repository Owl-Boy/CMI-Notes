---
tags:
  - Note
---
202408092108

Tags : [[Concurrent Programming]]
# Deadlock-freeness
---
As shown in the lock implementation in [[Mutual Exclusion]], the program gets stuck and satisfies the property of not running the critical section by not running the program at all. This is undesirable and the situation is called a *Dead lock*

>[!definition] Dead Lock
>A dead lock is a situation where no member of a group (or any thread in the thread pool) takes any action because they are waiting for someone else to take action.

Dead locks arise when the following conditions are met:
- Mutual Exclusion :  There is some shared resource on which atomic operations need to be performed. (counter)
- hold and wait response : A process is holding at least 1 resource and is requesting more resources (flag, counter)
- No preemtion: A resource can only be released voluntarily by the process holding it (unlock)
- Circular wait : Each process waiting for a resource must be held by another process, hence no process makes any action

## Deadlock-free implementation of Lock

The idea is to have a shared variable "victim", the shared variable victim. In a deadlock situation, the problem is that two(or more) resources are asking for a shared resources, the solution is to resolve the conflict by letting one of them win. This arbitrary victory is decided using the victim variable.

### Passive Startegy

```rust
struct LockTwo {
  victim: u32
  // threads have id 0 or 1 for the example
}

impl Lock for LockTwo {
  fn lock(self) {
    let i <- get_thread_id()
    victim <- i;
    wait_while (victim = i)
    // If there is a fight for resources, 
    // pick a winner and stop the conflict
  }

  fn unlock(self) { }
}
```

>[!failure] Single Thread
>LockTwo is inadequate because it halts if the program is running on a single thread. 

>[!success]
>But it avoids deadlocks and complements LockOne well and hence we can combine them to get the peterson lock, which will be seen in [[Starvation-freeness]].



### Aggressive Strategy

Another lock worth looking at is a faulty version of Dekkar's lock.

```rust
struct Faulty_Dekkar {
  wants_to_enter : [bool; 2],
  turn : 0 | 1
}

impl Lock for Faulty_Dekkar {
  fn lock(self) {
    let i <- get_thread_id()
    let j <- 1 - i
a:  wants_to_enter[i] <- true // interested
ls: while wants_to_enter[j] {
b:    wants_to_enter[i] <- false 
      wait_while (turn != 0)
      // don't show interested if not your turn
c:    wants_to_enter[i] <- true
le: }
  }
  fn unlock(self) {
    let i <- get_thread_id()
    let j <- 1 - i // other thread
    turn <- j
d:  wants_to_enter(i) <- false // not interested
  }
}
```

>[!success]
>This version of the lock is deadlock free, but uses an aggressive strategy as compared to the previous one. Here if two threads want to access a critical section, and both get into a conflict, we resolve the conflict by the shared variable "turn". Hence the lock is Deadlock Free!

>[!failure] Starvation
>The Faulty Dekkar Lock is inadequate because there is a change it might deny one of the threads resources, this is discussed more in [[Starvation-freeness]]

---
# References
