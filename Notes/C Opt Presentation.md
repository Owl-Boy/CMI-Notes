---
tags:
  - Note
  - Incomplete
title: The matching polytope has exponential extension complexity
theme: white
height: "900"
bg: white
---
<grid drop="2 10" drag="95 35" style="font-family:'lato',sans-serif;background-color:#FFFFFF;border-radius:8px!important;padding:auto;align:center;">
## The matching polytope has exponential extension complexity<!-- .element style="font-family:'Montserrat'; font-size:1.2em;color:#000000;" -->
</grid>

<grid drop="0 70" drag="100 30" style="line-height:0.6em;" align="top">
Thomas Rothvoss<!-- .element style="font-family:'lato';font-size:1.1em;font-weight:500;line-height:0.6;color:#111111!important;vertical-align:bottom!important;" -->

Presented by Rohan Goyal and Aditi Muthkhod, CMI<!-- .element style="font-family:'Montserrat'; font-size:0.8em;color:#616161;vertical-align:top;font-weight:400;" -->

Combinatorial Optimisation 2024, Course presentation <!-- .element style="font-family:'Montserrat'; font-size:0.8em;color:#616161;vertical-align:top;font-weight:400;" -->
</grid>
---
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Rectangle covering for matching<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Recall $S_{U,M}=|\delta(U)\cap M|-1$.

> [!note] Observe: Rect-cov-num (matching polytope) $\leq O(n^{4})$.

![[Pasted image 20240424132249.png]]

note: Part 1 (10-15 minutes):
- Remind non-negative rank defn with rectangles: 2 minutes
- Rectangle covering for perfect matching polytope: 4 minutes
- Covering with n^4 rectangles: 3 minutes
- Need for alternate method: 3 minutes
- Intuition:  (U, M) with M ∩ δ(U) = {e1, . . . , ek} lies in k^2 rectangles : 3 minutes

--
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Rectangle covering for matching<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Recall $S_{U,M}=|\delta(U)\cap M|-1$.

> [!note] Observe: Rect-cov-num (matching polytope) $\leq O(n^{4})$.

![[Pasted image 20240424132206.png]]
- For $e_{1},e_{2}\in E$:

note: Part 1 (10-15 minutes):
- Rectangle covering for perfect matching polytope: 4 minutes
- Covering with n^4 rectangles: 3 minutes
- Need for alternate method: 3 minutes
- Intuition:  (U, M) with M ∩ δ(U) = {e1, . . . , ek} lies in k^2 rectangles : 3 minutes

--
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Rectangle covering for matching<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Recall $S_{U,M}=|\delta(U)\cap M|-1$.

> [!note] Observe: Rect-cov-num (matching polytope) $\leq O(n^{4})$.

![[Pasted image 20240424132107.png]]
- For $e_{1},e_{2}\in E$: take $\{ U\mid e_{1},e_{2} \in\delta(U) \}$

note: Part 1 (10-15 minutes):
- Rectangle covering for perfect matching polytope: 4 minutes
- Covering with n^4 rectangles: 3 minutes
- Need for alternate method: 3 minutes
- Intuition:  (U, M) with M ∩ δ(U) = {e1, . . . , ek} lies in k^2 rectangles : 3 minutes

--
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Rectangle covering for matching<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Recall $S_{U,M}=|\delta(U)\cap M|-1$.

> [!note] Observe: Rect-cov-num (matching polytope) $\leq O(n^{4})$.

![[Pasted image 20240424132009.png]]
- For $e_{1},e_{2}\in E$: take $\{ U\mid e_{1},e_{2} \in\delta(U) \} \times \{ M\mid e_{1},e_{2}\in M \}$

note: Part 1 (10-15 minutes):
- Rectangle covering for perfect matching polytope: 4 minutes
- Covering with n^4 rectangles: 3 minutes
- Need for alternate method: 3 minutes
- Intuition:  (U, M) with M ∩ δ(U) = {e1, . . . , ek} lies in k^2 rectangles : 3 minutes

--
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Rectangle covering for matching<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Recall $S_{U,M}=|\delta(U)\cap M|-1$.

> [!note] Observe: Rect-cov-num (matching polytope) $\leq O(n^{4})$.

![[Pasted image 20240424131903.png]]
- For $e_{1},e_{2}\in E$: take $\{ U\mid e_{1},e_{2} \in\delta(U) \} \times \{ M\mid e_{1},e_{2}\in M \}$
- $(U,M)$ with $M\cap\delta(U)=\{ e_{1},\dots,e_{k} \}$ lies in $k \choose 2$ rectangles

note: Part 1 (10-15 minutes):
- Need for alternate method: 3 minutes
- Intuition:  (U, M) with M ∩ δ(U) = {e1, . . . , ek} lies in k^2 rectangles : 3 minutes

--
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Rectangle covering for matching<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Recall $S_{U,M}=|\delta(U)\cap M|-1$.

> [!note] Observe: Rect-cov-num (matching polytope) $\leq O(n^{4})$.

![[Pasted image 20240424131903.png]]
- For $e_{1},e_{2}\in E$: take $\{ U\mid e_{1},e_{2} \in\delta(U) \} \times \{ M\mid e_{1},e_{2}\in M \}$
- $(U,M)$ with $M\cap\delta(U)=\{ e_{1},\dots,e_{k} \}$ lies in $k \choose 2$ rectangles
![[Pasted image 20240424132912.png]]

note: Part 1 (10-15 minutes):
- Need for alternate method: 3 minutes
- Intuition:  (U, M) with M ∩ δ(U) = {e1, . . . , ek} lies in k^2 rectangles : 3 minutes

--
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Rectangle covering for matching<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Recall $S_{U,M}=|\delta(U)\cap M|-1$.

> [!note] Observe: Rect-cov-num (matching polytope) $\leq O(n^{4})$.

![[Pasted image 20240424131903.png]]
- For $e_{1},e_{2}\in E$: take $\{ U\mid e_{1},e_{2} \in\delta(U) \} \times \{ M\mid e_{1},e_{2}\in M \}$
- $(U,M)$ with $M\cap\delta(U)=\{ e_{1},\dots,e_{k} \}$ lies in $k \choose 2$ rectangles

> [!question] Does every rectangle covering over-cover entries of large slack?

note: Part 1 (10-15 minutes):
- Need for alternate method: 3 minutes
- Intuition:  (U, M) with M ∩ δ(U) = {e1, . . . , ek} lies in k^2 rectangles : 3 minutes

--
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Rectangle covering for matching<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Recall $S_{U,M}=|\delta(U)\cap M|-1$.

> [!note] Observe: Rect-cov-num (matching polytope) $\leq O(n^{4})$.

![[Pasted image 20240424131903.png]]
- For $e_{1},e_{2}\in E$: take $\{ U\mid e_{1},e_{2} \in\delta(U) \} \times \{ M\mid e_{1},e_{2}\in M \}$
- $(U,M)$ with $M\cap\delta(U)=\{ e_{1},\dots,e_{k} \}$ lies in $k \choose 2$ rectangles

> [!question] Does every rectangle covering over-cover entries of large slack?
> YES!

note: Part 1 (10-15 minutes):
- Need for alternate method: 3 minutes
- Intuition:  (U, M) with M ∩ δ(U) = {e1, . . . , ek} lies in k^2 rectangles : 3 minutes

---
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Hyperplane separation lower bound<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Frobenius inner product: $\langle W,S \rangle:= \sum_{i}\sum_{j}W_{ij}S_{ij}$

> [!example] Lemma
> Pick $W:\langle W,R \rangle\leq\alpha\ \forall$ rectangles $R$.

![[Pasted image 20240424133738.png]]

note:
- Frobenius: 1 minute
- Lemma: 6 minutes
- Show W that works and how <W,S>=1: 2.5 minutes
- Magic Lemma: 2.5 minutes
- Conclude: 2-3 minutes

--
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Hyperplane separation lower bound<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Frobenius inner product: $\langle W,S \rangle:= \sum_{i}\sum_{j}W_{ij}S_{ij}$

> [!example] Lemma
> Pick $W:\langle W,R \rangle\leq\alpha\ \forall$ rectangles $R$. Then $rk_{+}(S)\geq \frac{\langle W,S \rangle}{\| S \|_{\infty}.\alpha}$

![[Pasted image 20240424134256.png]]

note:
- Lemma: 6 minutes
- Show W that works and how <W,S>=1: 2.5 minutes
- Magic Lemma: 2.5 minutes
- Conclude: 2-3 minutes

--
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Hyperplane separation lower bound<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->
- Frobenius inner product: $\langle W,S \rangle:= \sum_{i}\sum_{j}W_{ij}S_{ij}$

> [!example] Lemma
> Pick $W:\langle W,R \rangle\leq\alpha\ \forall$ rectangles $R$. Then $rk_{+}(S)\geq \frac{\langle W,S \rangle}{\| S \|_{\infty}.\alpha}$

- Proof: Write $S=\sum_{i=1}^{r}R_{i}$ with $rk_{+}(R_{i})=1$. Then
$\langle W,S \rangle=\sum\limits_{i=1}^{r}\| R_{i} \|_{\infty}.\underbrace{\left\langle  W,\frac{R_{i}}{\| R_{i} \|_{\infty}}  \right\rangle}_{\leq\alpha} \leq\alpha.\sum\limits_{i=1}^{r}\| R_{i} \|_{\infty}\leq\alpha r\| S \|_{\infty}$.

![[Pasted image 20240424134350.png]]

note:
- Lemma: 6 minutes
- Show W that works and how <W,S>=1: 2.5 minutes
- Magic Lemma: 2.5 minutes
- Conclude: 2-3 minutes

---
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Applying the Hyperplane bound<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->

> [!example] Lemma
> Pick $W:\langle W,R \rangle\leq\alpha\ \forall$ rectangles $R$. Then $rk_{+}(S)\geq \frac{\langle W,S \rangle}{\| S \|_{\infty}.\alpha}$

- Recall $S_{UM}=|\delta(U)\cap M|-1$
- $Q_{l}:=\{ (U,M)\mid |\delta(U)\cap M| =l \}$
- The following choice of $W$ works!
![[Pasted image 20240424140058.png]]
- Then $\langle W,S \rangle=0+2-1=1$.

> [!example] Magic Lemma: For $k$ large, any rectangle $R$ has $\langle W,R \rangle\leq 2^{-\Omega(n)}$.

note: 
- Show W that works and how <W,S>=1: 2.5 minutes
- Magic Lemma: 2.5 minutes
- Conclude: 2-3 minutes

---
<!-- .slide style="font-size:0.7em;font-family:'Cantarell';" -->
## Open problem<!-- .element style="font-size:1.2em;font-family:'Cantarell';" -->

> [!tip] Show that there is no small SDP representing the Correlation/TSP/matching polytope!

Thank you for your attention!