# Complex Analysis Assignment 3
Name: Shubh Sharma
Roll Number: BMC202170

 ### 1. Map the common part of the disks $|z| < 1$ and $|z-1| < 1$ on the inside of the unit circle. Choose the mapping so that the two symmetries are preserved.

The two circles intersect at points $a= \frac{1}{2}+ \frac{\sqrt3i}{2}$ and $b= \frac{1}{2}- \frac{\sqrt3i}{2}$ , hence we can map these two points at $0$ and $\infty$ respectively by 
$$
f(z) = -\frac{z-a}{z-b}
$$
This makes a sector of angle $\frac{\pi}{3}$ passing through $f(0)=b$, $f(1)=a$ and $f\left(\frac{1}{2}\right) = 1$  
applying $$g(z) = z^\frac{3}{2}$$ considering a branch cut which makes it the half plane $Re(z) \ge 0$
and the map $$h(z) = \frac{z-1}{z+1}$$ sends it to the unit circle
The map $h\circ g\circ f$ takes the intersection of the two discs to the unit circle

 ---
  
 ### 2. Map the reigon between $|z|=1$ and $|z- \frac{1}{2}|=\frac{1}{2}$ on a half plane.
 The map $$f(z) = \frac{-i\pi z}{z-1}$$ to the strip $0\le Im(z)\le \pi$
 The map $$g(z)=e^{z}$$ sends the strip to the half plane $Im(z)>0$
 the map $g\circ f$ takes the reigon between the two circles to a half plane

---

 ### 3. map the complement of the arc $|z|=1, y\ge 0$ on the outside of the unit circle so that the points at infinity correspont to each other.
The map $$a(z) = -i\frac{z+1}{z-1}$$
this maps the the arc to the line $x\le0, y=0$, sending $\infty$ to $-i$
$$b(z)=\sqrt z$$
with the branch cut being the negative number real line, maps the points complement to the line on the half plane $Re(z)>0$ , sending $-i$ to $\frac{1}{\sqrt2}-\frac{i}{\sqrt2}$
The function $$
c(z) = i\frac{z-1}{z+1}
$$ maps the half plane onto the unit circle. sending $\frac{1}{\sqrt2}- \frac{i}{\sqrt2}$ to $\sqrt 2 -1$ 
The function 
$$
d(z) = \left(\sqrt 2 - 1\right)\cdot \frac{z+1}{1-z} 
$$
sends the circle to the right plane and send $\sqrt 2 -1$ to $1$
The function 
$$
e(x) = \frac{z+1}{z-1}
$$
Send the half plane to the complement of the circle and sends $1$ to $\infty$
Hence the function
$$e\circ d\circ c\circ b\circ a$$
sends the complement of the arc to outside the unit circle and sends $\infty$ to itself

---

 ### 4. Compute $$\int_{\gamma}xdz$$ where $\gamma$ is the directed line segment from $0$ to $i+1$
 Let $z(t)=t+it, t\in[0,1]$
 Then 
 $$
 \int_{\gamma}xdz = \int\limits_{0}^{1}x(z(t))\cdot z'(t)dt = \int\limits_{0}^{1}t(1+i)dt = \frac{1+i}{2}
$$

---

 ### 5. Compute $$\int_{z=|r|}xdz$$ for the positive sense in two ways, first by the use of parameters and second, by observing that $x = \frac{z+\overline z}{2}=\frac{1}{2}\left(z+ r^{2}{z}\right)$  on the circle
1. **Parameters**:
   $z(t) = re^{it},0\le t\le 2\pi$ 
   $z'(t)=ire^{it}$ 
   Hence
   $$
   \begin{align*}
   \int_{|z|=r}xdz &= \int\limits_{0}^{2\pi}x(z(t))\cdot z'(t)dt\\
   &= \int\limits_{0}^{2\pi}(r\cos t)(ir)(\cos t+i\sin t)dt\\
   &= r^{2}i\left(\int\limits_{0}^{2\pi}cos^{2}t\ dt + \int\limits_{0}^{2\pi}\sin t\cos t\ dt\right)\\
   &= \pi r^2i
   \end{align*}
$$
2. **Observation:**
   $f(z) = z$ is an analytic function, Hence the integral in a closed loop is $0$ thus
   $$
   \begin{align*}
   \int_{|z|=r}xdz &= \int_{|z|=r} \frac{r^{2}dz}{2z}\\
&= \frac{r^{2}}{2}\cdot 2\pi i = \pi i r^{2}
\end{align*}
$$
---

 ### 6. Compute $$\int_{|z|=2} \frac{dz}{z^{2}-1}$$ in the positive sense of the circle

  This is equal to 
  $$
  \begin{align*}
\frac{1}{2}\left(\int_{|z|=2} \frac{dz}{z-1}-\int_{|z|=2} \frac{dz}{z+1}\right)
\end{align*}
$$
for both the integral, the roots of the follwoing the linear polynimals, lie inside the loop, hence both of them evaluate to $2\pi i$ Hence the total integral evaluates to $0$.

---

 ### 7.
 ##### a)
 $n(\sigma_{1},x_{1})=0$, hence $n(\sigma_{1}, z)=0$ for $z\in\gamma_2$
 We know that $\sigma_1$ intersects the X-axis. Let $\sigma_1$ intersect the X-axis at $x'$ where $x'\ne 0$. Such that $x'$ is the rightmost intersection of $\sigma_{1}$ and X-axis.
 If $n(\sigma_{1}, x_{2})\ne 0, x_2$ lies in the interior of $\sigma_1$, hence $x_2<x'$ But this contradicts the fact that $x_2$ is the rightmost intersction of $\gamma_1$ with the X-axis.
 $\therefore n(\sigma_{1}, x_{2})=0$
 as $x_2\in\gamma_2$, for $z\in \gamma_2,n(\sigma_{1}, z)=0$ as $\gamma_2$ is a connected curve and $n$ is a continuous function, connected component get mapped to connected components. Image of $\mathbb N$ is singleton

 ##### b)
 $n(\sigma_{1},x)=n(\sigma_{2}, x)=1$ for small $x>0$.
 Let $x'$ be the point where $\gamma$ intersects X-axis for the first time. As $Im\ z_1<0$ and $Im\ z_2>0$ and subarc $z_{1}\to z_{2}$ passing through the origin. If $\sigma_1$ and $\sigma_{2}$ does not meet the X-axis at any point greater than $\frac{x'}{2}$ and the subarc $z_{1}\to z_{2}$ passing through $x'$ of $\gamma$ does not meet the X-axis at any point less than $\frac{x'}{2}, n(\sigma_{1}, \frac{x'}{2})=n(\sigma_{2}, \frac{x'}{2})=1$. As $x'>0, \frac{x'}{2}>0$
 ##### c)
 The first intersection of $x_1$ of the positive real axis with $\gamma$ lies on $\gamma_1$.
 If not, the first intersection $x_1$ of the positive real axis with $\gamma$ lies on $\gamma_2$.
 $Im\ z_1<0$ and $Im\ z_2>0$, the subarc $z_{1}\to z_{2}$ whcih $\gamma_1$ does not meet the X-axis at any point less than $x_1$ and the subserc $z_{1}\to z_{2}$ of $\sigma_1$passing through the origin does not meet the X-axis at any point greater than $x_{1}$   $\therefore n(\sigma_{1},x_1)=1$
 But if $x_1\in\gamma_2,n(\sigma_1,x_1)=0$ which is a contradiction
 $\therefore$ the first intersection $x_1$ of the positive real axis  with $\gamma$ lies on $\gamma_2$
 ##### d)
 $n(\sigma_{2},x_2)=1$, hence $n(\sigma_2,z)=1$ for $z\in\gamma_1$
 $Im\ z_1<0$ and $Im\ z_2>0$, the subarc $z_{1}\to z_{2}$ of $\sigma_2$ which $\gamma_{2}$ does not meet the X-axis at any point less than $x_1$ and the subarc $z_{1}\to z_{2}$ of $\sigma_2$ which passes through the origin does not meet the $x$ axis at any point greater than $x_1$, $\therefore n(\sigma_{2},x_{1})=1$
 $\therefore n(\sigma_{2},z)=1$, for $z\in \gamma_{1}$ as it is connected and $n$ is a continuous function, $n(\sigma_2,z)$ is connected $\forall z\in\gamma_{1}$ and hence a singleton image of $\mathbb N$

---
 ### 8. Compute $$\int_{|z|=1} \frac{e^{z}}{z}dz$$
$e^z$ is an analytic function, and by cauchy's integral formula
$$
e^{0}= 1=\frac{1}{2i\pi}\int_{|z|=1} \frac{e^{z}}{z-0}dz
$$
Thus the integral computes to $2i\pi$

---
 
 ### 9. Compute $$\int_{|z|=2} \frac{dz}{z^{2}+1}$$ by decomposing the integrand in partial fraction
$$
\begin{align*}
\int_{|z|=2} \frac{dz}{z^{2}+1} &= \frac{1}{2i}\left(\int_{|z|=2} \frac{dz}{z-i}-\int_{|z|=2} \frac{dz}{z+i}\right)\\
\end{align*}
$$
as $i$ and $-i$ both lie in the interior of $|z|=2$
$$\int_{|z|=2} \frac{dz}{z+i} = \int_{|z|=2} \frac{dz}{z-i}$$
Hence 
$$\int_{|z|=2} \frac{dz}{z^{2}+1}=0$$

---

 ### 10 Compute $$\int_{|z|=\rho} \frac{|dz|}{|z-a|^{2}}$$ under the condition that $|a| \ne \rho$
 $$
 \begin{align*}
\int_{|z|=\rho} \frac{|dz|}{|z-a|^{2}}&= -i\rho\int_{|z|=\rho} \frac{dz}{z(z-a)(\bar z - \bar a)}\\
&= -i\rho\int_{|z|=\rho} \frac{dz}{(z-a)(\rho^{2}-\bar a z)}\\
&= \frac{i\rho}{\bar a}\int_{|z|=\rho} \frac{dz}{(z-a)\left(z-\frac{\rho^{2}}{\bar{a}}\right)}\\
&= \frac{i\rho}{|a|^{2}-\rho^{2}}\left(\int_{|z|=\rho} \frac{dz}{z-a}-\int_{|z|=\rho} \frac{dz}{z-\frac{\rho^{2}}{\bar{a}}}\right)\\    
a<\rho&\implies \int_{|z|=\rho} \frac{dz}{z-a}=2\pi i, \int_{|z|=\rho} \frac{dz}{z- \frac{\rho^{2}}{\bar{a}}}=0\\
a>\rho&\implies \int_{|z|=\rho} \frac{dz}{z-a}=0, \int_{|z|=\rho} \frac{dz}{z- \frac{\rho^{2}}{\bar{a}}}=2\pi i\\
\text{Thus }\int_{|z|=\rho} \frac{|dz|}{|z-a|^{2}} &= \frac{2\pi\rho}{\rho^{2}-|a|^{2}}\\
&= \frac{2\pi\rho}{|a|^{2}-\rho^{2}}
\end{align*}
$$

---
 
 ### 11. Compute $$\begin{align*}\int_{|z|=1} e^{z}z^{-n}dz,\ \ \ \ \ \ \int_{|z|=2}z^{n}(1-z)^{m}dz,\ \ \ \ \ \ \int_{|z|=\rho} |z-a|^{-4}|dz|\ (|a|\ne\rho)\end{align*}$$
**Part 1**:
$$\int_{|z|=1} e^{z}z^{n}dz= \frac{2i\pi}{(n-1)!}e^{z}\Bigg|_{z=0} = \frac{2i\pi}{(n-1)!}$$

**Part 2:**
If $n, m>0$
since $z^n$ and $(1-z)^{m}$ are analytic, the integral evalutes to $0$
If $n<0$ and $m>0$
$$
\begin{align*}
\int_{|z|=2} \frac{(1-z)^{m}}{z^{|n|}}dz &= \frac{2i\pi}{(n-1)!} \frac{d^{|n|-1}}{dz^{|n|-1}}(1-z)^{m}\Bigg|_{z=0}=2i\pi(-1)^{|n|-1}{m \choose |n|-1} 
\end{align*}
$$ 
If $n > 0$ and $m<0$, similarly we get
$$
\int_{|z|=2} \frac{z^{n}}{(1-z)^{|m|}}dz = 2i\pi(-1)^{m}{n\choose |m| -1}
$$
**Part 3:**
$$I=\int_{|z|=\rho} \frac{|dz|}{|z-a|^{4}}= \frac{-i\rho}{a^{2}}\int_{|z|=\rho} \frac{zdz}{(z-a)^{2}(z-\rho^{2}{a^{2})^{2}}} $$
if $|a|<\rho$ then $1/(z- \frac{\rho^{2}}{a^{2}})$ is analytic and
$$
I=\frac{-i\rho}{a^{2}} \frac{2i\pi}{1!} \frac{d}{dz}\left(\frac{z}{z-\frac{\rho^{2}}{a^{2}}}\right)\Bigg|_{z=a}
$$
The derivative evalutates to 
$$
\frac{d}{dz}\left(\frac{z}{\left(z-\rho^{2} /a^{2}\right)}\right)= a^{2}\frac{\rho^{4}-a^{4}}{(az-\rho^{2})^{4}}
$$
hence the integral evalueates to
$$I=2\pi\rho\frac{a^{2}+\rho^{2}}{(\rho^{2}-a^{2})^{3}}$$
Similarly if $|a|>\rho$
$$I=2\pi\rho\frac{a^{2}+\rho^{2}}{(a^{2}-\rho^{2})^{3}}$$


---

 ### 12. Prove that a function which is analytic in the whole plane and satisfies the inequality $|f(z)|<|z|$ for some $n$ and all sufficiently large $|z|$ reduces to a polynomial
 $$
 \begin{align*}
|f^{(n+1)}(a)| &\le \left|\frac{(n+1)!}{2i\pi}\int_{|z|=r} \frac{f(z)dz}{(z-a)^{n+2}}\right| &\le \frac{(n+1)!}{2\pi}\int_{|z|=r} \frac{|f(z)|dz}{|z-a|^{n+2}}\\
&< \frac{(n+1)!}{2\pi}\int_{|z|=r} \frac{|z|^{n}dz}{|z-a|^{n+2}} &<   \frac{(n+1)!}{2\pi}\int_{|z|=r} \frac{r^{n}dz}{|r-a|^{n+2}}\\
&\le \frac{(n+1)!r^{n}}{2\pi(r-a)^{n+2}}\int_{|z|=r}|dz| &= \frac{(n+1)!r^{n}}{(r-a)^{n+2}}\\
\text{As }r\to\infty&, \frac{(n+1)!r^{n}}{(r-a)^{n+2}}\to0
\end{align*}
$$
Hence $f^{(n+1)}=0$, thus $f$ is a polynomial of degree upto $n$.

---

 ### 13. If $f(z)$ is analytic and $|f(z)|\le M$ for $|z|\le R$, find and upper bound for $f^{(n)}(z)$ in $|z|\le\rho< R$
$$
\begin{align*}
|f^{(n)}(a)|&= \left|\frac{n!}{2i\pi}\int_{|z|=R} \frac{f(z)dz}{(z-a)^{n+1}}\right|\\
&\le \frac{n!}{2\pi}\int_{|z|=R} \frac{|f(z)||dz|}{|z-a|^{n+1}}\\
&\le \frac{n!M}{2\pi}\int_{|z|=R} \frac{|dz|}{|z-a|^{n+1}}  \\
&\le \frac{n!MR}{(R-a)^{n}}
\end{align*}
$$

---

 ### 14. If $f(z)$ is analytic for $|z|<1$ and $|f(z)|\le \frac{1}{1-|z|}$, find the best estimate of $|f^{(n)}(0)|$ that Cauchy Inequality will yield.
 $$
 \begin{align*}
|f^{(n)}(0)| &= \left|\frac{n!}{2i\pi}\int_{|z|=R} \frac{f(z)dz}{z^{n+1}} \right|\\
&\le \frac{n!}{2\pi} \int_{|z|=R} \frac{|f(z)||dz|}{|z|^{n+1}}\\
&= \frac{n!}{R^{n}(1-R)}\\
\text{On minimizing by setting } R&= \frac{n}{n+1}\\
|f^{(n)}(0)| &\le (n+1)!\left(1+ \frac{1}{n}\right)^{n}
\end{align*}
$$

---

### 15. Show that successive derivatives of an analytic function at a point can never satisfy $|f^{(n)}(z)|>n!n^{n}$. Fromulate a sharper theorem of the same kind
$$
\begin{align*}
|f^{(n)}(z)| &= \frac{n!}{2\pi} \int_{|z|=R} \frac{|f(z)||dz|}{|z-a|^{n+1}} &\le \frac{n!M}{R} \text{ where }M=\sup\limits_{|z|=R}|f(z)|\\
\end{align*}
$$
$M$ exists as $f$ is continuous adn $|z|=R$ is compact
if $f^{(n)}(z) >n!n^n$ then $\frac{n!M}{R}> n!n^n$ hence $\frac{M}{R}>n^{n}$ which is a contradictoin. 
 
