202308171108

Type : #Note
Tags : [[Theory of Computation]], [[Timed Automata]]

---
# Untiming Timed Automata
Given $\mathcal L$ which is a timed language.
We add the following operation
$$
\text{Untime}(\mathcal L)=\{w\in\Sigma^{*}:\exists \text{ a time sequence }\tau,(w, \tau)\in\mathcal L\}
$$
which basically removes the time component from a timed language

**Claim:** $\text{Untime}(\mathcal L)$ is regular.

**Spoiler:** The answer is no, and this also shows deterministic version is strictly weaker. And that timed languages are not closed under complementation. which also shows that timed FSA are strictly stronger than untimed.

---
# References
