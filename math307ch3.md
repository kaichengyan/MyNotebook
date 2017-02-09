
# Intro to Differential Equations

## Chapter 3: Second order linear DEs

From the first lecture, we know these equations can be written as $F(t,y,y',y'')=0$, where $F$ is linear:

$$a_0(t)y''+a_1(t)y'+a_2(t)y+b(t)=0,a_0\neq 0$$

Equivalently, we can write is as: 

$$y''+p(t)y'+q(t)y=g(t)$$

* This is called "homogeneous" if $g(t)=0$, so we have $y''+p(t)y'+q(t)y=0$. 
* This is called "constant coefficient" if $p(t), q(t)$ are constant, so we can write it as $ay''+by'+cy=g(t)$.
* The initial value problem needs two conditions: $y(t_0)=y_0,y'(t_0)=y_0'$. 

In chapter 3, we basically study constant coefficient 2nd order linear DEs. Section 3.1-3.4 are for homogeneous equations; Section 3.5-3.6 are for non-homogeneous equations; Section 3.7-3.8 are for applications. 

### 3.1 Homogeneous equation with constant coefficients

$$ay''+by'+cy=0(*)$$

We look for solutions of the form $y=e^{rt}(**)$, where $r$ is a constant. To find $r$, we plug $(**)$ into $(*)$.

$$\begin{align}
a(e^{rt})''+b(e^{rt})'+ce^{rt}&=0\\
ar^2e^{rt}+bre^{rt}+ce^{rt}&=0\\
e^{rt}(ar^2+br+c)&=0\\
ar^2+br+c&=0
\end{align}$$

$ar^2+br+c=0$ is called the characteristic equation. To find $r$, we have 3 cases. 

$$\Delta=b^2-4ac
\begin{cases}
\gt 0 \implies \text{(3.1) 2 real solutions } \frac{-b\pm\sqrt{\Delta}}{2a}\\
=0 \implies \text{(3.4) 2 repeated real solutions } -\frac{b}{2a}\\
\lt 0 \implies \text{(3.3) 2 complex solutions } \frac{-b\pm i\sqrt{-\Delta}}{2a}
\end{cases}$$

Suppose we have 2 distinct real roots $r_1,r_2$ for the characteristic equation, then we have 2 solutions $y_1=e^{r_1t}, y_2=e^{r_2t}$ for $ay''+by'+cy=0$. It is easy to verify that $y=c_1e^{r_1t}+c_2e^{r_2t}$ is also a solution for any $c_1, c_2$. This is called the general solution. 

**Example** Find the general solution of $y''-7y'+10y=0$.

Characteristic equation: $r^2-7r+10=0$. Roots: $r_1=2, r_2=5$. So we have $y_1=e^{2t}, y_2=e^{5t}$. Thus we have the general solution: $y=c_1e^{2t}+c_2e^{5t}$.

**Example** 

**1. Find the solution to the initial value problem $y''+5y'+6y=0, y(0)=2, y'(0)=3$.**

Characteristic equation: $r^2+5r+6=0\implies r_1=-2, r_2=-3$. The general solution: $y=c_1e^{-2t}+c_2e^{-3t}$. 

We use the initial values to find $c_1, c_2$. 

$$y'(t)=-2c_1e^{-2t}-3c_2e^{-3t}$$

\begin{cases}
y(0)=2 &\implies 2=c_1+c_2\\
y'(0)=3 &\implies 3=-2c_1-3c_2
\end{cases}

Solve for $c_1, c_2$. 

\begin{cases}
c_1=9\\
c_2=-7
\end{cases}

$$\implies y=9e^{-2t}-7e^{-3t}$$

**2. Determine $\lim_{t \to \infty}y(t)$.**

Note that 

$$\lim_{t\to\infty}e^{rt}=
\begin{cases}
+\infty, r>0\\
1, r=0\\
0, r<0
\end{cases}$$

Notice that the general solution is a combination of $e^{rt}$. So $\lim_{t\to\infty}y(t)=0$.

**3. Find the maximum of $y(t)$.**

Set $y'(t)=0$. Find the critical point. 

\begin{align} y'(t)=-18e^{-2t}+21e^{-3t}&=0\\
\frac{21}{18}&=e^{t}\\
t&=\ln\frac{21}{18}\\
t&=\ln\frac{7}{6}\\
\end{align}

So the maximum is achieved at $t=\ln\frac76$, and the value is $y(\ln\frac76)$.

### 3.2 Solutions to linear homogeneous DEs

We consider non-constant coefficient DEs: 

$$y''+p(t)y'+q(t)=0$$

#### Existence and uniqueness of solutions

> **Theorem 3.2.1** Consider IVP $y''+p(t)y'+q(t)y=g(t), y(t_0)=y_0, y'(t_0)=y_0'$. If $p(t)$, $q(t)$ and $g(t)$ are all continuous on interval $I$ containing $t_0$, there's a unique solution for the IVP on $I$. 

**Example** Find the largest interval for which solution is defined: $(t^2-3t)y''+ty'-(t+3)y=0, y(1)=2, y'(1)=1$. 

$$y''+\frac{1}{t-3}y'-\frac{t+3}{t^2-3t}y=0$$

The answer is $(0,2)$.

#### Principle of superposition

> **Theorem 3.2.2** If we have two solutions $y_1,y_2$ for equation $y''+p(t)y'+q(t)y=0$, then the linear combination $y=c_1y_1+c_2y_2$ is also a solution for any $c_1, c_2$. 

#### General solution (Wronskian)

Consider IVP $y''+p(t)y'+q(t)y=0, y(t_0)=y_0, y'(t_0)=y_0'$. If $y_1,y_2$ are solutions as in Theorem 3.2.2, can we find a solution $y=c_1y_1+c_2y_2$ with proper $c_1$ and $c_2$? 

TO find $c_1, c_2$, we find two equations from the initial condition. 

\begin{align}
y(t_0)=y_0 &\implies y_0=c_1y_1(t_0)+c_2y_2(t_0), (1)\\
y'(t_0)=y_0' &\implies y_0'=c_1y_1'(t_0)+c_2y_2'(t_0), (2)
\end{align}

Use Crammer's rule (from 308). 

\begin{align}
(1)\times y_1' &\implies y_0y_1'=c_1y_1(t_0)y_1'+c_2y_2(t_0)y_1', (1)\\
(2)\times y_1 &\implies y_0'y_1=c_1y_1'(t_0)y_1+c_2y_2'(t_0)y_1, (2)
\end{align}

$$y_0'y_1-y_0y_1'=c_2y_2'y_1-c_2y_2y_1'\\
\text{if } y_2'y_1-y_2y_1'=0 (*), \\
\text{then } c_2=\frac{y_0'y_1-y_0y_1'}{y_2'y_1-y_2y_1'}.$$

$(*)$ can be written as 
\begin{vmatrix}
        y_1 & y_2 \\
        y_1' & y_2' \\
\end{vmatrix}

For $y_1, y_2$, the determinant 

$$W=\begin{vmatrix}
        y_1 & y_2 \\
        y_1' & y_2' \\
\end{vmatrix}$$

is called the Wronskian of $y_1, y_2$. 

> **Theorem 3.2.4** If $y_1, y_2$ are solutions to the equation $y''+p(t)y'+q(t)y=0$, the IVP $y(t_0)=y_0, y'(t_0)=y_0'$ has a unique solution given by $y=c_1y_1+c_2y_2$ if and only if the Wronskian $W[y_1, y_2](t_0)\neq 0$. 
$y=c_1y_1+c_2y_2$ is called the general solution, and $\{y_1, y_2\}$ is called the fundamental set of solutions. 

**Example** Find the Wronskian of $y_1=e^{at}, y_2=e^bt$.

$W[y_1,y_2]=(b-a)e^{(a+b)t}$. $W\neq 0$as long as $b\neq a$. 

Remark: This corresponds to 3.1, where $a,b$ are different solutions of the characteristic equation. 

**Example** Show that $y_1=\sqrt t, y_2=\frac 1t$ form a fundamental set of solutions to $2t^2y''+3ty'-y=0, t>0$.

1. Need to check $y_1, y_2$ are solutions. 
2. Check Wronskian is non-zero. 

$$W[y_1,y_2]=
\begin{vmatrix}
t^{\frac 12} & t^{-1}\\
\frac 12 t^{-\frac 12} & -t^{-2}\\
\end{vmatrix}\neq 0$$

1+2 $\implies y_1,y_2$ form fundamental set of solution. 

#### Compute the Wronskian

> **Theorem 3.2.7 (Abel's Theorem)** If $y_1, y_2$ are solutions of $y''+p(t)y'+q(t)y=0$ where $p(t)$ and $q(t)$ are continuous on $I$, then $W[y_1,y_2](t)=Ce^{-\int p(t)dt}$. 

Note: The Wronskian is either 0 for all $t\in I (C=0)$ or never 0 $(C\neq 0)$. 

**Example** Find the Wronskian of the equation $2t^2y''+3ty'-y=0, t>0$. 

$$y''+\frac{3t}{2t^2}y'-\frac{1}{2t^2}y=0\\
W[y_1,y_2]=Ce^{-\int \frac{3}{2t}dt}=Ct^{\frac{3}{2}}$$

### 3.3 Complex Roots of the Characteristic Equation

Consider $ay''+by'+cy=0$. The characteristic equation is $ar^2+br+c=0$. If $\Delta=b^2-4ac<0$, the equation has two complex roots $r=\frac{-b \pm i\sqrt{-\Delta}}{2a}$. We write $r_1=\lambda +i\mu, r_2=\lambda -i\mu$,  where $\lambda=-\frac b{2a}, \mu=\frac{\sqrt{-\Delta}}{2a}$.

Two complex solutions to the DE is $y_1=e^{(\lambda+i\mu)t}, y_2=e^{(\lambda-i\mu)t}$. 

We need to understand $e^{it}$. Use Euler's formula $e^{it}=\cos t+i\sin t$, we have complex value solutions for the DE: $y_1(t)=e^{\lambda t}(\cos \mu t + i\sin \mu t)$, $y_2(t)=e^{\lambda t}(\cos \mu t - i\sin \mu t)$. 

Use the superposition principle, $\tilde{y_1}=\frac{y_1+y_2}{2}=e^{\lambda t}\cos\mu t$, $\tilde{y_2}=\frac{y_1-y_2}{2i}=e^{\lambda t}\sin\mu t$. 

$\tilde{y_1}, \tilde{y_2}$ are real valued solutions. $W[\tilde{y_1}, \tilde{y_2}]=\mu e^{2\lambda t}\neq 0$ since $\mu \neq 0$. So the general solution in this case is 

$$y=c_1e^{\lambda t}\cos \mu t+c_2e^{\lambda t}\sin \mu t$$ 

(where $\lambda=-\frac{b}{2a}, \mu=\frac{\sqrt{-\Delta}}{2a}$).

**Example** Solve $y''+y'+\frac{37}{4}y = 0, y(0)=2, y'(0)=8$. 

The characteristic equation $r^2+r+\frac{37}{4}. $ $\Delta=36<0$. 

\begin{align}
r_1=-\frac{1}{2}+3i&, r_2=\frac{1}{2}-3i \\
\lambda=-\frac{1}{2}&, \mu=3
\end{align}

The general solution is 
\begin{align}
y&=c_1e^{-\frac 12 t}\cos 3t+c_2e^{-\frac{1}{2}t}\sin 3t \\
&= e^{-\frac 12 t}(c_1\cos 3t + c_2\sin 3t)
\end{align}

To find $c_1, c_2$, use the initial conditions. 

\begin{align}
y(0)&=c_1+0=2\\
\because y'(t)&=-\frac 12e^{-\frac 12 t}(c_1\cos 3t + c_2\sin 3t) + e^{-\frac 12 t}(-3c_1\sin 3t + 3c_2\cos 3t)\\
& = -\frac{1}{2}y(t)+e^{-\frac 12 t}(-3c_1\sin 3t + 3c_2\cos 3t). \\
&\implies 8=-1+3c_2 \\ 
&\implies c_2=3 \\
\end{align}

The solution is $y=e^{-\frac 12 t}(2\cos 3t + 3\sin 3t)$. The graph oscillates and decays to 0. 

**Example** Solve the equation $y''+9y=0$. 

$\lambda=0, \mu=3$. So the general solution is $y=c_1\cos 3t + c_2\sin 3t$. The graph of the solution is like a sine wave. 