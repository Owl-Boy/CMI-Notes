---
tags:
  - Example
---

202410122100

tags : [[Theory of Computation]]

#  2DFAs are equivalent to DFAs
---
Given a DFA, one can easily construct a 2DFA, by having the same states as the DFA and only move the head right, and on reading $\triangleleft$ decide if the word will be accepted or not.

The other direction is not that trivial.

>[!Theorem]
>Given a 2DFA $\mathfrak A$ with language $L$, there exists a 1DFA $A$ whose language is also $L$.

>[!idea]
>The thing that makes the theorem not obvious is the fact that one is allowed to back and re-read the input again and again, 
>
>That is, whenever one reaches a letter $s$ in the input tape, they can either move to the right and continue reading like a normal DFA or move left and re-read parts of the input, until one reaches $s$ again (and possibly repeating this step), until they finally move to the character after $s$. 
>
>Note that this can only be done at most $|Q|$ many times, otherwise the machine gets stuck in a loop and the word is rejected. This is another observation which will be useful.
>
>Given a state $q$, say we get to $q'$ following the above idea when we are ready to need the next character. We want to do these steps for many states like $q$ because we have a chance to read the same character from different states each time we revisit it, to fix this issue, we associate with each prefix of the input word with a function $f:Q \to Q$ and we incrementally build it for the entire word and check if it takes the inital state to the accept state or not.

Using the above idea, we start by building "the function that, when given the state where you read a given letter and returns the state where the next letter will be read after for the very first time".

For example,  let the current content of the tape be:

![[2DFA equiv.excalidraw]]

Then the function would take $q$ as an input and return $q'$ as the output which will be the state where the next $c$ is read.

We will construct a function for each word recursively as follows
***Base Case:***
The case of the word $\varepsilon$ is the function $q \mapsto \delta(q, \triangleright)$ whose definition will be helpful for the recursive case.

***Recursive Step:***
Given a function $f_{w}$ for a word $w$, we want construct the function $f_{wa}$ for the word $wa$ as follows.

If $\delta : (q, a)\mapsto (q', R)$, then $f_{wa}: q\to q'$.
If $\delta : (q, a) \mapsto (q', L)$, then the machine has gone back to read the previous word and we need to handle that case.

Since we read $a$, took the head one step back and went to state $q'$, the next time we have to read $a$, we will be in the state $f_{w}(q')$.

If $\delta: (f_{w}(q'),a) \to (q'', R)$, then we do $f_{wa}: q \mapsto q''$, otherwise we keep "zigzaggin" like this until we meet 2 scenarios
- We found a state that takes a transition that goes Right to read the new character and takes the control to the state $p$ then we say $f_{wa}: q \mapsto p$.
- We reach a state twice, which indicates a loop that we get stuck in, for our DFA, this means we just instantly go to the reject state, and we write that as $f_{wa}: q \mapsto q_{r}$.
- Except if we reach the accept state at any point in the middle, then we say $f_{wa} : q \to q_{a}$

Having outgoing edges from the accepting and rejecting state make this step easier.

Each function here, represents a word, and exclusively gives information about the movement to and from related to the last character, in context of the given word. What we want is to know which word takes the input state to the accept state.

We now let our state space to be $Q \times (Q \to Q)$ where the first component lets us know which state we are in, in the simulation and the function tells us where we will go next, hence the transitions look like:
$$
\delta': (q, f_{w}),a \mapsto (f_{wa}(q), f_{wa})
$$
And we keep doing this until the entire word is read (including the right end marker). If the first component is the accept state, then we accept the word, if the first component is the reject state, then we reject the word.

Finally, we get the following construction, given a 2DFA $\mathfrak A = \langle Q,\Sigma \cup \{ \triangleleft, \triangleright \} ,q_{0}, q_{a},q_{r}, \delta \rangle$ we will now construct the following DFA $A = \langle Q', \Sigma', q_{0}', F, \delta'\rangle$
- Let $Q' = Q \times (Q \to Q)$
- Let $\Sigma' = \Sigma$
- Let the start state be $q_{0}'=(q_{0},  q \mapsto \delta(q, \triangleright))$
- Let the accepting states be $F=\{ (q, f_{\omega}): f_{w\triangleleft}(q)=q_{a}\}$
- Let $\delta'$ be what was defined above

This $DFA$ has $n^{n+1}$ states for a 2DFA with $n$ states, the construction that reaches the tight lower bound constructs a DFA with $n(n^n-(n-1)^n)$ states.

---
# Related
[[2-Way DFA]]
[[Formal Description of a 2-DFA]]