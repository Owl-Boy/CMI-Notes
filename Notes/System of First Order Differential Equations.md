202301111201

Type : #Note
Tags : [[Differential Equations]]

---
# System of First Order Differential Equations
$$
\text{x bar raised to dot is fancy v bar(t, xbar)}
$$
$\overline x = (x_1,x_2, \dots, x_n)\in\mathbb R^n$ 
$\overline v:\Omega\to \mathbb R^n$ 
This is equivalent to solving $n$ differential equation for each dimentions
### n=1
This just becomes a single first order differential equation.
$$
{\partial x\over \partial t} = t
$$
### n=2
$$
\begin{aligned}
{\partial x_1\over \partial t} = x_1\\
{\partial x_2\over \partial t} = x_2\\
\end{aligned}
$$
This is an example of a decoupled system of differnetial eqautions since both the differential equations can be solved independently to get the $2$ components of the answer
### otherwise
**Proposition:** Any $n^{th}$ order differential equ
ation can be reduced to a system of $n$ first order differential equations.
**Proof:**
$$
x^{(n)}=F(t,x, x', x'',\dots,x^{(n-1)})
$$
where the $i^{th}$ derivative can be then written in terms of all $j^{th}$ derivatives where $j> i$.
This can be solved by succesively solving the differnetial equations from the last term tot he first term.

Systems that are not dependent on $t$ are called [[Autonomous System|autonomous systems]]

---
# Related Problems

---
# References
