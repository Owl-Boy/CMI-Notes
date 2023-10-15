---
tags:
  - Note
  - Incomplete
---
202309251409

Tags : [[Lambda Calculus]], [[Type Theory]]

---
# $\lambda\mu-$Calculus

```ad-cite
title: History
Until around 1990, it was a common belief that there is no [[Curry Howard Isomorphism]] for **Classical Logic**. Timothy Griffin then discovered that $\lnot\lnot p\rightarrow p$ can be implemented in the typing of *Control Flow* 
```

```ad-info
title:Motivation
One of main uses of *Type Theory* is in *Static Analysis* for *Software Verification*. The process being, we have built the calculus in such a way that, it will correspond to some valid logical statement. 
Correspondingly, If a program *crashes*(which it cannot for $\lambda$-calculus, but say it does) and corresponds to a logical statement. A good way to interpret it would be that the statement if **False**. This is exactly the idea behind $\lambda\mu$ calculus, where we use control flow to model something like *try-catch*. We use the $\mu$ stuff where we guarantee that a statement is going to be false, hence safely giving it a negated type, and evaluating it can lead to elimination of double negation, and hence help us prove satements from classical logic.
```

*Types* are formulas of the form $\Phi(\rightarrow,\perp)$
*Variables* are of the from $x,y,z:\tau\in\Phi(\rightarrow,\perp)$
*Addresses* are of the form $a,b,c:\lnot\sigma\in\Phi(\rightarrow,\perp)$

The **Context-free grammar** for $\lambda\mu-$calculus is
$$
\begin{matrix}x & | & MN & | & (\lambda x^{\sigma}.M) & | & [a]M & | & \mu a^{\lnot\sigma}.M\end{matrix}
$$
We write $\varepsilon_\varphi(M)= \mu a:\lnot\varphi M$ where $a\notin \text{FV}(M)$ which represents $\perp$, but has $\varphi$ associated to it for type checking purposes.
 
The *Syntax* for the calculus is described by the following **Context-Free Grammar**

$$
\begin{align*}
&\Gamma, x:\sigma \vdash x:\sigma\\\\
\frac{\Gamma, x:\sigma \vdash M:\tau}{\Gamma\vdash(\lambda x:\sigma.M):\sigma\to\tau}&&\frac{\Gamma\vdash M:\sigma\rightarrow\tau\;\;\;\;\Gamma\vdash N:\sigma}{\Gamma\vdash (MN):\tau}\\\\
\frac{\Gamma, a:\lnot\sigma\vdash M:\perp}{\Gamma\vdash (\mu a:\lnot\sigma M):\sigma} && \frac{\Gamma, a:\lnot\sigma\vdash M:\sigma}{\Gamma, a:\lnot\sigma\vdash ([a]M):\perp}
\end{align*}
$$


---
# References
