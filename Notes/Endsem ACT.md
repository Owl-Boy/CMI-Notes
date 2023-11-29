BMC202107
Aditi Muthkhod
# 4. 
We prove that the set $\mathcal{C}$ contains the set $RM_{q}(2,d)$.
$RM_{q}(2,d)=\{ f: \mathbb{F}_{q}^{2}\to \mathbb{F}_{q}\ |\deg(f)\leq d \}\subseteq \mathbb{F}_{q}[X,Y]$.
In other words, it is the set of evaluations of all bivariate polynomials in $\mathbb{F}_{q}[X,Y]$ of total degree at most $d$ and individual degree at most $q-1$ over all points in $\mathbb{F}_{q}^{2}$.
$\mathcal{C}$, on the other hand, is the set of evaluations of all polynomials in $\mathbb{F}_{q}[X,Y]$ that satisfy property $P(d)$ (i.e. are in $\mathcal{F}$) over all points in $\mathbb{F}_{q}^{2}$.
So it suffices to prove that $\mathcal{F}\supseteq\{ f\ |\deg(f)\leq d \}=\mathcal{F'}$. (We can ignore the condition of having individual degree at most $d$ because when we evaluate these polynomials over $\mathbb{F}_{q}$, all the higher degree terms will reduce to degree at most $q-1$ since $a^{q}=a$.)
Any polynomial $p(X,Y)$ in $\mathcal{F'}$ is also in $\mathcal{F}$ because $p(X,Y)$ itself is of degree at most $d$.

In local correction of RM codes, say at coordinate $a\in \mathbb{F}_{q}^{2}$, we pick a random direction $b\in\mathbb{F}_{q}^{2}$ and look at the restriction of the received word to the line $L=\{ a+bt\ |\ t\in\mathbb{F}_{q} \}$. This gives us evaluations of the univariate polynomial $Q(T)=f(a+bT)\in\mathbb{F}_{q}[T]$ which is of degree at most $d<q$, and we can recover $Q(T)$ successfully.
For $\mathcal{C}$, the same argument follows through. Say the coordinate we want to locally decode at is $a\in\mathbb{F}_{q}^{2}$, we pick a random direction $b\in\mathbb{F}_{q}^{2}$ and look at the restriction of the received word to the line $L=\{ a+bt\ |\ t\in\mathbb{F}_{q} \}$. This gives us evaluations of the univariate polynomial $f(a+bT)\in\mathbb{F}_{q}[T]$. $L=l(T)=(b_{x}T+a_{x},b_{y}T+a_{y})$. If $f\in\mathcal{F}$, then $\exists g$ such that $f\equiv g$ (i.e has all the same evaluations) and $g$ has degree at most $d$. Let $Q(T)=g(a+bT)$ Hence we can recover $Q$, and evaluating $Q(T)$ at $T=0$ gives us the corrected value of $g(a)=f(a)$.

---

We can use the same decoding algorithm as that for RM codes, by reducing it to decoding RS codes.

# 5.
We have seen in class a basic list decoding algorithm.
For the root finding step to go through, we had $\deg(X,P(X))\leq \deg_{X}(Q)+(k-1)\deg_{Y}(Q)$, so we required $t>\deg(X,P(X))$, which is not tight because the highest degrees of $X$ and $Y$ might occur in different terms, which would lead to the slackness.
We can counter this by using the notion of weighted degree. We can require the $(1,(k-1))-$degree of $Q(X,Y)$ to be at most $\sqrt{ 2(k-1)n }$, where $(1,w)-$degree of $X^{i}Y^{j}$ is defined to be $i+wj$. We extend this as: the $(1,w)-$degree of a polynomial is the highest $(1,w)-$degree among all its monomials.
Now the same argument as earlier goes through, and we can pick values such that $t> \lceil \sqrt{ 2(k-1)n } \rceil$, which will give us an algorithm to decode from $1-\sqrt{ 2R }$ fraction of errors, or $n-\sqrt{ 2kn }$ errors.

So $M=\{ x^{i}y^{j}\ |\ i+(k-1)j\leq \sqrt{ 2(k-1)n } \}$.

---
# 6.
I think there's a typo in the question: $\gamma$ and $\delta$ should be interchanged. (Or maybe the definition of an expander graph is different.) I am assuming a $(c,d)-$regular $(\delta,\gamma)-$expander. Let $\gamma=(1-\epsilon)c$, so $\gamma> \frac{2c}{3} \implies\epsilon< \frac{1}{3}$.

(a)
Let the vertex added to $ERASE$ at the $i^{th}$ iteration be $i$. Define $E_{0}=\phi,E_{i}=E_{i-1}\cup \{ i \},i\geq 1$. Let there be $t$ iterations.

*FTSOC* $|E_{t}|>\delta n-1$. Let $i$ be the last iteration for which $|E_{i}|\leq\delta n$.

We have that $|N(E_{i})|\geq(1-\epsilon)c|E_{i}|$.

We obtain an upper bound on $|N(E_{j})|$ as follows:
Since $j$ was added to $E_{j-1}$, $|N(j)\cap UNHAPPY|\geq \frac{c}{3}$.
Any $k\in N(j)\cap UNHAPPY$ is either in $N(j)\cap N(E_{j-1})$, or in $N(j)\cap (U\setminus N(E_{j-1}))$.

So $|N(j)\cap UNHAPPY|=|N(j)\cap N(E_{j-1})|+|N(j)\cap (U\setminus N(E_{j-1}))|\geq \frac{c}{3}$.
Using this, we get
$$
\begin{align*}
|N(E_{i})|&=\sum\limits_{j=1}^{n}(|N(j)|-|N(j)\cap E_{j-1}|)\\
&\leq \sum\limits_{j=1}^{n}\left( c- \frac{c}{3}+|N(j)\cap U\setminus N(E_{j-1})| \right)\\
&\leq \frac{2c}{3}i +|U|.
\end{align*}
$$
This and, $|E_{i}|=i$, gives us
$$(1-\epsilon)c|E_{i}|\leq |N(E_{i})|\leq \frac{2c}{3}|E_{i}|+|U|.$$Or,
$$
\begin{align*}
(1-\epsilon)c|E_{i}|&\leq \frac{2c}{3}|E_{i}|+|U|\\
|E_{i}|c\left( \frac{1}{3}-\epsilon \right)&\leq |U|\\
&\leq c|ERRORS|\\
|E_{i}|&\leq \frac{|ERRORS|}{\frac{1}{3}-\epsilon}.
\end{align*}
$$
Since $|E_{i+1}|=|E_{i}|+1>\delta n$,
$|E_{i}|>\delta n-1$,
so $|ERRORS|>\left( \frac{1}{3}-\epsilon \right)(\delta n-1)$.
So we can pick $\tau=\left( \frac{1}{3}-\epsilon \right)\delta$, which would give a *contradiction* since $|ERRORS|$ is an integer.

---

(b)
Suppose *FTSOC* $ERRORS\not\subseteq ERASE$. Let $\tau=\delta$, so $|ERRORS|\leq\delta n$.
Let $O=ERRORS\setminus ERASE$.
$|O|<|ERRORS|\leq\delta n$.
So, $|N(O)|\geq |O|(1-\epsilon)c$.

> [!info] Any $(\delta,(1-\epsilon)c)-$expander is also a $(\delta,(1-2\epsilon)c)-$unique neighbour expander.

We get $|N^{1}(O)|\geq |O|(1-2\epsilon)c$.
By PHP, $\exists i\in O$ such that $|N^{1}(O)\cap N(i)|\geq(1-2\epsilon)c> \frac{c}{3}$.

**Claim:** $N^{1}(O)\cap N(i)\subseteq UNHAPPY$.
*Proof:* Pick any $j\in N^{1}(O)\cap N(i)$.
$j$ is not a neighbour of any vertex in $O$ other than $i$, because it is a unique neighbour of $O$. If it is a neighbour of some vertex in $ERASE$, then $j\in UNHAPPY$. Otherwise, $j$ is a neighbour of exactly one vertex in $ERRORS$, which means $j\in U\subseteq UNHAPPY$.

This gives us that $i$ has $> \frac{c}{3}$ neighbours in $UNHAPPY$, so $i$ should have been in $ERASE$, which is a *contradiction*.

Thus, $ERRORS\subseteq ERASE$.

---
Referred to Viderman's paper [Vid13a], and "Viderman's algorithm for quantum LDPC codes" by Krishna, Navon, and Wootters

---
# 7.
We want to check whether $Ay=0$. Let the rows of the matrix be $A_{0},\dots,A_{m-1}$. We can construct a degree $m-1$ polynomial as follows: $P(X)=\sum\limits_{i=0}^{m-1}A_{i}X^{i}$. Checking if $Ay=0$ is equivalent to checking if $P(X)\equiv 0$.
$\mathbb{F}_{q^{s}}$ contains $\mathbb{F}_{q}$ as a subfield. So we pick a random point $\alpha \in\mathbb{F}_{q^{s}}$, and check if $P(\alpha)=0$, which is the same as checking if $\sum\limits_{i=0}^{m-1}\left( \sum\limits_{j=1}^{n}y_{j}A_{i,j} \right)\alpha^{i}=0$.
Reordering the summations, we need to check if $\sum\limits_{j=1}^{n}y_{j}\left( \sum\limits_{i=0}^{m-1}A_{i,j}\alpha^{i} \right)=0$.
Since $\alpha^{i}$ and $A_{i,j}$ can be computed in $O(1)$, the inner summation can be computed in time $O(m)$ for each $j$. So on seeing $y_{j}$ we can calculate the required term, and store the sum, till the end. The algorithm uses at most $O(\log q+\log m+\log n)$ bits.

If $Ay=0$, the algorithm always returns "Zero!". If $Ay\not=0$, then the algorithm returns "Not Zero!" with probability at least $\frac{q^{s}-m+1}{q^{s}}$. We want $\frac{q^{s}-m+1}{q^{s}}\geq \frac{2}{3}$. So we can pick $s$ such that $q^{s}\geq 3(m-1)$, or $s\geq\log_{q}3(m-1)$.

---
Referred to "Data Stream Algorithms for Codeword Testing" by Atri Rudra, Steve Uurtamo.

---
# 8.
For $p(x)=(p_{1}(x),\dots,p_{m}(x))$, we can define $p_{i}(x)=\sum\limits_{j=0}^{m-1}\lambda_{i}^{q^{j}}x^{q^{j}}$, where $\lambda_{1},\dots,\lambda_{m}\in\mathbb{F}_{q^{m}}$ are linearly independent over $\mathbb{F}_{q}$. Since $|\mathbb{F}_{q}^{m}|=|\mathbb{F}_{q^{m}}|$, it suffices to show that $p(x)$ has image $\mathbb{F}_{q}^{m}$, which we can do by observing algebraic properties of the image of $p$, which will be a subspace of $\mathbb{F}_{q}^{m}$.
Let the received polynomial be $w$. $w:\mathbb{F}_{q}^{m}\to \mathbb{F}_{q}$. $w\circ p:\mathbb{F}_{q^{m}}\to \mathbb{F}_{q}$. We can look at $w\circ p$ as the received polynomial for the RS code $[q^{m},k]_{q^{m}}$, evaluated over all of $\mathbb{F}_{q^{m}}$. It can be shown that $k=rq^{m-1}+1=\deg(w\circ p)+1$ in this case.

(a)
Now we can use any of the RS decoding algorithms to get the corrected polynomial, say $g=w\circ p$. We get $w=g\circ p^{-1}$. Since we can evaluate $p^{-1}$ and $g$, we can correct the RM code. The RS code decoding algorithm can uniquely decode up to half its minimum distance i.e. up to $\frac{q^{m}-rq^{m-1}}{2}$, which also is half the minimum distance for the RM code. The RS code decoding algorithm is polytime $(O(q^{m})^{s}=O(n)^{s})$, and it is easy to check that the reduction is as well.

(b)
We can use the same algorithm as in part (a), and use the algorithm mentioned in question 4 for decoding the RS code. It will take $O(q)$ queries because we are restricting to a line. We can correct $\frac{1}{2}\left( 1-\frac{r}{q} \right)$ fraction of errors as shown above. So $\epsilon_{0}=\frac{1}{2}$ here.


---
