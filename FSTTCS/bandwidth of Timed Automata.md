# Bandwidth of Timed Automata - 3 Classes

- *Bandwidth* - Information per unit time
	- For discrete languages we can just count the number of words, not possible for timed words because time is real
	- We define up to some precision
		- We say two words are less than epsilon away, if they  have the same set of letters(ordering can change)
		- We can move the letters in the first words in time by at most $\epsilon$ each to get the second words
- $\epsilon$-*net*: A set of points such that any point in the *Metric Space* is at most $\epsilon$ away from the space
- *Orbit Graphs* - defined for each path
	- We link vertices whenever it is possible to go from $v_1$ to $v_2$ (start and end)
	- We represent a vertex by 2 connected(special connection) nodes of a graph(representing start and end times) and we make connection between both ends of the vertex(both nodes)
	- These can be represented as adjacency matrices and multiplication of matrices represents composition of paths
	- Having *Orbit Graphs* for just edges lets us generate it for all paths
	- The matrix interpretation also gives a handy computation tool to deal with every configuration of clocks(even with fractional values, obviously)
	- Good for reachability

