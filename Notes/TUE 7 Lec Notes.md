- # Automata Learning
	- Valid Questions
		- Give a word and get a yes/no : *Membership*
		- Give a guess for the language and a get yes / counterexample: *Equivalence*
	- Idea: use strings to identity the states.
	- If we have a language with a minimal DFA with $n$ states, then we will need atleast $n$ equivalence queries. 
	- Story: *Student* ask a *Teacher*.
	- **Main Ideas:**
		- States Identified using Strings
		- Start Building Automata based on the tiny information we have at all points along the way and keep building a table with membership queries of the words and their 1 letter extensions.
		- DANA Anguling Paper
	- **Applications:**
		- testing of telecommunication systems at Seimens
		- Integration testing at France Telecom
		- Automatic testing of an online conference service at Springer-Verlag
		- Testing requirements of a brake-by-wire system from Volvo
		- Models of a smart card reader for internet banking
		- Learning Models of Legacy Software
		- Models of network protocols

>[!quote] Srivathsan
>See It is possible to do it, because I will tell you how to do it.

- # IFPL - Graph Reduction
	- Represent Application, lambda abstraction, constants and inbuilt functions as graphs.
	- For situations were arguments need to be copied 
>[!quote] Suresh
>Arunava: Sir, do we give presentation in Pairs
>Suresh: I don't know, in general we will first do baby steps by attending classes
