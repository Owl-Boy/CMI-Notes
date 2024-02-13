Given a regular language $V$ consider the language $\hat V$ 
$\hat V=\{\alpha\;|\;\text{infinitely many prefixes of }\alpha \text{ belong to }V\}$.

Yes, we find a DFA for $V$ andjust trivially make it a Büchi automata(make the final states good states)

This is not true for an NFA

For a DFA we can give this guarantee, because the run a prefix would just be an extension for the current one. So they do go over infinitely many good states(each extension is a new visit to a final state)

For an NFA we can find a language where all prefixes of the word $\alpha$ get to an accepting state exactly once. Ex let $V=aa^*a$ 
$\hat V$ can always be modelled by a deterministic Büchi automata.

$U\cdot \hat V$ cannot be accepted by a deterministic Büchi automata.

This is motivation for Rabin condition.

To deal with the above situation, we can take deterministic finite automata for both $U$ and $\hat V$.
we would like to have epsilon transitions from $U$ to $\hat V$ at final states of $U$.

running a word on that would be like, running a word and $U$ and branching off to $\hat V$ every time a final state is encountered. 

That procedure makes redundant copies because there are only finitely many configurations of a run in $\hat V$. as there are finitely many states. So we only need to run as many copies of $\hat V$ as we have states of $V$.

So for a determinitsic one we have states $Q^U\times(Q^V\cup\bot)^{N+1}$ 

each of the $N+1$ extra parts are like $N+1$ copies we have which is all we will need.

Then whenever we reach an end state in $U$ we start an a copy of $V$ that currently holds $\bot$ which is the initial value.

If two copies ever go to the same state, then we set the later one to $\bot$ so we have just one copy for one configuration.

If there is an accepting run, it will be running in one copy. That run might just work, or it be overwritten but it woudl be like, it continues in a copy above it. and this overwritten can only be done finitely many times.

- There will be an $i$ such that accepting state in the $i^{th}$ copy will be visited infintely many often.
- $\bot$ will be written in that copy only finitely many often.

$G_i$ is the states of states where the $i^{th}$ component is an accepting state of $V$
$R_i$ is the state where $i^{th}$ component is $\bot$.

The after the last of the finitely many bottoms is  read, a new run is started there, that run is the run, the run where we correclty switvh from $u$ to $v$.


The Gi and Ri condition is called the Rabin  acceptance condition.

Rabin came up with this because he wanted to close the languages under complementation.
