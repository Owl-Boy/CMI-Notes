202302191902

Type : #Note
Tags : [[Complexity Theory]]

---
# Emulating a Multi-tape Turing machine on a Single Tape Turing Machine Efficiently

**Claim:** If [[Turing Machines with multiple tapes|Multi-tape Turing Machine]] can compute inputs of size $n$ in $O(T(n))$ then a [[Turing Machines|Single-tape Turing Machine]] can emulate it in $O(T^{2}(n))$.
**Proof:** 
If the multiple tape turing machine has $k$ tapes, then its contents can be copied down to the single tape turing machine by interleaving the letters, as in 
$$
\begin{align*}
\text{Letters from tape} &\longmapsto \text{can be written in positions}\\
1 &\longmapsto 1, k+1,2k+1\dots\\
2 &\longmapsto 2, k+2,2k+2\dots\\
3 &\longmapsto 3, k+3,2k+3\dots\\
&\;\;\;\vdots\\
k &\longmapsto  k,2k\;\;\;\;\;,3k\;\;\;\;\;\;\dots\\
\end{align*}
$$
For each of the tapes, the letter which corresponds to the one that was pointed at by the head can be marked,eg $a$ can be written as $\hat a$.

Then in a single step, the turing machine can read the section of the tape which is filled to figure out the position of the heads, can go back and then repeat this while applying the valid changes, Hence a move of the $k$ tape turing  machine can be emulated in $O(T(n))$ hence, the entire execution of the machine can be done in $O(T^2(n))$ steps.

---
# Related Problems

---
# References
[[Turing Machines with multiple tapes]]