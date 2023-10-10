---
tags:
  - Note
---
202309231509

Tags : [[Timed Automata]]

---
# Event Predicting Automata
In an *Event Predicting Automata* given an *Alphabet* $\Sigma$, we have A set *Event Predicting Clocks*

## Event Predicting Clocks
Let $Y_{\Sigma}$ be the set of *Event Predicting Clocks*. The value of Every $Y_{a}$ gives the time stamp after which the _timed automata_ accepts the letter $a$.

```ad-example
Let $L=\{aa^*b\}$ where the time gap between the first $a$ and $b$ is $10$. 

![[Drawing 2023-09-23 15.24.58.excalidraw]]

There is no [[Event Recording Automata]] which can have the above language(It cannot talk about the first occurence of a letter)
```

## Semantics of Event Predicting Automata

Given a _Timed Word_, The value of $Y_i$ at each step would look something like  
![[Pasted image 20230923154314.png|500]]
Semantics on a timed word is given by $\gamma_{i}$ 
Given a word $\omega = (a_{1},a_{2}\dots a_{k},\tau_{1},\tau_{2}\dots \tau_{k})$
$$
\gamma_{i}(y_{a})=
\begin{cases} 
t_{j}=t_{i} & \text{if }\exists j>i,a_{j}\text{ is the first $a$ after $a_{i}$} \\
\perp & \text{otherwise}
\end{cases}
$$

Just like [[Event Recording Automata]], The languages here are closed under
- Intersection
- Union
- Complementation

And *Event Predicting Automata* are determinizable using the subset construction

---
# References
[[Event Recording Automata]]
[[Event Clock Automata]]