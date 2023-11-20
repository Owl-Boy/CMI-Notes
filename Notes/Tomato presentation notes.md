---
tags:
  - Note
  - Incomplete
---
202311201411

Tags :
# Tomato presentation notes
---
- History
	- want to model systems, so TA
	- want to model systems interacting with external, uncontrollable components: some transitions of the automaton cannot be forced or prevented to happen. The reachability problem then asks whether there is a strategy to reach a given state, whatever the uncontrollable components do. This problem can also be decided, in exponential time.
- Plan
- What is a weighted tomato?
	- (tomato, cost) on Locations $\cup$ Edges, definition in both
	- Imp: cost does not affect behaviour, only affects... cost
- Weighted timed games
	- weighted tomato, and Edges -> Controllable by Controller, and Uncontrollable by God
	- Define strategy: partial function, for finite run, associate (d,e) = delay time d, take edge e
	- Memoryless if no memory
	- run compatible with strategy = we stick to strategy at every move, except when God plays before we can -> gives a set of plays
	- winning strategy if all plays reach final
	- Classical reachability, in timed setting EXPTIME complete; memoryless, region-uniform strategies are good enough
	- cost of winning strategy = sup cost of all plays, finite cost; non winning can be infinite
	- opt_cost = inf cost over all winning strats
- Problems:
	- decision
		- bounded cost
		- optimal cost
	- come up with almost-optimal strat
	- example?

---
# References
