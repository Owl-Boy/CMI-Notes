202301270201

Type : #Note
Tags : [[Category Theory]]


# Structure Preserving Maps
A central theme in cateogry theory is the study of structure preserving maps. 
A map $f:X\to Y$ is like an observation of $X$ via a relationship it has with another object, $Y$ amd asking which aspects of $X$ one wants to preserve under the observation $f$ simply becomes the question ==what category are you working in?==.

As an example, there are a lot of funtions from $\mathbb R$ to $\mathbb R$, and we can think of them as observations: rather than view $x$ directly, we only observe $f(x)$. Out of all functions $f;\mathbb R\to \mathbb R$, only some of them are:
- **Order preserving**([[Preorder]]): if $x\le y$ implies $f(x)\le f(y)$, for all $x, y\in \mathbb R$;
- **Metric preserving:** if $|x-y|=|f(x)-f(y)|$, for all $x, y\in \mathbb R$;
- **Order preserving:** if $f(x+y)= f(x) + f(y)$, for all $x, y\in \mathbb R$;

For each of the three properties defined above (call it _foo_), there exists fuctions which preserve _foo_ and are called _foo-preserving_.

The less structure is preserved by our observation, the more ==surprises== occur when we observe its operations. One might call it [[Generating Effects]]

---
# References
