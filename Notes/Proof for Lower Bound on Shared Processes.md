---
tags:
  - Example
---

202408220928

tags : [[Concurrent Programming]]

#  Proof for Lower Bound on Shared Processes
---
>[!Theorem]
>There is no [[Deadlock-freeness|Deadlock free]] [[Mutual Exclusion]] algorithm for $n$ threads that uses fewer than $n$ shared variables.

>[!definition]
>A configuration $((p_{1},...,p_N),m)$ is *quiescent* if all processes are in remaining (are not in, and do not want to enter the critical zone).
>
>It is $P$*-quiescent* for a subset $P$ if it looks like a quiescent configuration for the processes in $P$ (i.e. it agrees with some quiescent configuration on the states of processes in $P$ as well as the state of the memory)

>[!definition]
>A configuration $C$ *covers* a set $S$ variables if for each variable $X$ in $S$ there is a specified process in $C$ that writes to $X$ via its next transition.

---

***CLAIM:***
Suppose $C$ is a configuration such that
1. A set $X$ of processes covers a set of variables $V$.
2. $C$ is $P$-quiescent.
Then there is a run $C \xrightarrow{\quad P\quad }^* C'$.

***PROOF:***
Let $C\sim_{P} D$ where $D$ is a quiescent configuration.

>[!note] There exists a run $\rho := C \xrightarrow{\quad X\quad} C'$ such that
>1. Only threads from set $X$ execute.
>2. $\rho$ begins with each thread in $X$ writing to the variable it covers (from $V$)
>3. At least one thread from $X$ has entered the ==critical section== in $C'$. This point follows from deadlock freedom.

Further, there is a $P$-run $\sigma := D \xrightarrow{\quad P\quad}^* D'$ where $P$ enters the ==critical section==, this is also a consequence of deadlock freedom.

If all variables written to in $\sigma$ are in $V$, then there is a run $C \xrightarrow{\quad \sigma\quad}^* C_{1} \xrightarrow{\quad\rho\quad}^* E$ where at least one of the threads from $X$ and $P$ are in the ==critical section==. This is true because $C_1 \sim_P D$ so they agree on shared memory and common states.

This contradicts [[Mutual Exclusion]].

Therefore $\sigma$ actually looks like $D \xrightarrow{\quad P(\rho_{1}) \quad}^*D_{1}\xrightarrow{\quad \text{write}(v) ;P(\rho_{2})\quad}^* D'$
where $v$ is a variable outside $V$.

Then $C \xrightarrow{P(\rho_{1})} C'$ is a $P$-run and $P$ writes to a variable different from $V$ at $C'$. This completes the proof of the claim.

----

Let $P_{1},\dots P_N$ be the $N$ threads and let $V_{1},\dots,V_N-1$ be the given set of shared variables

***Lemma***: 
Let $C$ be a quiescent configuration. For each $0 \leq i \leq N-1$ there is a run $C \longrightarrow C'$ where 
1. The threads $P_{1},\dots,P_{i}$ cover some set of $i$ variables $U_1,\dots,U_i$
2. $C'$ is ${P_{i+1},...,P_{N}}$-quiescent.

***Proof:***
For $i=0$ the result holds trivially taking $C = C'$.

Induction:
Consider a run as follows, where only the threads from $P_1,\dots,P_{i}$ execute.

$$
\begin{align}
C = C_{1} &\xrightarrow{\quad\rho_{1}\quad}^* D_{1}  \\
&\xrightarrow{\quad CS\quad}^*C_{2}  \\
&\xrightarrow{\quad\rho_{2}\quad}^* D_{2} \\
&\xrightarrow{\quad\text{writes}(Z_{2}) \to CS}^* C_3  \\
&\dots C_{M}  \\
&\xrightarrow{\quad\rho_{M}\quad}D_M  \\
&\xrightarrow{\text{writes}(ZM) \quad} CS
\end{align}
$$

Each thread starts to run, enter its critical section and then exits it. leaving $C_{1}, C_{2} \dots C_{M}$ to all be quiescent.
$D_i$ covers the set $Z_i$ of variables of size $i$.

Each $D_i$ is $\{ P_{i+1}, \dots, P_{N} \}$ quiescent.

The segments $CS \to C_{i}$ refers to a run where each thread in $P_{1}\dots P_{i}$ visits the $CS$ and then ends up in the reminder section (so that $C_{i}$ is quiescent).
The induction hypothesis guarantees the existence of $\rho_{i}$ and $D_{i}$ satisfying the above properties and deadlock-freedom guarantees the runs from $D_{i}$ to $C_{i+1}$.

Assuming $M$ is more than the number of ways of choosing a subset of size $i$ from a set of size $N-1$, it is guaranteed that some $Z_{i} = Z_{j}$. Thus we may consider the run up to $D_j$ as to be of the form

$$
C \xrightarrow{\rho_{A}}^* D_{i} \xrightarrow{\text{Writes}(Z) \to \rho_{B}}^* C_{j}\xrightarrow{\rho_{C}}^* D_{j}\xrightarrow{\text{Writes}(Z)}^*
$$

where $C$ and $C_{j}$ are both quiescent, only the threads $P_{1}\dots P_i$ execute in the
entire run, $D_i$ and $D_j$ cover the set of variables $Z = \{U_{1}, ... U_{i}\}$ and $D_{i}$ and $D_{j}$ are ${P_{i}+1,... P_{N}}$-quiescent.

Further, applying the claim to $D_i$ we know that there is $P_{i+1}$-run sigma $D_{i} \longrightarrow P_{i+1} (\sigma) \longrightarrow D_{i}' \xrightarrow{\text{Write}(v)}^*$ where $v\not\in\{U1,\dots,U\}$
and this is the first write to a variable outside $\{U1,...,Ui\}$ along this run.

Then

C ---rhoA--->* Di --sigma-->* Di' -Writes(Z)->* --rhoB-->Cj' --rhoC --->*Dj'

is a valid run. In all the configurations from Di' to Dj' the thread Pi+1
covers v. And in Dj' the thread P1,... Pi cover U1, ..., Ui. 
Thus, at Dj', the processes  P1,...,Pi+1 cover the set {U1, ..., Ui, Ui+1 = v}.

The configuration Dj' differs from Dj only in the state of the thread Pi+1 :
The memory Dj and Dj' are identical since sigma did not write to any variable
outside Z and the transitions immediately after Di' erased those writes. Thus
the two runs have identical memory at every configuration following these
writes. Since Cj was {Pi+1, ... PN}-quiescent, it follows that Cj' is
{Pi+2,...,PN}-quiescent.

This completes the proof of the Lemma.

Corollary: There is no deadlock-free ME algorithm for N threads that uses only 
N-1 locations

Proof of Corollary: 
Pick any reachable quiescent configuration C. By the above Lemma
C --->* C' where at C' {P1,...PN-1} cover {V1,...VN-1} and C' is also
PN-quiescent. But this contradicts the above claim which requires a PN run from
C' which writes to a variable outside {V1,.. VN-1} and there is no such
variable.

---
# Related
