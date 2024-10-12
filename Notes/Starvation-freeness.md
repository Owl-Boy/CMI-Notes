---
tags:
  - Note
---
202408092208

Tags : [[Concurrent Programming]]
# Starvation-freeness
---
The Faulty Dekkar Lock in [[Deadlock-freeness]] turns out to be inadequate as doesn't give both process a fair chance to execute their critical section. The problem here is *Starvation*

>[!definition] Starvation
>Starvation is a possible problematic situation where multiple process run together that access shared resources. It happens where one or more process are perpetually denied resources required for its execuation.

Some of the possible causes of Starvation are
- Faulty implementation of mutual exclusion, i.e errors in the scheduling algorithm
- resource leaks
- denial of service attacks

Here we look at the first issue, with the Faulty Dekkar as our example
>[!failure] Starvation
>The Faulty Dekkar lock is inadequate because there is a chance that it might perpetually deny one of the threads resources. The following steps would lead to such a scenario
>- Turn is initially set to 1, Thread 1 goes first and sets its 'want' flag to true, then thread 0 start and sets its 'want' flag to true.
>- Now Thread 1 enters the outer loop and sets its 'want' flag to false, so turn 0 can skip the outer loop and enter its critical section out of its turn. while 0 is in its critical section, 1 is stuck in the outer while loop.
>- 0 can now finish the critical section and start a request for another lock before 1 gets out of the loop, now 0 has its 'want' flag set to true 1 so one does another iteration of the loop and and sets its 'want' flag to false and the process repeats
>
>One potential run that can cause such an issue is
>$a_{1} a_{0} (ls_{1} b_{1} ls_{0} le_{0} c_{1} d_{0} a_{0} le_{1}) *$

## Dekkar Lock

```rust
struct Faulty_Dekkar {
  wants_to_enter : [bool; 2],
  turn : 0 | 1
}

impl Lock for Faulty_Dekkar {
  fn lock(self) {
    let i <- get_thread_id()
    let j <- 1 - i
    wants_to_enter[i] <- true
    while wants_to_enter[j] {
      if turn != i { // new line
        wants_to_enter[i] <- false 
        wait_while (turn != i)
        wants_to_enter[i] <- true
      }              // new line
    }
  }
  fn unlock(self) {
    let i <- get_thread_id()
    let j <- 1 - i 
    turn <- j
    wants_to_enter(i) <- false
  }
}
```

>[!success]
>This implementation does not have the same problem as when it is thread 1's turn it does not turn its 'want' flag to false, so thread 0 does not get to skip the wait.

## Peterson Lock
Peterson came up with a simpler lock which is a combination of LockOne and LockTwo as discussed in [[Mutual Exclusion]] and [[Deadlock-freeness]].  

```rust
struct Peterson {
  flag: [bool; 2],
  victim: 0 | 1,
  // threads have id 0 or 1 for the example
}

impl Lock for LockTwo {
  fn lock(self) {
    let i <- get_thread_id()
    let j <- 1 - i // other thread
    flag[i] <- true // I'm interested
    victim <- i // you go first
    wait_while (victim = i and flag[j])
    // If there is a fight for resource,
    // and we are chosen as the loser, wait.
  }

  fn unlock(self) { 
    let i <- get_thread_id()
    flag[i] <- false // not interested anymore
  }
}
```

Since Both threads cannot get stuck in the while loop, the Peterson Lock is Deadlock Free!

Also The Peterson lock is starvation free as if Thread 1 is waiting, and thread 0 wants to enter the critical section again after completing it once, it must make itself the victim and give priority to thread 1.

---
# References
