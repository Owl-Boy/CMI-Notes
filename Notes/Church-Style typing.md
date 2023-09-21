202308282208

Type : #Note
Tags : [[Lambda Calculus]], [[Type Theory]]

---
# Church-Style typing
## Orthodox Church Style
In Church's original system. Typing rules were built into the term formulation rules.

![[Pasted image 20230828220644.png|500]]

## Modern Church Style
The set $\Lambda_{\Pi}$ of all typed lambda calculus terms of Curry style are given by the following grammar:
$$
\begin{matrix}\Lambda_{\Pi} & ::= & V & | & (\lambda x:\Pi .\Lambda_{\Pi}) & | & (\Lambda_{\Pi}\ \Lambda_{\Pi})\end{matrix}
$$

^111a8d

where $V$ is the set of all Variables and $\Pi$ is the set of all input types.

The set of typability relation $\Vdash$ on $C\times\Lambda_{\Pi}\times\Pi$ are
![[Simply Typed Lambda Calculus Syntax#^f1c6a3]]

Then the triple $(\Lambda_{\Pi},\Pi,\Vdash)$ is the lambda calculus

Examples:
$$
\begin{align*}
\mathbf{I} &:= \lambda x:\sigma.x &&:\sigma\to\sigma\\
\mathbf{K} &:= \lambda x:\sigma.\lambda y:\tau.x &&:\sigma\to\tau\to\sigma\\
\mathbf{S} &:= \lambda x:\sigma\to\tau\to\theta.\lambda y:\sigma\to\tau.\lambda z:\sigma.xz(yz) &&:(\sigma\to\tau\to\theta)\to(\sigma\to\tau)\to\sigma\to\theta
\end{align*}
$$

^acb5f4

---
# References
