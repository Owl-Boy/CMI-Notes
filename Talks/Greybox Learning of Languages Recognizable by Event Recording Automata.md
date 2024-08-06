- Talk is about Active Learning
- There is a Learner and a Teacher
	- Membership queries :  `word -> bool`
	- Equivalence queries : `language -> Yes | No + CounterExample`
- >[!question] Problem
  > Given a timed language known to be recognizable by ERA, find one.
- Why do it for ERA if it is done for deterministic Timed Automata
	- It is easier
	- ERAs are easier to interpret
- To improve the guess, if we find a wrong word, 2 things can happen
	- If the word differs even in letters, then we do nothing different
	- If the word has timed differences, then we use recheck the guards

---

- A good way of explaining a regular language is giving a property and showing that word follow the property, this is also a good way of explaining timed regular languages, and words can just be represented on a timeline instead of the letter pair thingy
- going slow is fine for talks

---
[[Event Recording Automata]]
[[Deterministic Timed Automata]]
