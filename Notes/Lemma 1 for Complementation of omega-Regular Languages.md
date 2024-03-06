---
tags:
  - Example
---

202402281256

tags : 
202401122336 
tags : [[Automata Theory]] 
# $\sim_A$ has finitely many equivalence classes, all of which are regular languages.

---
For part one of the definition, consider a *NFA* that has the same states and transitions as $A$, and let $p$ be a string state and $q$ be an ending state and consider the language of this automata. Make $n^2$ many such languages and take the intersection of them, all of them are regular, so their finite intersection is regular. 
And We can use a Myhill-Nerode argument to show that its regular. 
For part two of the definition, we do something similar, but to enforce the condition that the path has covered a good state my making a coping of the automata, and moving to the copy of it. We only let the copy contain the final state. And do a similar process as above. This gives us that there are finitely many classes and all of them are regular.

---
# Related
[[Lemma 2 for Complementation of omega-Regular Languages]]
[[Lemma 3 for Complementation of omega-Regular Languages]]