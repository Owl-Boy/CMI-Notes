---
tags:
  - MOC
sticker: lucide//map-pin
---
# Software Verification and Analysis
---

>[!idea] What is this course about
>Software appearing as embedded components of systems is now ubiquitous in almost all devices and appliances  
>that are part of our lives today. Some of these devices are highly safety and mission critical, e.g., heart pacemakers, to cars, trains, aircrafts, and space stations. A typical modern car now has more than a million lines of code controlling various critical operations and subsystems including braking and navigation aspects. Bugs in embedded SW can be life-threatening as well as costly for businesses, e.g., blackout in NE USA in 2003, Ariane 5 missile crash in 1996 that cost $500 million, and Toyota's decision to recall more than 180,000 vehicles were all traced to undetected SW bugs. SW industry is keenly looking to complement traditional techniques of dynamic simulation, which can only show presence of bugs, with new techniques that can guarantee absence bugs in SW.
>
>Formal methods is an area of CS that is concerned with the application of symbolic logic for the purpose of SW verification, analysis, and synthesis with the motivation of guaranteeing "zero-bugs" in SW. This branch of CS, which started in the 1960's, has matured enough that several techniques and tools that are product of decades of research in this area are now deployed and are in use today within the SW industry. This course will cover some of the formal methods techniques and tools that have had the widest impact in practice.  Some of the tools the course will use - UCLID-5, FRAMA-C, and CBMC - gives you hand-on exposure to applying these techniques to real SW.  The contents of this course is designed to cover the fundamentals required for engaging in research in Formal Methods.  We also briefly cover some of the current research directions in the area.
>
>TLDR:
>- Provide a rigorous guarantee of quality
>- Provide methods that are automated
>- Can prove absence of bugs.

>[!note] Beginning of software verification
>- 1950s, Turing : manual correctedness proofs
>- 1966/1967 Floyd : assertional reasoning on flowcharts
>- 1969 Hoare : axiomatic program semantics
>- 1976 Dijkstra : weakest precondition for backwards analysis

--- 
## Course Plan
- Logic Recap
- Background (Program Syntax and Semantics)
- Formal modeling and specifying SW
- Hoare Logic
- Bounded Model Checking
- Static Analysis
- Inductive Model Checking
- Concurrent program chekcing
	- temporal logic model checking techniques
- Advanced topics
	- Abstarction techniques
	- Partial order reduction techniques
	- program synthesis


---
## Notes

- [[Big Software Fails]]
- [[WHILE programs]]
- [[IC3 Algrorithm]]

### Model Checking

### Static Analysis
- [[Application of Static Analysis]]

--- 
## MOCs
- [[Logic]]
- [[Logic, Automata and Games]]
- [[Type Theory]]
- [[Static Analysis]]
- [[Model Checking]] 

---
# References