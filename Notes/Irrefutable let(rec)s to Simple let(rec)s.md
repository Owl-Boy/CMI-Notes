---
tags:
  - Note
  - Incomplete
---
202311071911

Tags : [[Programming Languages]]
# Irrefutable let(rec)s to Simple let(rec)s
---

The process of converting Irrefutable lets to simple letrecs is almost identical to the process of converting irrefutable lets to simple lets

```haskell
letrec (t p1 ... pr) = B
       < Other Definitions >
in E
===
letrec v = B
       p1 = SEL-t-1 v
       ...
       pr = SEL-t-r v
       < Other Definitions>
in E
```

where `v` is a new variable.

---
# References
