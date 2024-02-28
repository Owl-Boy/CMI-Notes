---
tags:
  - Note
  - Incomplete
---
202402251702

Tags : [[Automata Theory]]
# Another way to Complement a Büchi Autromata
---
The direct complementation of Büchi Automata is a very complicated procedure, hence going over a sequence of other variants of $\omega$-[[omega-Automata|Automata]] give a simpler procedure. This will be the process.

>[!tldr] Conversion Path
>$$
>\text{NBA} \to \text{DRA} \to \text{DSA} \to \text{DPA} \to \text{DMA} \to \text{NBA}
>$$

1. Conversion from Non-Deterministic Büchi Automata to Deterministic Rabin Automata 
	- This conversion was discussed in depth in [[Deterministic Rabin Automata accept omega-regular languages]].
2.  Conversion from Deterministic Rabin Automata to Deterministic Streett Automata
	- This conversion is trivial, we just replace all good and bad states, and the conversion is complete.
	- This process is also the complementation.
3. Conversion from Deterministic Streett Automata to Deterministic Parity Automata
	- We make $G_1$ to be $0$, Then we make $R_1\setminus G_1$ to be 1, we keep making pairs of sets like that, and whenever we make an odd numbered set, we remove it from all its previous sets.
	- Now that we have numbered the sets, if the set that was visited the least number of times was even say $2n$, then we visit $G_n$ infinitely many times but $R_n$ finitely many times.
	- This is a Generalized parity automata, where we numbered sets, but its trivial to convert it to a normal one. We can then convert it to a standard Parity Automata
1. Conversion from Deterministic Parity Automata to Deterministic Muller Automata 
	- We simply let the set of final states be the set of inf states for all accepting runs for the parity automata.
1. Conversion from Deterministic Muller Automata to Non-Deterministic Büchi Automata
	-  Given a Deterministic Muller automata where there is just one good state, we can construct an automata in the following way
		- we make 2 copies of the automata, and delete all the states that are not in the good set from one of them.
		- Then we make epsilon transitions from the first copy to the second one, and only make the good states in the second one.
	- Given the above construction, we can take the union for each of the sets.
	- [[Last Action Record Conversion]]

This conversion is much simpler to follow than the conversion given by Büchi.

---
# References
[[Büchi Automata]]
[[Deterministic Rabin Automata accept omega-regular languages]]