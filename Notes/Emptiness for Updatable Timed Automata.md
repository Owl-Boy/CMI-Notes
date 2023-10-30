---
tags:
  - Note
  - Incomplete
---
202310301010

Tags : [[Timed Automata]]
# Emptiness for Updatable Timed Automata
---
>[!note] Theorem
>Emptiness problem is [[Turing Machines#^71406d|undecidable]] for [[Updatable Timed Automata]]

We prove the following theorem by reducing the **Emptiness problem for updatable timed automata** to the emptiness problem of 2-[[Counter Automata]].

We use clocks to simulate counters of the counter automata. The only problem with using clocks for counters is that the value of clocks change with time. To counter this, we have an extra clock that is used to fix the time.

---
## Emulating a 2-counter machine using an Updatable Timed Automata

Let $\mathcal C$ be a 2-counter automata $\langle Q, \Sigma, q_{0}, \{c_{1}, c_{2}\}, \Delta \rangle$
We construct a Timed Automata $\mathcal T$ defined as $\langle Q, \Sigma, q_{0},\{x_{1},x_{2},x_{\text{fix}}\}, \Delta'\rangle$

We deal with operations on the counter automata by defining transitions in our timed automata.

1. Increment
	- The for the transition on the counter automata 
	  $$
	  q\xrightarrow[c_{1}++]{\quad a\quad}q'
	  $$
	- We have the following transition on the UTA
	  $$
	  q \xrightarrow[x_{1} := x_{1}+1]{\quad a,x_{\text{fix}}=0\quad}q'
	  $$
2. Increment
	- The for the transition on the counter automata 
	  $$
	  q\xrightarrow[c_{1}--]{\quad a\quad}q'
	  $$
	- We have the following transition on the UTA
	  $$
	  q \xrightarrow[x_{1} := x_{1}-1]{\quad a,x_{\text{fix}}=0\quad}q'
	  $$
3. Increment
	- The for the transition on the counter automata 
	  $$
	  q\xrightarrow[c_{1}=0]{\quad a\quad}q'
	  $$
	- We have the following transition on the UTA
	  $$
	  q \xrightarrow[x_{1} =0]{\quad a,x_{\text{fix}}=0\quad}q'
	  $$

Because of $x_\text{fix}$, time does not elapse, hence the other clocks behave perfectly like a counter.

---
# References
