---
tags:
  - Note
aliases:
  - ALock
---
202408282008

Tags : [[Concurrent Programming]]
# Anderson's Lock
---
The idea behind this lock is to construct a circular list with one slot for each thread, a thread that wants to get the lock enters the list and all other threads after the new one take consecutive spaces clockwise. The lock is also passed clockwise around the table.

![[Pasted image 20240828202536.png]]
the *true* represents the start of the queue.

```rust
Let each thread have a slot variable

struct ALock<n : int> {
  tail  : Atom<int>,
  flags : [Atom<bool>],
}

impl ALock<n> {
  fn new(n:int) -> Self {
    slot <- 0
    flags <- [true, false ... false] // n elems
    tail <- 0
    return ALock { slot, tail, flags}
  }
}

impl Lock for ALock<n> {
  fn lock(self, thread) {
    thread.slot <- tail.get_and_inc() mod n
    wait_while flag[thread.slot] = false
  }

  fn unlock(self, thread) {
    flag[thread.slot] <- false
    flag[thread.slot + 1 mod n] <- true
  }
}

```

>[!error] Drawback
>Drawback of using this lock is the need for $O(n)$ space for the queue. This drawback is avoided by using a better implementation of the queue in [[CLH queue Lock]].

---
# References
