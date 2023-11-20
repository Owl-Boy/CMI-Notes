- Define a 2-counter Automaton, and prove reachability in Counter Automata is undecidable.
- Given a 2 counter Automaton and 2 natural numbers, check if there is a run that takes $\langle q_{0},0,0\rangle$ to $\langle q,n_{1},n_{2}\rangle$.
- For a given machine, we create a first order formula $\phi$ such that, the machine will only reach the configuration if the first order formula would be valid
	- $L=(R,F,C)$
		- $C=Q \cup \{0\}$
		- $F=\{S\}$ such that $\#S=1$
		- $R=\{\text{conf}\}$ such that $\#\text{conf}=3$
	- $\varphi_{\text{init}}= \text{conf}(q_{0},0,0)$
	- $\varphi_{t}=\forall x\forall y\forall z\ \text{conf}(q_{1},x,y)\land (S(z)\equiv y) \to \text{conf}(q_{2},S(x),z)$ 
	- Make bigger formula which is just a huge `and` block
	- Proof is induction on the number of steps required to reach the thingy
	- Then you write a formula which says that if you can reach a given configuration then you can reach the next configuration, and thne you make a formula that says you can get to the desired state if the transitions allow it.
	- lemma
		- If the formula is valid, then there are 2 numbers that will imply that a state is reachable
		- proof is consider the model where universe is $Q \cup \mathbb N$. The Interpretation is true in this model.
	- Since First Order Logic can model a counter automaton, things will be undecidable.
- How to we get back decidability!
	- We can try restricting stuff. More restriction makes the above prove more tedious, because even with just a binary relation, validity is still dedidable
	- We can try restricting the universe, apparently there is a huge amount of stuff, sir might study a few papers and give in class,
		- Example FO formulas with just 2 variable, turns out that this is decidable???? what the fuck
- Multi Sorted First Order Logic, where you can have a collection of universes.




>[!warning] LOOK
> say you Universes are A and B in MSFOL
>you say you have $A \sqcup B$, and whenever you write $\exists x.A\ \phi(x)$, just write $\exists x.\phi(x)\land \phi_{A}(x)$
>where we define $\phi_{A}(x)$ to be $A\subseteq A \sqcup B$