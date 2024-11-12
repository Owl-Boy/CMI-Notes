---
tags:
  - Note
  - Incomplete
---
202410271910

Tags : [[Algebraic Automata Theory]]
# Quotients of Syntactic Monoid of a language
---
>[!theorem] 
>A monoid $M$ recognizes a language $L$ iff it divides the [[Monoids as Regular Languages#^a9668b|Syntactic Monoid]] of $L$.
>That is given any monoid $M$ that recognizes the language $L$, there exists a monoid $N$ and morphism $h$ such that the following diagram commutes.
>```tikz
>\usepackage{tikz-cd} 
>\begin{document} 
>\begin{tikzcd} 
>\langle \Sigma^*, \cdot, \epsilon \rangle \arrow[two heads]{r}{h} \arrow{dr}{\eta_L} 
>& N \arrow[hook]{r}{i}\arrow[two heads]{d}{h_L}& M \\
>& \langle \Sigma^* / \equiv_L, \cdot, [\epsilon] \rangle 
>\end{tikzcd} 
>\end{document}
>```

The proof in one direction is easy, if a monoid $M$ recognizes $L$, then the syntactic monoid divides it, we just the image of each letter in the alphabet to equivalence class of the letter in the syntactic monoid. All other elements that are unmapped can go anywhere.

For the other direction, given a Monoid $M$ that the syntactic monoid of $L$ divides it, let $N$ be the sub-monoid that surjects to the syntactic monoid. The idea is to find the inverse image of an equivalence class of a single character, pick one element from the set, and choose that as the element that the lettr maps to in $h$.

---
# References
[[Quotients in Monoids]]