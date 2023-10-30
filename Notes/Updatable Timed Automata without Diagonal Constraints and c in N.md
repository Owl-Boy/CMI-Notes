---
tags:
  - Example
---

202310301144

tags : [[Timed Automata]]

#  Updatable Timed Automata without Diagonal Constraints and positive constants only
---

>[!note] Theorem
> Updatable Timed Automata without Diagonal constraints and all constants positive are just as expressive as regular Timed Automata
> 

To prove the above theorem, we give a construction to regular *timed automata*.

---
## Construction of Regular Timed Automata.

Since we are not allowed to assign values of one clock to another in a regular timed automata, we simulate that process by replacing the clocks in guards with whatever other value that we want.
This will create a dependency chain that needs to be dealt with while resetting clock that have other clocks dependent on them.

We first get rid of all the transitions of the form $x:=c$ for all $c\ge 0$ using the same method discussed in [[Updatable Timed Automata with only x=c and x=y updates]]
### Removing updates of the form $x:=y+c$
For such constraints we create a copy of of the states that we mark  with the transition $x:=y+c$ and instead of using $x$ in all of the guards in the outgoing edges, we use $y+c$, rendering the variable $x$ free to be used elsewhere.
Now for all transitions that create a dependency on $x$ like $z:=x+c_2$ we rewrite them as $z:=y+c+c_2$.
Also transition that will make $y$ dependent will also be handled in a similar way. For a transition with update $y:=w+c_{3}$ we also do $x:=w+c_3+c$ and $z:=w+c_3+c+c_2$ 

Updates of the from $x:= x+c$ are trivial to deal with.  We also update all clocks that are dependent on it.

Now we have guaranteed that there will be no dependency changes longer than 2 elements long.

This gets rid of all the transitions of the form $x:= y+c$ but creates a dependency issue that should be dealt with carefully in the next step.
### Resets of clocks 
Resetting a clock that is dependent on another clock or is not a part of any dependency tree is trivial, it resets normally. If the clock is dependent on other clocks then it removes the dependency.

For resetting of clocks that have other clocks dependent on them, we reset one of the free clock available and use those instead, to preserve the original value of the clock.

The only non trivial fact left to prove is that there will be free clocks available to use.

This is true because whenever we reset the base of a tree, we use a different with the same name as the base for its alias such that it shadows the original one, now if it becomes dependent on something else, that frees the clock again, and if something else becomes dependent on it, then that also gives a free clock. Hence whenever there is a dependency tree, there will always be free clocks.

### Final steps
All constants that have value greater than the maximum value used in guards and updates of the original automata are reset to the maximum guard value. This ensures that the number of states will be finite.
This also ensure the termination of the procedure as we can only produce a finite amount of copies of states and transitions

### Example
![[Pasted image 20231030125421.png]]
here the subscripts of states represent the actual values used instead of directly using the clocks, like for $p_{x,x}$ the clock $x$ is being used for $y$.

### Importance of not having diagonal constraints
We could do the modification done in the section [[Updatable Timed Automata without Diagonal Constraints and c in N#Final steps|Final steps]] because there are no negative constants and diagonal constraints.
Having negative constant means that, you can add any constant to a clock any number of times but the new value need to kept track of because its not necessary that subtracting values from the clocks would bring the value below the max constant, hence we cannot guarantee a finite amount of states.
Having diagonal constraints lets us have negative constants to add for difference between clocks, causing the same problem.

---
# Related
- [[Updatable Timed Automata]]