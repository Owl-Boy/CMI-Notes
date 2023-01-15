# Homework 1
Name: Shubh Sharma
Roll Number: BMC202170

 ### 1
 For $f=u+i v$ to be analytic, $u, v$ have to satisfy the Cauchy-Reimann Eqations.
 $$
 \begin{aligned}
 \frac{\partial u}{\partial x} &= 2x\\
 \frac{\partial u}{\partial y} &= -2y\\
 \end{aligned}
 $$
 The Cauchy-Reimann Equations are
 $$
  {\partial u \over \partial x} = {\partial v \over \partial y}, {\partial u \over \partial y} = -{\partial v \over \partial x}
 $$
 So
 $$
 \begin{aligned}
 {\partial v\over \partial y}&= 2x \\
 {\partial v\over \partial x}&= 2y \\
 \implies v &= 2xy + c 
 \end{aligned}
 $$
 Hence 
 $$
 \begin{aligned}
 f(x+i y) &= (x^2-y^2)+ i(2xy + c)\\
 f(z) &= z^2 + ic & \text{where } c \in \mathbb R 
 \end{aligned}
 $$
 ### 2.
 **One way**
 If $f$ is differentiable as a complex function, then its derivative follow Cauchy Reimann Equation, then 
 $$
 \begin{equation}
 Df(x, y) = 
 \begin{pmatrix}\frac{\partial u}{\partial x} & \frac{\partial u}{\partial y} \\ -\frac{\partial u}{\partial y} & \frac{\partial u}{\partial x}\end{pmatrix}
 \end{equation}
$$
which is of the form 
$$
\begin{pmatrix}a & b \\ -b & a\end{pmatrix}
$$
which computes with any complex number $(x+iy)$ of the from 
$$
\begin{pmatrix}x & y \\ -y & x\end{pmatrix}
$$
as the product for the two matrices is 
$$
\begin{pmatrix}ax-by & ay+bx \\ -ay-ab & ax-by\end{pmatrix}
$$
**Converse**
If the derivative of $f$ commtues with multiplication with complex number $z=x+iy$
let the derivative of $f=Df$ be
$$\begin{pmatrix}a & b \\ c & d\end{pmatrix}$$
$$
\begin{align*}
Df\times z &= \begin{pmatrix}ax+cy & bx+dy\\
cx-ay & dx-by\\
\end{pmatrix}\\
z\times Df&= \begin{pmatrix}ax - by & ay+bx\\
cx-dy & cy+dx\end{pmatrix}
\end{align*}
$$
This implies $a = d$ and $b=-c$, hence the derivative is of the form
$$
\begin{pmatrix}a & b  \\  -b & a\end{pmatrix}
$$
which means it follows the Cauchy Reimann Inequality and hence complex function corresponding to $f$ will be Analytic. 
 ### 3.
 To Prove
 $$
 \Bigg|\sum\limits_{i=1}^{n}a_i\overline b_i\Bigg|^2\le\sum\limits_{i=1}^{n}|a_{i}|^{2}\sum\limits_{j=1}^{n}|b_{j}|^{2}
$$
consider the term $\sum\limits_{i=1}^{n}|a_{i}\overline b_{j}|$ , then 
by Triangle inequality
$$
\Bigg|\sum\limits_{i=1}^{n}a_{i}b_{j}\Bigg|^2\le\sum\limits_{i=1}^{n}\big|a_{i}\overline b_{j}\big|^2
$$
replacing the terms $a_i$ and $b_i$ with $|a_i|$ and $|b_i|$ in the vectors and using the cauchy inequality for real numbers gives 
$$
\sum\limits_{i=1}^{n}\big|a_{i}\overline b_{j}\big|^2\le\sum\limits_{i=1}^{n}|a_{i}|^2\sum\limits_{i=1}^{n}|b-i|
$$
which gives the desired inequality.
 ### 4.
 Let $f= u_1 + iv_1$ and $g = u_2 + iv_2$
 $$
 \begin{aligned}
 g\circ f &= u_2(u_1+iv_1) + iv_2(u_1+iv_2) \\
 {\partial (g\circ f)\over \partial x} &= {\partial u_2(f)\over \partial x}{(u_1' + iv_1')\over \partial x} + i{\partial v_2(f)\over \partial x}{(u_1'+iv_2')\over \partial x} \\
 &= \left(\frac{\partial u_2(f)}{\partial x}\cdot {\frac{\partial u_1}{\partial x}} - \frac{\partial v_2(f)}{\partial x}\cdot \frac{\partial v_1}{\partial x}\right)+i\left(\frac{\partial u_2(f)}{\partial x}\cdot {\frac{\partial v_1}{\partial x}} + \frac{\partial v_2(f)}{\partial x}\cdot \frac{\partial u_1}{\partial x}\right)\\
 {\partial (g\circ f)\over \partial y} &= {\partial u_2(f)\over \partial y}{(u_1' + iv_1')\over \partial y} + i{\partial v_2(f)\over \partial y}{(u_1'+iv_2')\over \partial y} \\
 &= \left(\frac{\partial u_2(f)}{\partial y}\cdot {\frac{\partial u_1}{\partial y}} - \frac{\partial v_2(f)}{\partial y}\cdot \frac{\partial v_1}{\partial y}\right)+i\left(\frac{\partial u_2(f)}{\partial y}\cdot {\frac{\partial v_1}{\partial y}} + \frac{\partial v_2(f)}{\partial y}\cdot \frac{\partial u_1}{\partial y}\right)\\
 \end{aligned}
 $$
letting
$$
\begin{align*}
\frac{\partial u}{\partial x}&= \left(\frac{\partial u_2(f)}{\partial x}\cdot {\frac{\partial u_1}{\partial x}} - \frac{\partial v_2(f)}{\partial x}\cdot \frac{\partial v_1}{\partial x}\right)\\
\frac{\partial v}{\partial x}&= \left(\frac{\partial u_2(f)}{\partial x}\cdot {\frac{\partial v_1}{\partial x}} + \frac{\partial v_2(f)}{\partial x}\cdot \frac{\partial u_1}{\partial x}\right)\\
\frac{\partial u}{\partial y}&= \left(\frac{\partial u_2(f)}{\partial y}\cdot {\frac{\partial u_1}{\partial y}} - \frac{\partial v_2(f)}{\partial y}\cdot \frac{\partial v_1}{\partial y}\right)\\
\frac{\partial v}{\partial y} &= \left(\frac{\partial u_2(f)}{\partial y}\cdot {\frac{\partial v_1}{\partial y}} + \frac{\partial v_2(f)}{\partial y}\cdot \frac{\partial u_1}{\partial y}\right)
\end{align*}
$$
Then by applying Cauchy Reimann Equation to the components, we can prove that $f\circ g$ also follows the Cauchy Reimann Equations, hence it is also analytic.
 
 ### 5.
 The solution to the first question verifies the Cauchy Reimann Equations for $f(z)=z^2$

 For $f(z)=z^3$ we can write $f$ as 
 $$
 \begin{aligned}
 f(x+iy)&=x^3 +3ix^2y - 3xy^2 - iy^3\\
 f(x+iy)&=(x^3 - 3xy^2) + i(3x^2y - y^3)\\
 \end{aligned}
 $$
 and let
 $$
 \begin{aligned}
 u&=x^3-3xy^2\\
 v&=3x^2y - y^3
 \end{aligned}
 $$
 Then
 $$
 {\partial u \over \partial x} = {\partial v \over \partial y} = 3x^2-3y^2
 $$
 And
 $$
 {\partial u \over \partial y} = -{\partial v \over \partial x} = -6xy
 $$
 Hence $f(z) = z^3$ follows the Cauchy Reimann Equations.
 ### 6.
 Since $ax^3 + bx^2y + cxy^2 + dy^3$ is harmonic
 $$\begin{aligned}
 6ax + 2by &= 0\\
 2cx+6dy &= 0
 \end{aligned}
 $$
 Hence $3a + c = 0$ and $b+3d = 0$
 Hence the cubic is of the form $ax^3  + 3dx^2y - 3axy^2 - dy^3$
 **Integration Method**
 For the conjugate harmonic function 
 $$
 \frac{\partial u}{\partial x}= 3ax^{2}+6dxy-3ay^2=\frac{\partial v}{\partial y} 
$$
Hence $v$ is of the form 
$$
v = 3ax^{2}y+ 3dxy^{2}- ay^{3}+f(x) 
$$
$$
\frac{\partial u}{\partial y}= 3dx^2-6axy-3dy^2=-\frac{\partial v}{\partial x}
$$
Hence $v$ is of the form
$$
v=-x^3+3a^2xy+3dxy^{2}+f(y)
$$
Hence 
$$
v=-dx^{3}+3ax^{2}+3dxy^{2}-ay^{3}
$$
**Formal Method**
$$
\begin{align*}
f(z)&= 2u\left(\frac{z}{2},\frac{z}{2i}\right)-u(0,0)+ic\\
u(0,0) &= 0\\
2u\left(\frac{z}{2},\frac{z}{2i}\right) &= a \frac{z^{3}}{8}+3b\frac {z^{3}}{8i}+3a\frac{z^{3}}{8}+b\frac{z^3}{8i}\\
\therefore f(z) &= z^{3}\left(a+\frac{b}{3i}\right)\\
\therefore f(z) &= ax^3  + 3dx^2y - 3axy^{2} - dy^{3}+i(-dx^{3}+3ax^{2}+3dxy^{2}-ay^{3})
\end{align*}
$$

 The conjugate harmonic of the equation of the following will be of the form $-dx^3 + 3ax^2y + 3dxy^2 - ay^3+K$ , because they follow the Cauchy Reimann Equations.
 ### 7.
 **FTSOC**
 Let $|f(z)| = c\ne 0$ be a function which has constant absolute value but is not constant value
 $$
 \begin{align*}
|f(z)|^{2}&=c^2\\
f(z)\overline{f(z)}&= c^2\\
\overline {f(z)} &= \frac{c^2}{f(z)}\\
\end{align*}
$$
Hence, $\overline {f(z)}$ is also analytic, so it follows the Cauchy Reimann Equations, comparing Cauchy Reimann Equations for $f(z)$ and $\overline{f(x)}$ is $u(x, y) = v(x, y) = 0$ where $f = u+iv$ and $\overline f = u -iv$, which means that the functions is constant, which is a contradiction, hence, if an analytic function has constant absolute value then it reduces to a constant number.
 ### 8.
 let $f(x+iy) = u(x,y) + iv(x, y)$
 then 
 $$
 \begin{align*}
\overline {f(\overline z)} &= u(x, -y) - iv(x, -y)\\
\frac{\partial \overline {f(\overline z)}}{\partial x}&= \frac{\partial u(x, -y)}{\partial x}- i\frac{\partial v(x, -y)}{\partial x}\\
\frac{\partial \overline f}{\partial y}&= -\frac{\partial u(x, -y)}{\partial y}+ i\frac{\partial v(x, -y)}{\partial y}\\
\end{align*}
$$
$f(z)$ is analytic $\iff$ $\overline {f(\overline z)}$ is analytic because they satisfy the Cauchy Reimann Equations together. 
 ### 9.
 $$
 \begin{align*}
u(z) &= a(x, y) + ib(x, y)\\
u \text{ is harmonic} &\implies v(x, y)=\frac{\partial^{2}u(x, y)}{\partial x^{2}} + \frac{\partial^{2}u(x, y)}{\partial y^{2}} = 0\\
\frac{\partial^2 u(\overline z)}{\partial x^{2}}&+\frac{\partial^2 u(\overline z)}{\partial y^{2}}=v(x, -y)=0\\
\therefore u(\overline z) &\text{ is also harmonic}\\
\end{align*}
$$$$
 
 