# Complex Analysis Homework 2
Name: Shubh Sharma
Roll Number: BMC202170

## Page 47
 ### 1. 
 $$
 \sin z = z - \frac{z^{3}}{3!}+ \frac{z^{5}}{5!}-\cdots,\;\;\cos z = 1- \frac{x^{2}}{2!}+ \frac{x^{4}}{4!}-\cdots
$$
To show:
$$
S_k(z)=\sin z - \sum\limits_{i=0}^{k}(-1)^{i} \frac{z^{2i+1}}{(2i+1)!},\;\;\;C_k(z)=\cos z - \sum\limits_{i=0}^{k} (-1)^{i} \frac{z^{2i}}{(2i)!}
$$
have the same sign as $(-1)^{k+1}$
Inducting on $n$, which is the term in the considered series with the highest degree.
**Base case:** The condititon is clear for $n = 1,0$ 
**Induction Hypothesis:** The condition if true for all $n\in\{1,2,3,\cdots n-1\}$
**Induction Step:** 
_If $n(2k+1)$ is odd:_ By the induction hypothesis, $C_k(z)$ satisfies the condition, by integrating it over $[0,z]$ we get that $S_k(z)$ also satisfies the condition.
_If $n(2k)$ is even:_ By the induction hypothesis, $S_{k-1}(z)$ satisfies the condition, by integrating it over $[0,z]$ we get $-C_k(z)$ has the same sign as $(-1)^k$ hence $C_{k}(z)$ has the same sign as $(-1)^{k+1}$.
This completes the Induction.
 ### 2. 
 $$
 \begin{align*}
 3<\pi<2\sqrt3\\
\end{align*}
$$
$$
\cos z = 1 - \frac{z^{2}}{2!} + \frac{z^{4}}{4!}-\cdots
$$
Hence $\cos r$ is real if $r$ is real. 
also $\sin^{2}z+\cos^{2}z = 1$
Hence for all real $z$, $-1\le \sin z, \cos z \le 1$ 
Derivative of $x-\sin x$ is $1-\cos x$ which is always greater than or equal to $0$, and since $\sin 0 = 0$, $\sin x < x\forall x>0$ 
Hence 
$$\sin \frac{\pi}{6}=\frac{1}{2}\implies \frac{1}{2}<\frac{\pi}{6}\implies 3<\pi$$
From the previous question, we can say that 
$$
\sin x \le x - \frac{x^{3}}{3!}+ \frac{x^{5}}{5!}- \frac{x^{7}}{7!}+ \frac{x^{9}}{9!}
$$
putting $2\sqrt 3$ in the above polynomial returns a negative number. Hence $\sin 2\sqrt3 <0$ so there is a root $c_0\in[0,2\sqrt 3]$, and $c_0$ is hence and integral multiple of $\pi$ , thus $\pi\le c_0\le2\sqrt3$
 ### 4.
 $$
 \begin{align*}
e^{z}&= k\\
\log(k) &= \log(|k|)+i\arg(k)\\

\text{For } k&= 2\\
z&= \log(2) + 2ni\pi\\

\text{For } k&= -1\\
z&=  i\pi+ 2ni\pi\\

\text{For } k&= i\\
z&= \frac{i\pi}{2} + 2ni\pi\\

\text{For } k&= \frac{-i}{2}\\
z&= \log\left(\frac{1}{2}\right) + \frac{i3\pi}{2} +2ni\pi\\

\text{For } k&= -1-i\\
z&= \log\left(\sqrt2\right)+ \frac{i5\pi}{8} + 2ni\pi\\

\text{For } k&= 1+2i\\
z&= \log\left(\sqrt5\right) + i\arctan\left(\frac{2}{\sqrt5}\right)  + 2ni\pi\\

\end{align*}
$$
 ### 6.
 $$
 \begin{align*}
2^{i}&= (e^{\log 2})^{i}=e^{i\log(2)}=\cos(\log 2)+i\sin(\log 2)&\\
i^{i}&= (e^{\frac{i\pi}{2}+2in\pi})^{i}=e^{\frac{-\pi}{2}+2n\pi}&\\
(-1)^{i}&= (e^{\log -1})^{i}=e^{\pi+2n\pi}\\
\end{align*}
$$
 ### 7.
 $$
 \begin{align*}
z^{z}&=e^{z\times\log z}\\
&=e^{z\times(\log(|z|)+i\arg(z))}\\
&= e^{Re(z)\cdot\log(|z|)-Im(z)\cdot(\arg(z)+2n\pi)}\cdot e^{i(Re(z)\cdot(\arg(z)+2m\pi)+Im(z)\cdot\log(z))}\\
&= e^{Re(z)\cdot\log(|z|)-Im(z)\cdot(\arg(z)+2n\pi)}\cdot e^{i(Re(z)\cdot\arg(z)+Im(z)\cdot\log(z))}\\

\end{align*}
$$
 ### 9.
 Let the triangle be formed by $3$ complex numbers $a,b,c$. let $m= \frac{a+b+c}{3}$ let $f(z) = \frac{z-m}{a}$.
 Since $f$ is conformal, the angle between $2$ lines does not change, hence the "angles of a trianlge" do not change
 If $Im(b')>0$:
   let angles 
   $$
 \begin{aligned}
   A=\arg(c'-a')-\arg(b'-a')\\
   B=\arg(a'-b')-\arg(c'-b')\\
   C=\arg(b'-c')-\arg(a'-c')\\
 \end{aligned}
   $$
   where $a' = f(a), b' = f(b), c' = f(c)$ 
   Then $A+B+C = \arg(b'-c')-\arg(c'-b') + \arg(c'-a')-\arg(a'-c')+\arg(a'-b')-\arg(b'-a')$
   Thus $A+B+C = -\pi + \pi + \pi = \pi$
## Page 72
 ### 1. 
 The domain for a single valued branch of $\sqrt z$ is the complement of $\{x : x\in\mathbb R, x\le0\}$, hence for $\sqrt {1+z}$ the domain would be $\{x:x\in\mathbb R, x\le-1\}$ and for $\sqrt {1-z}$ the domain would be $\{x:x\in\mathbb R, x\ge1\}$ Hence, for the function $f(z) = \sqrt {1+z}+\sqrt {1-z}$ the domain would be the intersection of two which is $\{x+iy:x,y\in\mathbb R, y\ne 0\}\cup\{x:x\in\mathbb R, -1\le x\le1\}$ 
 ### 3.
 if $Re\ f(z) = 0$ then $f(z)=iy$ and $|f(z)^2-1|<1$ implies $|-y^2-1|<1$ which is false for all $y\in\mathbb R$ hence $Re\ f(z)$ is never zero in the domain. Since the domain is connected $Re\ f(z)$ is either greater than $0$ or less than $0$ in the entire domain.
 
## Page 78
 ### 1.
 __FTSOC:__ If there exists a transformation, let that be 
 $$
 \overline z = \frac{az+b}{cz+d}
$$
$\overline 0 = 0$ hence $b=0$
if $r\in\mathbb R, \overline r = r$
$$
\begin{align*}
r &= \frac{ar}{cr+d}\\
cr^{2}&= (a-d)r\\
cr &= a-d
\end{align*}
$$
which is a contradiction, hence such a linear transformation does not exist
 ### 2.
 If a linear transform is represented in the following way
 $$
 Tz= \frac{az+b}{cz+d}=\begin{bmatrix}a & b \\ c & d\end{bmatrix}
$$
Then composition of maps will correspond to multiplication of matrices
$$T_1=\begin{pmatrix}1 & 2 \\ 1 & 3\end{pmatrix}$$
$$T_2=\begin{pmatrix}1 & 0 \\ 1 & 1\end{pmatrix}$$
$$T_1^{-1}=\begin{pmatrix}3 & -2 \\ -1 & 1\end{pmatrix}$$
Then 
$$T_1T_{2}= \begin{pmatrix}1 & 2 \\ 1 & 3\end{pmatrix}\begin{pmatrix}1 & 0 \\ 1 & 1\end{pmatrix} = \begin{pmatrix}3 & 2 \\ 4 & 3\end{pmatrix}$$
$$T_1T_{2}= \begin{pmatrix}1 & 0 \\ 1 & 1\end{pmatrix}\begin{pmatrix}1 & 2 \\ 1 & 3\end{pmatrix} = \begin{pmatrix}1 & 2 \\ 2 & 5\end{pmatrix}$$
$$T_1^{-1}T_{2}= \begin{pmatrix}3 & -2 \\ -1 & 1\end{pmatrix}\begin{pmatrix}1 & 0 \\ 1 & 1\end{pmatrix} = \begin{pmatrix}1 & -2 \\ 0 & 1\end{pmatrix}$$
Hence 
$$
\begin{matrix}T_{1}T_{2}z= \frac{3z+2}{4z+3} & T_{2}T_{1}z= \frac{z+2}{2z+5} & T_{1}^{-1}T_{2}z= z-2\end{matrix}
$$
 ### 3.
$|az -  aw| = |a||z-w| = |z=w|$ if $|a|=1$ Hence rotation preserves distances.
Since distance is preserved $|z| = |Tz|$. Hence all points of a circle of radius $r$ around $0$ will remain on the cirlcle.
Let $a = T1$ 
Let $b = Tz$ for some $z\in \mathbb C$
$| \frac{b}{a} |= |z|$
and $|z-1| = \left| \frac{b}{a} - \frac{a}{a}\right| = \left| \frac{b}{a}-1\right|$  
Since the distance from $0$ and $1$ is the same for the points $z$ and $\frac{b}{a}$,  $\frac{b}{a}= z$ or $\frac{b}{a}=\overline z$ .
Hence the transformation followed by a rotation that sends 1's image to 1 sends all points to themselves or thier relfection in the real number line. 
Let that transformation be $T'z = \frac{Tz}{T1}$ 
For non real numbers $a=x+iy, b=z+iw$ and $T'a=\overline a$ 
Since $T'$ is distance preserving 
$$
\begin{align*}
|a-b| &= |Ta - Tb|\\
|(x-z)+i(y-w)| &= |(x-z)+i(-y-w')|
\end{align*}
$$
is true if and only if $y-w = -y-w'$ where $w' = w$ or $-w$ and for  $w,y\ne 0$ the statement is true iff $w' = -w$ or $T'b=\overline b$
Hence if one of the points goes to its mirror image, all points go to their mirror image. so $T'$ is either identity or reflection about the real number line.
any such $T$  can be obtained by following $T'$ with a rotation that maps $1$ to $T1$.
Hence the most general distance preserving transformations are identitiy or relfection about the real numberline followed by a rotation.
If the transfomation is relfection followed by rotation, it maps $r\cdot e^{i\theta}$ to $r\cdot e^{-i\theta+i\alpha}$ which can be rewritten as $r\cdot e^{-(i\theta-i\alpha)}$ which is rotation by $-\alpha$ followed by reflection.
Hence any transformation that preserves distances is of the form, a rotation followed by identity or reflection along the real number line.
 ### 4.
 Let the transformation be 
 $$Tz'= \frac{a'z+b'}{c'z+d'}$$
 If $a'\ne 0$
divide the numerator and denominator by  $|a'|^2$
 $$
 Tz = \frac{z+b}{cz+d}
$$
putting $z=0$ we get $b/d$ is real and taking the sequence of natural numbers $Tz$ converges to $\frac{1}{c}$ Hence $c$ is also real.

Taking $b=x+iy$ and $z=-x$ we get 
$$T(-x)= \frac{iy}{(-cx+kx)+kiy}$$
Which is real iff $c=k$ so 
$$
Tz = \frac{z+b}{cz+cb}=1/c
$$
otherwise, 
if $c=rd$ where $r$ is real we get
$$
Tz = \frac{b}{d(rz+1)} = \frac{b/d}{rz+1}
$$
which would make $\frac{b}{d}, r, 1$ real
otherwise,
We can find real numbers $a$ and $b$ such that they would make the real and imaginary parts of the denominator $0$ respectively. Hence To make the fraction always real, we $b$ would have to be both real and imaginary so $T(z)=0$.