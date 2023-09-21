<center><h1>TOC Problem Set 1</h1></center>
Not to be graded.
<br>

### 1.
Design <i>DFA</i>s for the following language in $\{0,1\}^*$
- $L=\{w\ |\ \text{Number of }0\text{s and } 1\text{s are both even} \}$
- $L=\{w\ |\ w\ \text{read as a binary number is divisible by }3\}$
<br>

### 2. Subsequence
For any word $w\in {0,1}^*$, let $L_{w} = \{y\ |\ w\text{ is a subsequence of }y\}$; any string $s'$ which can be formed by dropping letters from $s$ while maintaining ordering is subsequence of $s$.

Design a <i>DFA</i> when:
- $w=1101$
- $w=010001$

Show that a similar construction works for any $w\in \{0,1\}^*$.
<br>

### 3.
Is the language $L=\{a^{m}+ a^{n}=a^{m+n}\}$ over the alphabet $\{a,+,=\}$ regular?
(Here $a^{m}$ is ${aa\dots a}$ repeated $m$ times.)
<br>

### 4.
Given a language on a singleton alphabet, give a criterion that would determine if it is a regular language.
<br><br><br>

### 5.
For any languages $L_{1}$ and $L_{2}$ on alphabets $\Sigma_{1}$ and $\Sigma_{2}$, let $\Sigma=\Sigma_{1}\cup\Sigma_{2}$. 
Given a word $w$ over $\Sigma$, let: 
1. $\pi_{1}(w)$ be the word obtained from $w$ by deleting all the letter that are not in $\Sigma_{1}$
1.  $\pi_{2}(w)$ be the word obtained from $w$ by deleting all the letter that are not in $\Sigma_{2}$

If $L_{1}$ and $L_{2}$ are regular then:
- Given the <i>DFA</i>s for $L_1$ and $L_{2}$, if $\Sigma_{1}\cap \Sigma_{2}=\emptyset$ then design a <i>DFA</i> for $L=\{w\ |\ \pi_{1}(w)\in L_{1}, \pi_{2}(w)\in L_{2} \}$.
- Given the <i>NFA</i>s for $L_1$ and $L_{2}$ design an <i>NFA</i> for the above $L$.
<br>

### 6.
Give an algorithm to check if a given <i>NFA</i> accepts any words at all (i.e. its language is not empty). 
<br>

### 7.
Give an algorithm to check if a given <i>NFA</i>  accepts a word of even length.
<br>

### 8.
Given a regular language $L$ and its <i>DFA</i>:
- Find a <i>DFA</i> for $\text{Rev}(L)=\{w^{R}\ |\ w\in L\}$.
- Find a <i>DFA</i> for $\text{Pal}(L)=\{ww^{R}\ |\ w\in L\}$, or show that the language is not always regular.
---
 