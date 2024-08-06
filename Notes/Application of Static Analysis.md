---
tags:
  - Note
---
202408051608

Tags : [[Static Analysis]]
# Application of Static Analysis
---
- About doing analysis before running the co de
- Roots in Compiler Construction
	- been there since 1970s
	- Analyse why transforming code in different representations
- Infer semantic information about programs
- Prove absence of runtime error
	- array index out of bounds - value range of variable check
	- null pointer dereference - points-to analysis?

Static Analysis is about analysing the code before its execution.

It has roots in compiler construction as compilers have been a common tool (lmao can't really avoid it) for finding bugs before running a program.
- Been there since 1970s
- Extract information while converting between intermediate representations, which relates to semantic information.

Compilers, and Static analysis in general, can be used to prove that entire classes of bugs do not exist like:
- array index out of bounds - value range of variable check
- null pointer dereference - points-to analysis?

This analysis can also be used to compute the worst time computation of programs, which is usefule in
- Real time systems : AirTraffic control
- Compute Cache contents to predict cache misses

This happens by making approximation of the program to more easily predict its runtime under the constraint that if the property that we care about holds true for the approximation, then it will also hold for the real program. This is not necessarily true in the reverse order. So if Static analysis say that something words, it must do, but it can lead to false positives.

Hence, static analysis tends to give warnings and not errors.

---
# References
