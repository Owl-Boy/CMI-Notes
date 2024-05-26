---
tags:
  - Note
---
202402251702

Tags : [[Automata Theory]]
# Another way to Complement a Büchi Autromata
---
The direct complementation of Büchi Automata is a very complicated procedure, hence going over a sequence of other variants of $\omega$-[[omega-Automata|Automata]] give a simpler procedure. This will be the process.

>[!tldr] Conversion Path
>$$
>\text{NBA} \to \text{DRA} \to \text{DSA} \to \text{DMA} \to \text{NBA}
>$$

1. Conversion from Non-Deterministic Büchi Automata to Deterministic Rabin Automata 
	- This conversion was discussed in depth in [[Deterministic Rabin Automata accept omega-regular languages]].
2.  Conversion from Deterministic Rabin Automata to Deterministic Streett Automata
	- This conversion is trivial, we just replace all good and bad states, and the conversion is complete.
	- This process is also the complementation.
3. Conversion from Deterministic Streett Automata to Deterministic Muller Automata
	- For every $S \in 2^Q$, if $S \cap R_{i} = \emptyset$ or $S \cap G_{i} \ne \emptyset$ then we let $S \in \mathcal F$ 
2. Conversion from Deterministic Muller Automata to Non-Deterministic Büchi Automata
	-  Given a Deterministic Muller automata where there is just one good set, we can construct an automata in the following way
		- For each state in the set, we make a copy of the automata, that is restricted to the set, for each copy we make one states in the good set as the good states.
		- Then we give an arbitrary ordering to the good state, and we order the copies using the same. 
		- Everytime we visit a good set in a copy we moved to the next copy and we go back to the first one after visiting the last copy.
	- Given the above construction, we can take the union for each of the sets.
	- [[Last Appearance Record]]

This conversion is much simpler to follow than the conversion given by Büchi.

---
# References
[[Büchi Automata]]
[[Deterministic Rabin Automata accept omega-regular languages]]