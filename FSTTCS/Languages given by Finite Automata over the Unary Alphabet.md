# Languages given by finite Automata over the Unary Alphabet
- Chrobak Normal Form
	- You go to a start state, then you have trees and the leaves of trees are the only cycles. 
- Comparing NFAs
	- We convert to Chrobak Normal form, poly time
	- stem is trivial to compare, we match the tree part by unrolling the loops to change the size of the branches
	- We multiply the size of the cycle to get a common size, and use CRT
- Complementation of UFA
	- assume Chorbak Normal Form
	- 