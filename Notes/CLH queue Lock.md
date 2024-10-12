---
tags:
  - Note
---
202408282008

Tags : [[Concurrent Programming]]
# CLH queue Lock
---
The idea behind the **CLh Queue Lock** is to provide a queue that is efficiently implemented to give the order in which the threads get their lock.

A doubly linked list is used to implement the queue in order to have it use as much space as there are threads wanting the lock, this makes it significantly more memory efficient and portable than locks like [[Anderson's Lock]].

The implementation of the CLH Lock requires a node for each thread which is the place where the thread will spin.

![[Pasted image 20240828211408.png]]

The QNode struct represents a spot on the queue and is implemented as
```rust
struct QNode{
  locked : bool
}
impl QNode {
  fn new() -> ARef<Self> {
    let ref <- ARef(QNode{ locked: false })
    return ref
  }
}
```

The lock itself keeps track of the end of the queue to know where to add more queue and a for each thread, it and its predecessor's address.

```rust
struct CLHLock {
  tail : ARef<QNode>,
  pred : Local<QNode>
  my_node : Local<QNode>
}
```

To create the lock object, we want to start with a node, which will also be the "tail" or the last node in the queue without a predecessor.

```rust
impl CLHLock {
  fn new() -> Self {
    let tail <- QNode::new()
    let myNode <- ARef<new Local<QNode>>
    let pred <- null
  }
}
```

To get in the queue from the perspective of a thread, it takes its node, and sets its flag to `true`. the current value f the common variable will become the tail and the current node will become the new tail.  To release the lock, we just set our current node to false.

```rust
impl Lock for CLHLock {
  fn lock(self) {
    my_node.locked <- true
    pred <- tail.get_and_set(my_node)
    wait_while(pred.locked)
  } 

  fn unlock(self) -> {
    my_node.locked <- false
  }
}
```

---
# References
[[Pseudocode for CLH queue Lock]]