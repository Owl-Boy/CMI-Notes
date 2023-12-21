---
tags:
  - Note
---
202312041512

Tags : [[Advanced Algorithms]]
# Job Scheduling Problem
---
**Given:** $n$ jobs, $m$ identical machines, processing times $p_{j}$ for each job $j=1,\dots,n$
**Schedule:** A schedule is an allotment of a slot to each job on any of the $m$ machines. A job cannot be stopped midway.
**Goal:** Finish all jobs as early as possible. (NP-hard)

## Basic algorithms
---
- **Greedy:** Take jobs one by one and schedule them at the earliest possible time.
- **Local Search:** Start with an arbitrary schedule. If the last finishing job can be moved to an earlier slot, move it.

**LB1:** $\max\limits_{j}p_{j}$
**LB2:** $\sum\limits_{j} \frac{p_{j}}{m}$
Look at the job that finished last, say $j$. Right before it was scheduled (say at time $s_{j}$), every machine was busy. Thus $\text{Cost}(OPT)\geq s_{j}$, and $\text{Cost}(OPT)\geq p_{j}$, so
$$
s_{j}+p_{j}\leq 2.\text{Cost}(OPT).
$$

> [!success] Thus we get a $2-$approximation algorithm.

## Smarter greedy algorithm (Sort first)
---
Sort so that $p_{1}\geq\dots\geq p_{n}$. Then implement greedy.
If $j$ was the job that finished the last, we can ignore jobs $j+1,\dots ,n$ because they didn't start before $j$ nor did they end after $j$.
So we can assume job $n$ finished last.
Let $C$ be our completion time, and $C^{*}$ be completion time of OPT.
$C=s_{n}+p_{n}$.
If $p_{n}\leq \frac{1}{3}C^{*}$, then $C\leq \frac{4}{3}C^{*}$.
If $p_{n}> \frac{1}{3}C^{*}$, then $p_{j}> \frac{1}{3}C^{*}\quad \forall j$.
Thus in OPT, no machine has $>2$ jobs.

> [!tip] **Claim:** If OPT schedules $\leq 2$ jobs on each machine, then greedy algorithm gives the OPT schedule.

> [!success] Thus we get a $\frac{3}{4}-$approximation algorithm.

**Tightness example:** $2m-1,2m-1,\dots,m,m,m$. $C=4m-1$, whereas $C^{*}=3m$.

## Improvement
---
If $p_{j}\leq \frac{1}{k}C^{*}$ for some $k>3$, then we can get better approximation.
We define *short jobs:* $\left\{  j\ |\ p_{j}\leq \frac{1}{k}C^{*}  \right\}$, and *long jobs:* $\left\{  j\ |\ p_{j}> \frac{1}{k}C^{*}  \right\}$.
OPT schedule can't have $>k$ long jobs on any machine. So $|\text{long jobs}|\leq km$.

> [!tip] Idea:
> 1. Schedule long jobs optimally.
> 2. Schedule short jobs greedily.

---
# References
[[Approximation Algorithms]]
--> [[Linear Programming]]