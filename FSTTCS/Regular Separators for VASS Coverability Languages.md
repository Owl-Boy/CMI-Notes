# Regular Separators for VASS Coverability Languages'
- VASS
	- NFA with finitely many counters
	- Equivalent to Petri Nets
	- Models concurrent behavior
- Regular Separability
	- Safety verification consists of deciding disjointness of two langauges like event sequences
	- A regular separator verifies disjointness
	- transitions are , read a letter, change state, update counters
	- Transitions fail if counter goes below 0
- Reachability language 
	- Start state $(s,0)$
	- Final state $(t,0)$
- Converability language
	- Start state $(s,0)$
	- Final state $(t,v)$ for some $v\ge 0$
- Regular Seperability
	- regular languages are open sets now they are like T-2 separability.

## New Lowerbounds for Reachability in VASS
- Counter Programs vs VASS, directly interconvertible
- The problem is EXPSpace-Hard 
- Ackerman-upperbound
- Tower Hardness
- Ackerman Hard