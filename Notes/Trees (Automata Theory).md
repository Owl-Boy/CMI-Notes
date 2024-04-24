---
tags:
  - Note
  - Incomplete
---
202404221804

Tags : [[Automata Theory]]
# Trees (Automata Theory)
---
>[!attention] 
>The special kind of trees discussed here are *Rooted, Ordered* and *Finitely Branching*. This is not a general note for trees.

^1b71dc

The 3 properties mentioned in the [[Trees (Automata Theory)#^1b71dc|Attention Callout]] can be used to define the trees we will be dealing with as follows.
- Trees are a special case of graphs where there is a unique path from a designated *root node* to any other node.
- Given any node, there are finitely many children of the node that are ordered.

## Formalizing Trees
One way to formalise trees is to separate the "structure" of the tree and its "colours".

### The Structure
>[!idea] Intuition
>We have the root as the default location, and from each node, we label the children with natural numbers representing their order, Each path is then represented by a the sequence of nodes taking corresponding to a word formed from the alphabet $\mathbb{N}$.

Since we are working with trees, each node can corresponds to the path from the root to it which can be represented in the following manner

>[!definition] Tree-Domain
>We define $\text{dom}$ to be a function from the set of trees to the set of *prefix closed subsets* of $\mathbb{N}^*$  such that if $u\cdot i \in \text{dom}(t)$ for some tree $t$, $u \cdot j \in \text{dom}(t)$ for all $j<i$ . 

>[!todo] Diagrams

A tree where the maximum element of $\mathbb{N}$ being used is $k$ is called a $k$-ary tree

### The Colour
Now that we have a way to define the "structure" of a tree, we can construct a tree over some set $S$ by taking such a "structure" and colouring its nodes with the members of $S$. This is defined using the $\text{val}$ function where $\text{val}(t)$ is a function from $S$ to $\text{dom}(t)$. Such a tree is also called $S$-labelled.

>[!todo] Diagram + Example

>[!definition] Notation
>We can now define a tree $t = \langle \text{dom}_{t}, \text{val}_{t} \rangle$, also we define the following function 
>- $\text{dom} : t \mapsto \text{dom}_{t}$
>- $\text{val} : t \mapsto \text{val}_{t}$



---
# References
[[Tree Automata]]