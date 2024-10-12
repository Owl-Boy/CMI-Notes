---
tags:
  - Example
---

202408282111

tags : [[Concurrent Programming]]

#  Pseudocode for CLH queue Lock
---
The following is a pseudocode implementation of the [[CLH queue Lock]].

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

struct CLHLock {
  tail : ARef<QNode>,
  pred : Local<QNode>
  my_node : Local<QNode>
}
impl CLHLock {
  fn new() -> Self {
    let tail <- QNode::new()
    let myNode <- ARef<new Local<QNode>>
    let pred <- null
  }
}

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
# Related
