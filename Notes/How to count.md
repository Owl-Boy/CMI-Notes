202305280005

Type : #Note
Tags : [[Enumerative Combinatorics]]

---
# How to count
**Enumerative Combinatorics** is mainly about counting the number of elements in a finite set. Usually in an infinite family of finite sets $S_i$ where $i$ ranges over some indexing set $I$. 

One of the ways to achive that is by finding a **counting function** $f(i):\mathbb N \to \mathbb N$ which returns the size of the $i^{th}$ set.

Some of the Standard ways to give a counting function are

1. **Closed Form**: ^8d213d
	1.  The nicest form and generally the most desired one, but one's preference towards this would decrease as the complexity of the formula decreases
	2.  _Ex:_ Number of subsets of $[n]$, its corresponding counting function would be $f(i)=2^{i}$
2.  **Recurrence Relation:**
	1. Where $f(i)$ is calculated based on smaller $f(i)$'s 
	2. _Ex:_ Number of subsets of $[n]$ That do not contain consecutive numbers gives $f(i) = f(i-1) + f(i-1)$ where $f(1)=2, f(2)=3$
3.  **Algorithm:**
	1.  This one subsumes a few other methods
	2. We need the algorithm to be effient, should require much less steps than $f(i)$ itself, otherwise is useless
4.  **Estimation by Asymptotic Functions:**
	1.  This one is prefferered when the solution to the first one is extremely ugly, which makes it in some sense better than the [[#^8d213d|Closed Form]]. 
	2. _Ex._ Something like $e^{-2} 36^{-n} (3n)!$ seems more useful than $$6^{-n} n!^{2}\sum \frac{(-1)^{\beta}(\beta+3\gamma)!2^{\alpha}3^{\beta}}{\alpha!\beta!\gamma!6^{\gamma}}$$For non negative $\alpha + \beta + \gamma = n$
	3. $f$ and $g$ are said to be aymptotic if $\lim\limits_{x\to\infty}\frac{f}{g}(x)=1$
5.  **Generating Function:**
	1.  Functions that can be written as a polynomial series where the coefficient of $x^n$ is $f(i)$ or $\frac{f(i)}{n!}$ 
	2.  *Ex:* For number of elements in $[n]$ gives the exponential generating function $F(x)=e^{x+1}$ 


---
# References
[[Generating Functions]]