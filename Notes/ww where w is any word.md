202211150118

type : #Example
tags : [[Theory of Computation]]

#  ww where w is any word
---
### Question: $\{ww|w\in \{a, b\}^*\}$ is a recursive set 
###  Answer:
The machine first scans through the word until it finds the first $\sqcup$ and keeps track of the size of the word in mod 2, rejecting immediately if the word is not of even length.
If it is then it puts a $\dashv$ at the end and then repeatedly scans back and forth the input.
On each passing from right to left, it marks the first unmarked $a$ or $b$ with a $'$ and on each passing from left to right, it marks the first unmarked letter with $`$, it continues until all symbols are marked.

The initial tape contents are
$$
\begin{matrix}
\vdash &a&a&b&b&a&a&a&b&a
\end{matrix}
$$
and the tape condition in the following few steps would be 
$$
\begin{matrix}
\vdash &a&a&b&b&a&a&a&b&b&\acute a &\dashv &\sqcup&\sqcup&\sqcup&\dots\\
\vdash &\dot a&a&b&b&a&a&a&b&b&\acute a &\dashv& \sqcup&\sqcup&\sqcup&\dots\\
\vdash &\dot a &\dot a&b&b&a&a&a&b&\acute b&\acute a& \dashv& \sqcup&\sqcup&\sqcup&\dots\\
\vdash &\dot a &\dot a&b&b&a&a&a&b&\acute b&\acute a &\dashv &\sqcup&\sqcup&\sqcup&\dots\\
\vdash &\dot a&\dot a&b&b&a&a&a&\acute b&\acute b& \acute a& \dashv& \sqcup&\sqcup&\sqcup&\dots\\

\end{matrix}
$$
now the left and the right half of the word are marked differently.
$$
\begin{matrix}
\vdash &\dot{a}&\dot{a}&\dot b &\dot b&\dot{a}&\acute{a}&\acute{a}&\acute b&\acute b&\acute{a}& \dashv &\sqcup &\sqcup&\sqcup& \dots
\end{matrix}
$$

Then the machine starts from the left and scans to the right repeatedly, it sees the first unremoved symbol, removes it, but remembers it, then it keeps moving forward until it finds the first symbol marked the other way, if it corresponds to the original letter then repeat the process, it at any point it fails,  move to the reject state. Otherwise it will remove all letters and then go to the accpeting state.

$$
\begin{matrix}
\vdash & \dot a & \dot a & \dot b & \dot b &\dot a& \acute a & \acute a& \acute b & \acute b &\acute a & \dashv & \sqcup & \sqcup & \sqcup & \dots\\
\vdash & \sqcup & \dot a & \dot b & \dot b &\dot a& \sqcup & \acute a& \acute b & \acute b &\acute a & \dashv & \sqcup & \sqcup & \sqcup & \dots\\
\vdash & \sqcup & \sqcup & \dot b & \dot b &\dot a& \sqcup & \sqcup& \acute b & \acute b &\acute a & \dashv & \sqcup & \sqcup & \sqcup & \dots\\
\vdash & \sqcup & \sqcup & \sqcup & \dot b &\dot a& \sqcup & \sqcup& \sqcup & \acute b &\acute a & \dashv & \sqcup & \sqcup & \sqcup & \dots\\
\vdash & \sqcup & \sqcup & \sqcup & \sqcup &\dot a& \sqcup & \sqcup& \sqcup & \sqcup &\acute a & \dashv & \sqcup & \sqcup & \sqcup & \dots\\
\vdash & \sqcup & \sqcup & \sqcup & \sqcup &\sqcup& \sqcup & \sqcup& \sqcup & \sqcup &\sqcup & \dashv & \sqcup & \sqcup & \sqcup & \dots\\
\end{matrix}
$$



---
# Related


