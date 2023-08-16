202308141408

Type : #Note
Tags : [[Logic]], [[Type Theory]]

---
# Natural Deduction
Natural Deductions is a simpler syntax for Intuitionistic logic. Natural deduction uses "Judgments" to prove statements

```ad-info
title:Judgements
Judgements are statements of the form
$$
\Gamma\vdash\phi
$$
Where $Gamma$ is a set of assumptions, $phi$ is the statement we need to prove and $\vdash$ can be read as "proves"
```

Natural deductions has the following rules
It has mainly two types of rules
- Rules that Introduce an operator (Labelled with $I$)
- Rules that use, or eliminate an operator (Labelled with $E$)

$$
\begin{align*}
\frac{}{\Gamma,\varphi\vdash\varphi}(Ax)\\\\

\frac{\Gamma,\varphi\vdash\psi}{\Gamma\vdash\varphi\to\psi}(\to\mathcal I) && \frac{\begin{matrix}\Gamma\vdash\varphi\to\psi &&  \Gamma\vdash\varphi\end{matrix}}{\Gamma\vdash\psi}\\\\

\frac{\begin{matrix}\Gamma\vdash\varphi&&\Gamma\vdash\psi\end{matrix}}
{\Gamma\vdash\varphi\land\psi}(\land\mathcal I) &&
\frac{\Gamma\vdash\varphi\land\psi}
{\Gamma\vdash\varphi}
(\land\mathcal E)
\end{align*}
$$

---
# References
[[P implies not-not P - Intuitionistic Logic]]