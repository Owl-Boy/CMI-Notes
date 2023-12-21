# Measuring Average Case Complexity via Sum of Squares Degree - Prasad Raghavendra
- Proof
	- For Univariate Polynomials, the polynomial is always non-negative iff it is a sum of squares of polynomials
	- Standard idea
		- $-1=\text{sos}_{0}(x)+\sum_{i}\text{sos}_{i}(x)\cdot p(x)$
	- A system of multivariate polynomial inequalities is infeasible iff it exhibits a proof via sum of squares.
	- Searching for degree $d$ proof of infeasibility take $n^{O(d)}$ time 
	- Unifies Spectral Methods and linear programming
- Measuring average case complexity
	- Random 3-SAT - Success Stories
		- Given a formula, formulate it as a system of polynomials
			- $x^2=x$ ensures $x=0,1$ so each variables becomes binary like this
			- and given a close, if $x$ is not negated we put $(1-x)$ otherwise $x$ and we equate it to $0$. 
				- $x+\overline y + z$ becomes $(1-x)(y)(1-z)=0$ 
		- This can be used to figure out the complexity of this algorithm for not just highly-likely-to-be-successful cases
	- Bayesian CSPs
		- Big class of problems
		- We know how to separate teh easy cases with hard cases
		- SoS comes here is that we that the SoS degree is low in the easy region and goes up in the harder region.
	- Low-degree Hardness Hypothesis
		- for sufficiently nice distributions, low degree algorithms are the optimal algorithms

>[!quote] Prasad Raghavendra
>Sorry I bombarding you with these statements in the talk. But don't read it.

