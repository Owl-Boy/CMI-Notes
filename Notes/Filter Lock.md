---
tags:
  - Note
aliases:
  - Filter Lock
---
202408131908

Tags : [[Concurrent Programming]]

# The Filter Lock
The *Filter Lock* generalises other locks to work for $n > 2$ threads. It does that by creating "waiting rooms" called *levels* that a threads must traverse before acquiring the lock.

The [[Starvation-freeness#Peterson Lock|Peterson Lock]] uses a two-element boolean flag to indicate whether a thread is trying to enter the critical section. The *Filter Lock* generalises by using an $n$-element integer `level : [Int]` array, where the value of `level[A]` indicates the highest level that thread $A$ is trying to enter. Each level also has a distinct `victim[l]` to "filter out" one thread.

```rust
struct Filter<n : Int> {
  level  : [Int; n],
  victim : [Int; n]
}

impl Lock for Filter {
  fn lock(self, n: Int) {
	let me <- get_thread_id()
	for i in 1..n {
	  level[me] <- i
	  victim[i] <- me
	  // When you reach the level, and there is someone higher
	  // wait for someone else to come and take your place.
	  wait_while(
		  exists k != me, 
		  level[k] >= i && victim[i] = me
	  )
	}
  }  

  fn unlock(self) {
    let me <- get_thread_id()
    level[me] <- 0
  }
}
```

## Properties
>[!theorem] Mutual Exclusion
>Entering the critical section is equivalent to entering level $n^{\text{th}}$ and then crossing it, hence there can only be 1 thread in the critical section.

>[!theorem] Starvation-freeness
>Once a thread becomes the victim in the $i^{\text{th}}$ level, It will move to the next level and become the victim at most after all threads ahead for every level. By induction the algorithm is starvation free.

## Fairness of the Filter Lock

The starvation-freedom property guarantees that every thread that calls `lock()` eventually gets it, but makes no guarantee about how long this may take, not does it guarantee if the lock will be "fair".

For example, consider the *Filter Lock*. Ideally, the lock should guarantee a "first-come-first-serve" idea, so if $A$ calls lock first, before thread $B$, it should be allowed to go to the critical section before $B$. But before $A$ can claim that it wants to keep the lock, $B$ can finish execution.

The idea is that a lock can be broken into 2 parts: 
- A Doorway Section (from the start of the lock to the wait loop, which is always completed in finite number of steps)
- Wait Section 

If one wants a "first come first served" scenario then after a thread completes its wait section, it cannot enter the loop and overtake another thread that is waiting in the doorway section. This is further discussed in [[Lamport's Bakery Lock]]

---
# References
