---
tags:
  - Note
  - Incomplete
---
202401051501

Tags : [[Automata Theory]]
# Reachability in Finite Pushdown VASS
---
>[!tip] Why vass
>This model is very popular because you can model regular thread using this, and it nicely models events like task creation and ending, which is called *asynchronus calls*. Push down automata enforce and ordering or a stack like behaviour, so that counts as *sychronus calls*

>[!note] Pushdown Vass
>we have counters with a stack, and transitions are like a mix of PDA and VASS transitions

Reachability defined usually: Init counter and stack  config and final counter and stack.

reachability in 
PVASS reduces to coverability with one counter
It inhertis Ackerman lowerbound from VASS
decidability of reachability is open, even for one counter.

Coverability is PSPACE hard for one counter and is decidable. 

# Continuous Pushdown PVASS
Here a transition can be fired fractionally, so counter increments are fractional, the state changes are obviously discrete

0 is not a valid fraction. the domain is $(0,1]$ 

Continuous approximation is P-Complete
Reachablity for continuous VASS is NP-Complete

# VASS with heirarchical Zero test
So we can test the sum of first $n$ counters for $0$, this is known to be decidable and this is a special case of PVASS

Reachability in bidirected PVASS (you are allowed a reverse arrow for arrow)



---
# References
