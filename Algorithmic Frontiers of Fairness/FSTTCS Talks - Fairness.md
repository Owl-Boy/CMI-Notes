
## Talk 8: Aniket Murhekar

### Prelims

- EFX up to one _chore_: I value my bundle less than Bob's bundle after removing some _chore_ from my bundle; EF1 allocations always exist.
- Efficiency: people are better at different things and take less time at different things
- Allocation $x$ is PO if there is no allocation $y$ such that $y$ is better for everyone than $x$.
- This talk: fairness + efficiency, both at once. Want to be fair, but want to also want to be efficient. In particular, we look at EF1 + PO allocations.

- EF1 is easy, PO is hard. Round robin, envy-cycle algos give EF1 allocations in poly$(n, m)$ time.
	- Round robin is just each person picks turn by turn, but this doesn't guarantee PO
	- Can try to improve to get PO, but this could break EF1
	- Even _verifying_ PO is hard!
- Turns out that maximizing Nash welfare guarantees EF1 and PO!

- What worked for this problem of EF1 + PO was the competitive equilibrium model.
- Fisher's market model:
	- Agents have budgets
	- Goods have prices
	- Goods are divisible
	- Agents want the maximum value they can get with their budget
- $(x, p)$ is CE if:
	- Market clears:
	- People get the maximum bang for their buck
- For a CE, the allocation is fractionally PO.

- An EF1 + PO allocation of goods can be computed in pseudo-polynomial time. Later, it was shown that an EF1 + fPO allocation can be computed in pseudopoly time.

### Algorithm
- Augmenting path type idea, draw a graph with solid lines being assignments, dotted lines being MBB edges, transfer goods along the augmenting path
- This works.
- The point is that this maintains PO, we never break this condition.

## EF1 + PO for chores

- First: deal with disutilities instead of negative values to make everything positive. EF1 is still what one would expect.
- There's nothing analogous to the Nash welfare function for chores.
- Overall want $min_{x} W(x)$ to be EF1 and PO.
- If we try roduct of utilities, or negative product of utilities, none of these things work
- In fact there is _no_ (reasonable) welfare function for EF1 + PO
- So, we try CE ideas. Agents have earning requirements, chores pay money.
- Same definition as above but have min-pain-per-buck instead of bang per buck.
- pEF1: Payment EF1, people don't envy what the other people were paid out apart from one chore.
- We try the algo we used for chores, but this doesn't work because the rich get richer and the poor get poorer.
- Open: Existence of EF1 + PO allocations for chores is not known.
- Key ideas:
	- use structural properties of instance class - what do fPO allocations of MPB graphs look like?
	- Carefully modify the standard algorithm to work - need to monitor things more closely than saying 'just do it'


(Federated Learning)

## Talk 9 - Fair and Efficient Resource Allocation - Sujit Gujar


## Talk 10 - Prajakta Nimborkhar - Matchings with Fairness Constraints

- Fairness is something different here!

- Input: set of items, a set of platforms, NOT looking for a 1-1 matching, in particular, it can be many to one but not one to many
- Each platform has a quota of items that it can accept
- The platforms don't treat the items equally, they define _classes_ on items
- All these quotas say 'I want at most $k$ things from some class'
- Platforms can say 'I want at most $k$ things from some class'
- Goal: match maximum _number_ of items to platforms.
- Classes are intended to denote fairness constraints; people don't hog too much of some resource

- Why this model?
	- Committee selection: if there are some number of experts in some area, committees don't want a lot of experts from the same area because they don't want to hog and also why have so many in one area
	- Same idea for project team creation, selecting speakers for a workshop, accepting papers for a conference, etc.

### Laminar Classes
- Defn: when any pair of classes has no nontrivial intersection.
	- Arise naturally; geographic boundaries for example.
	- Special case: classes form a partition.
- The laminar condition allows one to reduce this to finding maximum flows in a similar manner to bipartite matching
- Hardness for non-laminar classes:
	- Reduce from independent set
	- Vertices are the items, and only one platform.
	- Put two adjacent edges in the original graph into a single class and force at most one of them to be selected by making the class's quota 1.
	- Reduction looks very straightforward if one thinks about it

## A $\frac{1}{2}$-approximation for $O(1)$ classes

- $O(1)$ classes, one platform: can get an exact algorithm by solving an integer linear program
- Items have at most $2^{\Delta}$ types, the progaam has one variable $x_{i}$ for each type.
- Maximize $\sum_{1}^{2^{\Delta}} x_{i}$ subject to:
	- quota conditions
	- smth else I forgot smh

- The algorithm: greedy, show approximation guarantee similar to maximal / maximum matching 2-approximation argument
- Can generalize this to a more general case

- Connection between this problem and a generalized independent set notion for hypergraphs
	- Independent set: for each edge $e$ of the hypergraph, have some quota $q(e)$ of vertices from the edge which can be picked
		- Strong independent set: quota is 1 for all edges
		- Weak independent set: quota is dimension (of the hypergraph) - 1 for all edges
		- regular graphs: both the above coincide
	- The problem above is a general version (I think) of this: to reduce from that, set quotas for edges to be quotas for the classes of each platform


## Fair Division via Quantile Shares - Vishnu Narayan

NOTE ON GIVING TALKS:
- Pause for a bit after the last line appears, so that people can read it and parse

- Mainly about a new fairness notion via shares
- Assume agents' valuation functions are normalized (empty set is valued 0) and monotone (more items = better)
- Indivisible goods, deterministic - no random allocation
- EF1, EFX for envy fairness, fair shares: proportionality, maximin share
- Again, don't know if EFX exists even for monotone valuations

- Share function $\tau$ assigns a share value to eah agent, which depends on $v_{i}$ and $n$. And allocation is fair if the value that each agent gets is at least their share value.
- Eg proportional share, maximin share (definitions in notes for talk 2).
- Note that: the share here does not depend on $v_{j}$ for other $j$!
- Also, no notion of envy here.

- Feasibility: a feasible allocation is just one which gives everyone at least their share value
- Results: maximin share is _infeasible_, even for additive valuations.
- Constant fractions of the maximin share: $\frac{3}{4}$-maximin share is feasible for additive valuations
- NO constant fraction is feasible for general monotone valuations for 'easy' counterexamples
- NO constant fraction of the proportional share is feasible: eg 2 agents and a single positively valued item

## Quantile Shares

- Consider an agent who believes that the allocation of items will be done uniformly at random.
- Idea: compare deterministic allocations with this random procedure to assign shares

>[!definition] Quantile Share
>For every $q \in[0, 1] $ the $q-$quantile share $\tau_{q}$ is the $q$ quantile of the random variable $v_{i}(X_{i})$. $X_{i}$ is the bundle they get in the random uniform allocation.

An agent asks what the probability is that their bundle in the uniform allocation is weakly worse than the bundle they received. An allocation is $q-$fria if this probability is at least $q$ for all $i$.

- For $q \leq \frac{1}{2e}$ the $q$-quantile share is feasible for all monotone valuations if Erdos's Rainbow Matching Conjecture is true.
- There are some unconditional results as well.

- An alternate interpretation
- An allocator who does not know the valuations tries to allocate according to the following procedure:
	- Every agent submits a veto list of allocations of size at most $L$.
	- The allocator comes up with an allocation that doesn't appear in any of the veto lists.
	- Question: how large can $L$ be such that the allocator's task is always possible?

- In the absence of any assumptions:
	- $L < \frac{ \# \text{allocations}}{n}$ is clearly possible
	- Monotonicity is missing here
- Result: can get a much much larger bound for $L$ by adding monotonicity and assuming rainbow matching

- Negative result: $q > \frac{1}{e}$, then $q$-quantile share is infeasible.
	- Proof: $n$ agents, $n-1$ items with positive value for each agent, so every allocation, some agent doesn't get something
	- The probatility that an agent doesn't get anything is $\left( 1-\frac{1}{n} \right)^{n-1}$ which tends to $\frac{1}{e}$.

### Connecting the EMC and Quantile Shares

Claim: the $q$-quantile share is feasible for all monotone valuations off the $q$-quantile share is feasible for all monotone 0/1 valuations.

Forward is direct, for backwards: Consider the $q$-quantile of a given monotone valuation. Just send $q$-quantile and higher bundles to 1, and others to 0, this supposedly works.

