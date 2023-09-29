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

*Types* are formulas of the form $\Phi(\rightarrow,\perp)$
*Variables* are of the from $x,y,z:\tau\in\Phi(\rightarrow,\perp)$
*Addresses* are of the form $a,b,c:\lnot\sigma\in\Phi(\rightarrow,\perp)$

The **Context-free grammar** for $\lambda\mu-$calculus is
$$
\begin{matrix}x & | & MN & | & (\lambda x^{\sigma}.M) & | & [a]M & | & \mu a^{\lnot\sigma}.M\end{matrix}
$$
We write $\varepsilon_\varphi(M)= \mu a:\lnot\varphi M$ where $a\notin \text{FV}(M)$ which represents $\perp$, but has $\varphi$ associated to it for type checking purposes.
 
```ad-info
title:Try-Catch
Its Not possible to encode try-catch like procedure in Lambda Calculus, but here we try to use addresses to do just that. This is to encode `not` by just throwing a negative around it
```
```ad-warning
fix the above info block after class.
```

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
