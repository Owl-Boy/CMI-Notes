---
tags:
  - Example
---

202405221040

tags : [[Conformance Checking]]

#  Maximal Traces for Linear Time Petri Nets for Delay Only Distance
---

As we update out our Petri Net, the alignment will also change, that is, If we look at the alignment before the process, it is not necessary that it will remain the alignment throughout the end of the process, hence we take care of a set of possible runs that work as alignments, this will simply be the set of alignments we get if we find one for each run in the log individually.

```
INPUT
L : list traces -- Set of Log traces
F : Linear Time Petri Net Flow Function

OUTPUT
C : list (list R+) -- Set of alignment candidate for each log

FUNCTION alignment_candidites(L, F) := 
    let C = empty list
    for log in L
        let candidiate = alignment(log, F)
        C.append(candidate)
    endfor
    return C
end
```

We shall keep this list and edit it as we edit the Petri Net.

Now we need to find the candidates with maximum distance from the log from the given candidate sets. All of these would be alignments.

We define a helper distance function 
```
INPUT
s : list R+ -- a single log trace
F : Linear Time Petri Net Flow Function 

OUTPUT
d : R+ -- Distance of s from F

FUNCTION distance(s, F) :=
    let d = 0
    for i in 1..len(s)
        let [a, b] = F(i)
        if s(i) > a
            d = d + (s(i) - a)
        else if s(i) < b
            d = d + (b - s(i))
        else  -- s(i) in [a, b]
            d = d + 0
        endif
    endfor
    return d
end
```

And now we find the set of Maximal traces

```
INPUT
C : list traces  --  List of Traces
F : Sequential Time Petri Net Flow Function

OUTPUT
C' : list traces -- Alignments

FUNCTION filter_max(C, F) :=
    m = C.map(distance)
    C' = C.filter(\x -> x.distance == m)
    return C'
end
```

Now that we have alignments with us, we can figure out how to edit the Petri Net

---
# Related
[[Greedy Cost Bounded Model Repair for Sequential Time Petri Nets with Delay Only Distance]]
[[Formalising Precision and Fitness for Time Petri Nets]]
[[Purely Timed Alignment Problem for Linear Time Petri Nets for Delay Only Distance]]