---
tags:
  - Note
  - Incomplete
---
202310251410

Tags : [[Advanced Algorithms]]
# Dinic's algo for max-flow
---
**Blocking flow:** $f$ is a blocking flow if it saturates at least one edge on every $s-t$ path.
*Observe:* A blocking flow need not be a max flow.

1. Find a BFS layout of the network.
2. Perform a DFS using only the BFS edges.
3. Every time $t$ is reached, send a flow along the $s-t$ path (present on the stack).

This results in a blocking flow. Compute residual graph $G_{f}$.

*Observe:* When a blocking flow is found, the network has no $s-t$ path of length $d$.

Analysis: $O(n)$ iterations since each iteration increases the length of an $s-t$ path. So $O((m+n)n)$ time.


---
# References
[[Edmonds-Karp algo for max flow]]