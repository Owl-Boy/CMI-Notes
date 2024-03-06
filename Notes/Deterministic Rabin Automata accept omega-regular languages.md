---
tags:
  - Note
---
202401171501

Tags : [[Automata Theory]], [[Logic]]
# Rabin Automata accept $\omega$-Regular Languages
---
>[!attention] Notation Abuse
>I will be using characters like $V$ for both a language and an automata for the langauge. 

>[!tldr]
>We will try to construct a deterministic *Büchi Automata* for a regular language and we shall see that the construction breaks at some point, requiring non-determinism, which can then be fixed by changing the acceptance condition.

Looking at the closer properties of $\omega-$regular languages. 
Given two regular languages $U$ and $V$. We know that $U\cdot \hat V$ is $\omega-$regular.

A simple way to construct a *Büchi Automata* that accepts this would be to take the *DFA* for $U$ and the *Büchi Automata* for $\hat V$, and make $\epsilon-$transitions from final states if $U$ to the start state of $\hat V$.

![[U-Hat-V-Buchi.excalidraw]]

This happens to be a non-deterministic. At the places where the two automata are connected by the $\epsilon-$transitions. And there is no easy way to get rid of it because whenever we reach a final state of $U$, there is no way to be sure if it is time to switch to the other automata, or stay in $U$ for some more letter.

So a run of an $\omega-$word here would look like, a run of the words in states of $U$, written in a line, and from each of the final states, we branch off to a copy of $V$ and continue the computation there.

![[U-Hat-V-Buchi-Run.excalidraw]]
Here, the blue states are states that belong to $U$, each row of pink states represent runs in copies of $\hat V$.

---
## Dropping Redundancies
In the above construction and the interpretation of runs, we create infinitely many copies of $V$, one new copy for each time we want to enter $V$. 

But $V$ is deterministic, and has finitely many states. Which means there are only finitely many configuration of it. To be more precise, if $|V|=n$, we require at most $n$ copies of $V$, with no two running with the same configuration.

---
## Formalizing the Construction
Given $U$ and $V$, we can construct the following automata to eliminate redundancies, while staying deterministic.

### Setup
Let $Q'= Q_U\times (Q_V\cup\{\bot\})^{n+1}$ 
This is an $n+2$ array where the first element is the position in the automata $U$ before moving over to $V$.
Then we need $n$ elements for the $n$ possible configuration for automata $V$. We are keeping an extra to make proofs about this easier, it is not necessary though. The bottom represents a machine where we are not running a computation at the moment.
![[Rabin-Example-setup.excalidraw]]

### Transitions
Transitions in the first element are just run's in $U$. But we do the following to deal with the copies of $V$. 

- If we reach a final state of $U$, we find the first element at the state $\bot$. And we set that element to the to the start state of $V$. This is starting a new run when we reach a final state.
  ![[Rabin-Example-transition-1.excalidraw]]
- If any of these elements are in the same state (have the same configuration) we turn every element except for the one with the smallest index to $\bot$. This step drops redundant computations.
  ![[Drawing 2024-01-18 15.35.43.excalidraw]]
- If from any state a letter is read without a corresponding transition, that state is also taken to $\bot$.

>[!theorem] Lemma
> There will always be at least 1 element with the value $\bot$. This lets use guarantee that we can take the transitions described in the first bullet.
> 
> *Proof:* The transitions in the second bullet point reduces redundant computations, so apart from the first element, the number elements that can be used are equal to the number of configurations.
> Since there are $n$ states in $V$, we can use at most $n$ elments, apart from the one dedicated to $U$. Hence there will be at least $1$ element that stores $\bot$.

### Start Configuration
The element which represents computation in $U$ is set to its start state.

If the start state of $U$ is also an accept state, we set the first element to be the start state of $V$. Otherwise all but the element dedicated to $U$ have $\bot$.

### Acceptance Conditions
Given a word from $U\cdot \hat V$, we want an accepting run, and given a word which is not in the language, we want to make sure that there isn't a run. In our automata, given a word $w$
If $w\in U\cdot \hat V$:
- We can break it into parts $u$ and $v$. We follow the first element until the end of $u$, and then we look at element, where $\bot$ was replaced with the start state of $V$, that is the state where new computation started once $u$ was read. *We reach good states infinitely may often for a run*.
- That itself is not enough, because there are transitions that rewrite computations to $\bot$(bullet 2 of the above section). But that is okay because each time that transition is taken, there is another element with a lower index that has the same configuration. We can think it as continuing our computation at a lower index. This cannot happen indefinitely so we will definitely reach some index after which the current computation will never be overwritten by $\bot$. 
	  ![[Rabin-Example-Property.excalidraw]]	
- Also there may be a case where we have a word that reaches a final state of $U$, and then in some position we reach a good state of $V$, but then the computation is eventually overwritten by $\bot$, then later somewhere in the word, we again reach a final state of $U$, and start a computation in the same element which will be overwritten in the same way and so on. For this condition we keep reaching a final state infinitely many often, but the runs are discarded by $\bot$ rewrites. The above two points suggest the following condition. *$\bot$ is visited in the "accepting" element only finitely many times*.
So a reasonable acceptance condition would be the following.
>[!tip] Acceptance Condition
>A word is accepted, if there is some index(apart from the one dedicated to $U$), where we reach an accepting state of $V$, infinitely many times, and we write $\bot$ on that state only finitely many times.

For the other direction: 
If there is $w$ that is accepted  by the above automata:
- Then there is an element where the good states are reached infinitely many often, and $\bot$ is reach finitely often. Let the index of that element be $i$ and the last $\bot$ was removed at step $k$.
- We now look at the following run of the word. Let the first part of the word, that is read in the language be $u$, and we have $u=w_{k}$. We know this is fine, because $\bot$ is removed after the $k^{th}$ is read, and out transitions only remove $\bot$ if the prefix is accepted by  $w$.
- Then we then the rest of the word is computed in $i^\text{th}$ element, where it is accepted because good states are visited infinitely many often without encountering any invalid states ($\bot$). Hence the word belongs in the language $U\cdot \hat V$.

>[!seealso] Rabin Automata (informal)
>The accepting condition above is precisely the Rabin Accepting condition, where we have pairs of good(accepting) and bad($\bot$) states and we want to visit the good states infinitely often and the bad states only finitely many times.

Union of two deterministic Rabin Automata can be accepted by a deterministic rabin automata, this construction is easy to prove. Hence Given any Non-Deterministic Buchi Automata, we can convert it to a Deterministic Rabin Automata.

---
# References
[[hat V- Deterministic Büchi Automata]]
[[Rabin Automata]]