---
tags:
  - Note
  - Incomplete
---
202408171608

Tags : [[Concurrent Programming]]
# Lamport's Bakery Lock
---
Lamport's Bakery lock algorithm is one of the most elegant solutions to the mutual exclusion problem for $n$ threads.

It guarantees ==first-come-first-served== property by using a distributed version of the number-dispersing machines that are often found in bakeries: Each thread takes a number in the doorway, and then waiters until no thread with an earlier number is trying to enter the critical section.

```rust
struct Bakery<threads : Int> {
  flag : [bool; threads],
  label : [Int; threads]  
}

impl Lock for Bakery {
  fn lock(self) {
    let i <- get_thread_id()
    flag[i] <- true
	label[i] <- max of all labels + 1
    wait_while(
      exists k != i, flag[k] &&
                    (label[k],k) < (label [i],i)
    )
  }

  fn unlock(self) {
    let i <- get_thread_id()
    flag[i] <- false
  }
}
```

---
## Properties

>[!theorem] Bakery lock is Deadlock-free
>The set of possible `(label[id], id)` is well-ordered, hence, if there is a non empty set of threads wanting to get the lock, there is a minimum thread that does not wait others

>[!theorem] Bakery Lock is first-come-first-served
>If thread $A$'s doorway precedes thread $B$'s doorway since $A$'s label is smaller
>$$
\text{write}_{A}(\text{label[A]}) \to \text{read}_{B}(\text{label[A]}) \to \text{write}_{B}(\text{label[B]}) \to 
\text{read}_{B}(\text{flag[A]})$$
>
>This also makes sure that the Bakery lock is **starvation free**.

>[!theorem] Bakery Lock satisfies mutual exclusion
>If two thread want to get to their critical section, both have to set their flags to true and get a label. If one of the threads gets its label before the other one, it gets to execute its critical section first, If both concurrently get their label, the pair `(label, id)` will give an order to both the threads and hence one of then will execute first and the other one would have to wait for it to set its flag to false. 

---

# References
[[Filter Lock]]