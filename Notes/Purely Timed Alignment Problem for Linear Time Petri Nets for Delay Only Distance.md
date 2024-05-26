---
tags:
  - Example
---

202405161034

tags : [[Conformance Checking]]

#  Purely Timed Alignment Problem for Linear Time Petri Nets for Delay Only Distance
---
>[!question] 
>Given a Linear Time Petri Net $N$ and a log $L$ of traces, find the [[Alignments (Conformance Checking)|Alignment]], i.e the run in $N$ such that it's delay only distance from $L$ is minimum.

## Simple Case : $|L|=1$
### Algorithm
Considering Flow functions instead of the trace directly makes the process significantly easier.

Say the flow function of the given trace in the log reads as $\sigma = [\sigma_{1}, \sigma_{2}\dots \sigma_{n}]$  then the alignment for this can be given using the following function.

```
INPUT 
s : R+
[a, b] : [R+, R+]

OUTPUT : s' in [a, b] such that |s - s'| is minimum

FUNCTION closest(s, [a, b]) := 
    if s < a
        return a
    else if s > b
        return b
    else  -- s is in [a, b]
        return s
    endif
end
```

Using that we get the following algorithm to find the alignment $\tau$ using the following algorithm

```
INPUT
s : list R+  -- log trace
F : Linear Time Petri Net Flow Function

OUTPUT
t : list R+  -- trace on the petri net which is an s alignment

FUNCTION alignment(s, F) :=
	let t = empty list
	for si in s
		ti = closest(si, F(i))
		t.append(ti)
	endfor
	return t
end
```

### Proof
Since the delay only distance is just Manhatten distance on the flow function, we construct a trace with its flow function closes to that of the log trace.

And for each component, we pick the optimal value using the `closest` function. This shows that both our algorithm is correct, and that there is a unique alignment.

## General Case
For this case, we just find the alignment for every single trace in the log, and then return the one of the alignments with the least distance to their corresponding trait.

This works because the distance of the alignment from the log is the least distance of the alignment from any of the log traces. Which means the set of logs received from the above algorithm is guaranteed to contain it.

---
# Related
[[Greedy Cost Bounded Model Repair for Sequential Time Petri Nets with Delay Only Distance]]