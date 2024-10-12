---
tags:
  - Note
  - Incomplete
---
202409270009

Tags : [[Concurrent Programming]]
# Consensus Number for Compare and Set - Omega
---
>[!success] Claim
>A wait-free consensus algorithm exists based on `compare_and_set()` for any number of threads.

***PseudoCode***:
```
thread(i, vi):
  if compare_and_swap(-1, vi, decision)
    return vi
  else 
    return(get decision)
```

We can get rid of `get` by looping over all values. and trying compare and swap without changing values.

---
# References
