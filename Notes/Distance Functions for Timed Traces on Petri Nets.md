---
tags:
  - Note
---
202405141605

Tags : [[Conformance Checking]]
# Distance Functions for Timed Traces on Petri Nets
---
Our notion of distance is similar to Levenstein Edit distance, i.e, based on given edit operations, the distance between two traces would be the minimum cost of the edits required to go from one trance to another. 

>[!Attention]
For the project, we assume that we only care about the pure time alignment, i.e, we assume that the processes themselves perfectly match in the log and in the model, but events in the process might occur at different time stamps, hence we find distances between vectors of same size that have entires from $\mathbb{R}^+$, equivalent, it can be thought of as a function from the causal net of the given petri net.

### Stamp Edit
These distances correspond to measurement errors of the system where it might have recorded an event happening at a wrong time stamp, we edit a particular entry of the vector by some given value. Defined as follows

![[Pasted image 20240514153336.png]]

where $\gamma$ is timing function on the Causal Net of the petri net.
The cost of such an edit can just be taken as $x$. We also define $\text{Stamp}$ as the set of stamp edits

### Delay Edits
These distances correspond to a difference in time interval of a particular event happening in the model and log. This difference propogates to all subsequent events and can be defined as
![[Pasted image 20240514155651.png]]
The cost of an edit here can also be taken as $x$ eventhough the change propogates to all subsequent values.

## Distances Functions
With the above types of edit moves, we get 3 natural edit distances 
- ***Stamp Only Distance***: Given any two timing function $\tau_{1}, \tau_{2}$ over the same causal process, their stamp distance is $d_{t}(\tau_{1},\tau_{2}) := \min \{ \text{cost}(m)\ |\ m \in \text{Stamp}^*, m(\tau_{1})=\tau_{2} \}$
- ***Delay Only Distance***: Given any two timing function $\tau_{1}, \tau_{2}$ over the same causal process, their delay distance is $d_{t}(\tau_{1},\tau_{2}) := \min \{ \text{cost}(m)\ |\ m \in \text{Delay}^*, m(\tau_{1})=\tau_{2} \}$ 
- ***Mixed Moves Distance***: Given any two timing function $\tau_{1}, \tau_{2}$ over the same causal process, their mixed move distance is $d_{t}(\tau_{1},\tau_{2}) := \min \{ \text{cost}(m)\ |\ m \in (\text{Stamp} \cup \text{ Delay})^*, m(\tau_{1})=\tau_{2} \}$

---
# References
[[Formalising Precision and Fitness for Time Petri Nets]]