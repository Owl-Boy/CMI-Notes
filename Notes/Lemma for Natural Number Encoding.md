---
tags:
  - Example
---

202403071605

tags : [[Logic]]

#  Lemma for Natural Number Encoding
---
>[!Theorem] Lemma
>Let $h\geq 1, l,\geq 1$. There is a first order formula $\chi_{h,l}(x, y)$ of size $O(h \cdot \lg h+l)$ such that for all words $\mathcal W$ and $a, b\in W$ and $m, n\in[0\dots T(h, l)]$ the following holds:
>If $a$ is the first position of a subword $\mathcal U\sqsubseteq  \mathcal W$ with $\mathcal U\cong \mu_{h}(m)$ and $b$ is the first position of a subword $\mathcal V\sqsubseteq \mathcal W$ with $\mathcal V\cong \mu_{h}(n)$, then 
>$$
>\mathcal W \models \chi_{h,l}(a, b) \iff m=n
>$$
>And the formula can be computed in $O(h \cdot\lg h + l)$

>[!success] In simpler words
>We are given a string where there are 2 sub-strings that encode numbers that we want to check for equality. Then for every $h, l$ we can find a formula $\chi_{h, l}$ that takes in the start position of the two sub-words and is satisfied iff the subwords represent the same numbers less that $T(h, l)$. The formula's size and complexity to find is $O(h \cdot \lg h + l)$

---
## $\mu_{1}$ encoding
These are just the binary representation of a number enclosed within tags. Also our goal is to be able to write a formula of size $O(n)$ that can for equality of number of size upto $2^n$. This can be trivially done by checking digit by digit and can be given by:
![[Pasted image 20240307162602.png]]
The first two lines of the equation just make sure that we stop reading once we reach the closing tag and we start reading after the opening tag.

We shall build the formula recursively and this will be our base case.

## General case
Now we will build an army of auxiliary functions to help us define the general formula.

First we have 
![[Pasted image 20240307163144.png]]
These formulas state that $y$ is in the interior of the encoding of the word and $y$ is at the end of the encoding of the word respectively.  assuming a $\mu_h$ encoding starts at $x$.

Now to construct the formula we show that, every corresponding subwords and the digit after that the two words match, then they are the same word.

For all subwords of $\mu_h(p)$ of the form $\mu_{h-1}(q)$ we have $q \leq L(p)$. Our Formulas will only word if $q\leq L(p)\leq T(h-1, l)$, but by definitions of $L$ and $T$ this holds whenever $p<T(h, l)$ which is what we are assuming anyways.

>[!error] Straightforward approach which fails.
>![[Pasted image 20240307164955.png]]
>Here the first term states that if the two given encodings of the form $\mu_h(p)$ are the same, then for every position $w$ in the interior of the first word that is the start of a subword of the form $\mu_{h-1}(q)$, there is a position $z$ in the interior of the second encoding, also of the form $\mu_{h-1}(q)$ and that both encode the same word.
>The Second sentence says the same in the opposite direction.
>The third part states that if you have two isomorphic subwords of the form $\mu_{h-1}(q)$ in both the words, then they are followed by the same digit.
>
>This approach fails because the resultant formula is exponential in $l$.

But that is an easy problem to fixed by rewriting the formula as follows.
![[Pasted image 20240307165923.png]]

This formula states that for all $w$ there will be a $z$ such that,
- If one of them of them belong to interiors of separate words
- If $w$ is the start of a $\mu_{h-1}$ subword so is $z$
- such positions do exists
- The subwords match and are followed by the same letter.

This formula now satisfies our bound for the size because
- $\chi_{1, l}$ is linear in size of $l$
- Every time $c\cdot \lg h$ terms are added to go from $\|\chi_{h-1, l}\|$ to $\|\chi_{h,l}\|$
	- This log factor comes in because we want to talk about the binary encoding of the formula, so each tag check becomes a $\log h$ sized check

The construction also shows that the formula can be computed in time linear to the size of the output hence it follows the bound.\

---
# Related
[[Succinct Encoding of Natural Numbers Using Strings]]