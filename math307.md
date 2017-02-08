
# Intro to Differential Equations

## Chapter 2: First order DEs

### 2.1 First order linear DEs

Multiply both sides of DE $y'+p(t)y=g(t)$ by the integration factor: $\mu (t)=\exp{\int p(t)dt}$. Then we have $(\mu(t)y)'=g(t)\mu(t)$. Integrate both sides to find $y$.

### 2.2 Separable DEs

$f(y)dy=g(t)dt$. Integrate both sides to find $y$.

### 2.3 Applications

Key ingredient: derivatives = rate of change

#### Falling object (2.3 HW: 20, 21, 26)
Newton’s 2nd law: $F=ma$, specially, $G=mg, g=9.8m/s^2$.
**Example** Consider object of $m=10kg$ falling from the top of a building of height $h=100m$. Then the object is subject to gravity and air resistance, which is proportional to the velocity of the object with constant: $f=\gamma v, \gamma=2 kg/s$. 

1)	Find the differential equation for the velocity $v$ of the object. 
2)	Assume that the object is initially at rest. Find the velocity at time $t=1s$. 
3)	Find the height of the object at time $t=1s$.

$F=ma \implies \frac{dv}{dt}=\frac{mg-\gamma v}{m}$. 

Integration factor $\mu=e^{\frac{t}{5}}$. 

$$
\begin{align}
\because \frac{dh}{dt}&=v(t) = 49 - 49{e^{ - \frac{t}{5}}}\\
\therefore h(t) &=  - \int vdt \\
&=  - 49t - 49 \times 5 \times {e^{ - \frac{t}{5}}} + C \\
&= C - 245{e^{ - \frac{t}{5}}} - 49t.\\\\
h(0) &= C - 245 = 100 \Rightarrow C = 345,\\
\therefore h(t) &= 345 - 49t - 245{e^{ - \frac{t}{5}}}\\\\
\therefore h(1) &= 95.345({\rm{m}})
\end{align}$$

 
#### Mixing problem (2.3 HW: 3, 4)
Example A tank which holds 1000 L contains initially 400 L of water in which 50 kg of salt is dissolved. Fluid is coming in at a rate of 30 L/min, and it contains 0.3 kg/L salt. The tank drains at 10 L/min. How much salt is in the tank when the water level reaches the top? 

Let $Q(t)$ be the amount of salt in kg at time $t$ in min. 

\begin{align}
\frac{{dQ}}{{dt}} &= {r_{in}}{\rho _{in}} - {r_{out}}{\rho _{out}} \\
&= 30 \cdot 0.3 - 10\frac{Q}{V} \\
&= 9 - \frac{{10Q}}{{400 + 20t}} \\
&= 9 - \frac{Q}{{40 + 2t}}.
\end{align}

#### Newton’s Law of Cooling

$$\frac{dT}{dt}=k(T-T_s)$$

#### Compound Interest
Suppose that a sum of money is deposited in a bank that pays interest at an annual rate of $r$. Let $s(t)$ be the value of the investment at time $t$. Suppose the interest is compounded continuously and let a constant $k$ be the number of dollars to be deposited every year. 

$\frac{{ds}}{{dt}} = rs + k$. If there's withdrawal of money, change model to $\frac{{ds}}{{dt}} = rs - k$.

**Example** One is paying \$30,000 in car loans. The interest rate is 5%, annually compounded continuously. How much should he pay each-year to pay off the loan in 10 years (aka find $k$)?

Let $s(t)$ be the amount due at time $t$. 

$$\frac{{ds}}{{dt}} = rs - k = 0.05s - k$$

### 2.4 Differences between linear and non-linear equations

We consider the existence and uniqueness of solutions of the initial value problem 
$$\frac{dy}{dt}=f(t,y), y(t_0)=y_0$$

#### Linear equations, i.e. $\frac{dy}{dt}+p(t)y=g(t)$.

> **Theorem 2.4.1** Consider first order linear equation $y'+p(t)y=g(t)$. If $p(t)$ and $g(t)$ are continuous on the open interval $I=(\alpha, \beta)$ containing $t_0$, then there is a unique solution $y=\varphi(t)$ for the initial value problem $y(t_0)=y_0$ and $\varphi(t)$ is defined on $I$. 

**Example** Determine an interval in which the solution of $(4-t^2)y'+2ty=3t^2, y(-3)=1$ is certain to exist and unique. 
$$y'+\frac{2t}{4-t^2}=\frac{3t^2}{4-t^2}$$
The two functions $p(t)$ and $g(t)$ are continuous if $t\neq\pm2$. The intervals are $(-\infty, -2), (-2,2),(2,+\infty)$. $\because -3\in(-\infty,-2),\therefore (-\infty, -2)$.

#### General Case

> **Theorem 2.4.2** Consider equation $\frac{dy}{dt}=f(t,y),y(t_0)=y_0$. If $f(t,y)$ and $\frac{\partial f(t,y)}{\partial y}$ are continuous on rectangle $(\alpha, \beta)\times (\gamma, \delta)$, there is a unique solution $y=\varphi(t)$ defined on a smaller interval $(t_0-h,t_0+h), h>0$. 

**Example** Determine how the interval of definition depends on the initial value $y_0$ for $y'=-\frac{4t}{y},y(0)=y_0,y_0\neq0$.

First, solve the separable equation.

$$
\begin{align}
\int ydy &= \int -4tdt\\
y^2&=-4t^2+C\\
y&=\pm\sqrt{-4t^2+C}, -4t^2+C\geq 0
\end{align}$$

Next, use $y(0)=y_0$ to find $C$. 

$$y_0=\pm\sqrt{C} \implies C=y_0^2$$

So the solution is $y=\pm\sqrt{y_0^2-4t^2}$. It is defined on $t\in(-\frac{|y_0|}{2}, \frac{|y_0|}{2})$, where the solution exists. 

What happened to $y_0=0$? $y'$ is not defined, so no solution for $y_0=0$. 

**Example** (a) Verify that $y_1(t)=1-t$ and $y_2(t)=-\frac{t^2}{4}$ are solutions to $y'=\frac{-t+\sqrt{t^2+4y}}{2},y(2)=-1$. Determine where the solutions are valid. (b) Explain why the existence of two solutions does not contradict theorem 2.4.2. 

(a) Plug in the solutions to the original equation, and see if the left and right sides are equal. 

For $y_1$, 
$$\begin{align}
\text{LHS}&=y_1'=-1\\
\text{RHS}&=\frac{-t+\sqrt{t^2-4t+4}}{2}\\
&=\frac{-t+|t-2|}{2}\\
&=
\begin{cases} 
-1 & (t\geq 2)\\
-t+1 & (t < 2)
\end{cases}
\end{align}$$

So, $y_1$ is a solution when $t\geq2$. Similarly, $y_2$ is a solution on $\mathbb{R}$.

(b) Draw the graph of the two solutions. Theorem 2.4.2 does not apply here because $f_1(t, y) = \frac{-t+\sqrt{t^2+4y}}{2}$ is not continuous at $(2, -1)$.

### 2.5 Autonomous Equations and Population Dynamics

> **Definition** Equations of form $\frac{dy}{dt}=f(y)$ is called autonomous ($f(y)$ does not depend on $t$ explicitly). 

> **Definition** Equilibrium solutions of $\frac{dy}{dt}=f(y)$ are constant solutions $y(t)=C$, such that $f(C)=0$.

Consider the stability of equilibrium solutions. We assume $f(y)$ and $\frac{\partial f}{\partial y}$ are continuous, so that Thm 2.4.2 holds (no solution crosses the equilibrium solution). Let $y(t)=C$ be the equilibrium solution. 

1. $y(t)=C$ is asymptotically stable if nearby solutions approaches $C$ as $t \to \infty$. 
2. $y(t)=C$ is asymptotically unstable if solutions does not approach to $C$ as $t \to \infty$.
3. $y(t)=C$ is semi-stable if solution approaches to $C$ from one side as $t \to \infty$.

To determine the stability type, we can essentially use direction fields. This is simple if we use the **phase line**. 

**Example** Find the equilibrium solution of $\frac{dy}{dt}=y^2-6y+5$. Determine the stability type for each equilibrium solution. 

Find the equilibrium solution from $f(y)=0$: $y_1=1,y_2=5$. 

We have two equilibrium solutions: $y_1(t)=1, y_2(t)=5$.
To determine the stability type, we draw a rough graph of $f(y)$. 
$\frac{dy}{dt}>0$ when $y>5$ or $y<1$. $\frac{dy}{dt}<0$ when $1<y<5$. 

From the phase line, $y_2(t)=5$ is unstable, $y_1(t)=1$ is stable. 

**Example** Consider $\frac{dy}{dt}=(2-y)(y-5)^2$. Determine the stability type. 

Equilibrium solutions: $y_1(t)=2, y_2(t)=5$.

$\frac{dy}{dt}>0$ when $y<2$, $\frac{dy}{dt}<0$ when $2<y<5$ or $y>5$. 

From the phase line, $y_1(t)=2$ is stable, $y_2=(5)$ is semi-stable. 

**Application: Population Dynamics**

Let $y(t)$ be the population of a given species at time $t$.

1. The exponential growth model: Assume variation of population is proportional to the current population, i.e. $\frac{{dy}}{{dt}}=ry$, where $r$ is a constant. If $y(0)=y_0$, $y(t)=y_0e^{rt}$, which grows exponentially. 

2. The logistic growth model: Assume that the growth rate $r$ depends on $y$, say $r=h(y)$. $\frac{{dy}}{{dt}}=h(y)y$. Further, we assume $h(y)=r(1-\frac{y}{k})$. This is the logistic model. 

$$\frac{dy}{dt}=r(1-\frac{y}{k})y$$

Question: for $y(0)=y_0$, determine the population as $t \to \infty$.

Solution: Equilibrium solutions $y_1=0, y_2=k$. If $y<0$, the slope is negative. If $0<y<k$, the slope is positive. If $y>k$, the slope is negative. From the phase line, we can see that $y_2(t)=k$ is a stable solution. The population approaches to $k$ as $t \to \infty$.

### 2.6 Exact Equations

Consider equations of the form $M(x, y) + N(x, y)\frac{dy}{dx} = 0 (*)$. This is called "exact" if there is a function $\psi(x, y)$ such that 

$$\frac{d}{dx}\psi(x, y) = M(x, y) + N(x, y)\frac{dy}{dx}(**)\\
\frac{\partial \psi}{\partial x}=M(x, y), \frac{\partial \psi}{\partial y}=N(x, y)$$

How to tell if an equation is exact? 

> **Theorem 2.6.1** $(*)$ is exact if $\frac{\partial M}{\partial y}=\frac{\partial N}{\partial x}$.Then we know there is a function $\psi(x,y)$ so that $(**)$ (from Fubini's theorem).

**Example** Determine if equation $\frac{dy}{dx}=\frac{x+3y}{y^2-3x}$ is exact. 

$M(x,y)=x+3y, N(x,y)=3x-y^2$. $\because \frac{\partial M}{\partial y}=\frac{\partial N}{\partial x}=3$, $\therefore$ exact. 

**Example** Find the general solution of $x+y^2\frac{dy}{dx}=0$. 

$\frac{\partial M}{\partial y}=\frac{\partial N}{\partial x}=0$, so exact. 

$$\begin{cases} 
\frac{\partial \psi}{\partial x} &=x \\
\frac{\partial \psi}{\partial y} &=y^2
\end{cases}\\
\begin{align}
\psi(x, y)&=\int xdx + h(y)\\
&= \frac{x^2}{2}+h(y)
\end{align}\\
\because \frac{\partial \psi}{\partial y} =y^2=\frac{dh}{dy}\\
\therefore h(y)=\frac{y^3}{3}+C\\
\therefore \psi(x, y)=\frac{x^2}{2}+\frac{y^3}{3}+C\\
\because \frac{d\psi}{dx}=0\\
\therefore \psi(x, y)=C'$$

Therefore, the solution is $\frac{x^2}{2}+\frac{y^3}{3}=C$.

**Example** Find the solution of 

$$(y\cos x+2xe^y)+(\sin x+x^2e^y-1)\frac{dy}{dx}=0$$

$\frac{\partial M}{\partial y}=\frac{\partial N}{\partial x}=\cos x + 2xe^y$, so exact. 

$$\begin{align}
\because \frac{\partial \psi}{\partial x} &= M(x, y) = y\cos x+2xe^y \\
\therefore \psi(x, y)&=\int M(x, y)dx + h(y)\\
&= y\sin x+x^2e^y+h(y)\\
\because \frac{\partial \psi}{\partial y} &=\sin x+ x^2e^y + h'(y)\\&= \sin x+ x^2e^y -1 \\
\therefore h'(y)&=-1\\
\therefore h(y)&=-y+C\\
\therefore \psi(x, y)&=\sin x+ x^2e^y -y + C\\
\because \frac{d\psi}{dx}&=0\\
\therefore \psi(x, y)&=C'\\
\end{align}\\
\text{Therefore, the solution is }\sin x+ x^2e^y -y = C.$$

**Exercise** Homogeneous equation substitution. Using substitution $v=\frac{y}{x}$ to solve: 

$$\frac{dy}{dx}=\frac{x^2+xy+y^2}{x^2}$$

\begin{align}
\frac{dy}{dx}&=(\frac{y}{x})^2+\frac{y}{x}+1\\
&=v^2+v+1.
\end{align}

$$\therefore \frac{dy}{dx}=\frac{d}{dx}vx=x\frac{dv}{dx}+v.\\
\implies x\frac{dv}{dx}+v=v^2+v+1.\\
...\\
v=\tan(\ln|x|+C)\\
\text{Finally, the solution is } y=x\tan(\ln|x|+C).$$ 

### 2.7 Euler's Method (Numerical Method)

Consider $\frac{dy}{dt}=f(t,y), y(t_0)=y_0$. Assume that Thm 2.4.2 holds, that is $f$ and $\frac{\partial f}{\partial y}$ are continuous near $(t_0, y_0)$.

**Euler's method** find an approximate solution. 

Idea: use tangent line to approximate the true solution. 

Find the equation of the tangent line at $(t_0, y_0)$. Use point-slope form of line: 

$$y=y_0 + f(t_0,y_0)(t-t_0)$$

Suppose $t_1=t_0+h$, where $h$ is small, called the "step size." We get an approximation of the true solution at $t_1$ as $y_1=f(t_0, y_0)+h$.

**Euler's method: algorithm**

Given equation $\frac{dy}{dt}=f(t,y), f(t_0)=y_0$.

1. Choose $h$, the step size. 
2. Compute $f(t_0,y_0)$.
3. Compute $t_1=t_0+h$, $y_1=y_0+f(t_0,y_0)h$.
4. Repeat step 2-3. $t_{k+1}=t_k+h$, $y_{k+1}=y_k+f(t_k,y_k)h$. 

**Example** $\frac{dy}{dt}=2y-1, y(0)=1$. Using Euler's method with step size $h=0.25$ to approximate $y(1)$. 

<table>
<tr>
<th>Step</th><th>$t_k$</th><th>Estimate $y_k$</th><th>$f(t_k,y_k)$</th><th>True value of $y(t_k)$</th>
</tr>
<tr>
<td>0</td><td>0</td><td>1</td><td>1</td><td>1</td>
</tr>
<tr>
<td>1</td><td>0.25</td><td>1.25</td><td>1.5</td><td>1.324</td>
</tr>
<tr>
<td>2</td><td>0.5</td><td>1.625</td><td>2.25</td><td>1.859</td>
</tr>
<tr>
<td>3</td><td>0.75</td><td>2.168</td><td>3.375</td><td>2.741</td>
</tr>
<tr>
<td>4</td><td>1</td><td>3.031</td><td>-</td><td>4.195</td>
</tr>
</table>

Finally, $y_4=3.031$ is the estimate for $y(1)$. 

Remark: the true solution is $y(t)=\frac{1}{2}e^{2t}+\frac{1}{2}$.

**Exercise** Consider $\frac{dy}{dt}=2t-y,y(2)=4$. Use Euler's method with step size $h=0.5$ to estimate $y(4)$. 

## Review: Exercises for mid-term

**Example** Understand the meaning of a solution to a differential equation.

Find $r$ so that the equation $t^2y''+4ty'+2y=0$ has a solution of the form $y=t^r$. 

To solve this, plug the function into the equation and solve for $r$.

$$\begin{align}
t^2(t^r)''+4t(t^r)'+2t^r&=0\\
t^2(rt^{r-1})+4t\cdot rt^{r-1}+2t^r&=0\\
r(r-1)t^r+4rt^r+2t^r&=0\\
t^r(r^2+3r+2)&=0\\
\implies r^2+3r+2&=0\\
\implies r&=-1 \text{ or} -2.
\end{align}\\$$

The solutions are $y(t)=t^{-1}, y(t)=t^{-2}$.

**Example** Substitution.

**Example** Autonomous equations. 

Consider $\frac{dy}{dt}=\sin^2(y)-k$.

1. Find $k$ such that $y=\frac{\pi}{3}$ is an equilibrium solution and determine the stability.
2. Let $y=\varphi(t)$ be a solution with $y(0)=0$. Find $\lim_{t\to +\infty}\varphi(t)$.

Solution:

1. $$\sin^2\frac{\pi}{3}=k \implies k=\frac{3}{4}.\\
f(y)=\sin^2(y)-\frac{3}{4}.\\
\sin(y)=\pm\frac{\sqrt{3}}{2}\\
y=k\pi\pm\frac{\pi}{3},k\in\mathbb{Z}\\$$
$\sin(y)>0$ when $y\in (k\pi+\frac{\pi}{3}, k\pi+\frac{2\pi}{3})$, 
$\sin(y)<0$ when $y\in (k\pi-\frac{\pi}{3}, k\pi+\frac{\pi}{3})$. 
Through the phase line, $y(t)=\frac{\pi}{3}$ is unstable. 

2. From the stability analysis, $\lim\varphi(t)_{t\to\infty}=-\frac{\pi}{3}$. 

**Example** Applications.

Mixing problem: $\frac{dQ}{dt}=r_\text{in}\rho_\text{in}-r_\text{out}\rho_\text{out}$. $\rho_\text{out}$ is usually $\frac{Q(t)}{V(t)}$. 

Temperature problem: $\frac{dT}{dt}=k(T-T_s)$.

Compound interest: $\frac{dS}{dt}=rS\pm k$.

Free fall problem: Not tested in midterm 1.

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
y(0)=2 \implies 2=c_1+c_2\\
y'(0)=3 \implies 3=-2c_1-3c_2
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
W[y_1,y_2]=Ce^{-\int \frac3{2t}dt}=Ct^{\frac32}$$

### 3.3 Complex Roots of the Characteristic Equation

Consider $ay''+by'+cy=0$. The characteristic equation is $ar^2+br+c=0$. If $\Delta=b^2-4ac<0$, the equation has two complex roots $r=\frac{-b \pm i\sqrt{-\Delta}}{2a}$. We write $r_1=\lambda +i\mu, r_2=\lambda -i\mu$,  where $\lambda=-\frac b{2a}, \mu=\frac{\sqrt{-\Delta}}{2a}$.

Two complex solutions to the DE is $y_1=e^{(\lambda+i\mu)t}, y_2=e^{(\lambda-i\mu)t}$. 

We need to understand $e^{it}$. Use Euler's formula $e^{it}=\cos t+i\sin t$, we have complex value solutions for the DE: $y_1(t)=e^{\lambda t}(\cos \mu t + i\sin \mu t)$, $y_2(t)=e^{\lambda t}(\cos \mu t - i\sin \mu t)$. 

Use the superposition principle, $\tilde{y_1}=\frac{y_1+y_2}{2}=e^{\lambda t}\cos\mu t$, $\tilde{y_2}=\frac{y_1-y_2}{2i}=e^{\lambda t}\sin\mu t$. 

$\tilde{y_1}, \tilde{y_2}$ are real valued solutions. $W[\tilde{y_1}, \tilde{y_2}]=\mu e^{2\lambda t}\neq 0$ since $\mu \neq 0$. So the general solution in this case is 

$$y=c_1e^{\lambda t}\cos \mu t+c_2e^{\lambda t}\sin \mu t$$ 

(where $\lambda=-\frac b{2a}, \mu=\frac{\sqrt{-\Delta}}{2a}$)

**Example** Solve $y''+y'+\frac{37}4y = 0, y(0)=2, y'(0)=8$. 

The characteristic equation $r^2+r+\frac{37}{4}. $ $\Delta=36<0$. 

$r_1=-\frac12+3i, r_2=\frac12-3i$. 

$\lambda=-\frac12, \mu=3$. 

The general solution is $y=c_1e^{-\frac 12 t}\cos 3t+c_2e^{-\frac{1}{2}t}\sin 3t = e^{-\frac 12 t}(c_1\cos 3t + c_2\sin 3t)$.

To find $c_1, c_2$, use the initial conditions. 

$y(0)=c_1+0=2$

\begin{align}
y'(t)&=-\frac 12e^{-\frac 12 t}(c_1\cos 3t + c_2\sin 3t) + e^{-\frac 12 t}(-3c_1\sin 3t + 3c_2\cos 3t)\\
& = -\frac{1}{2}y(t)+e^{-\frac 12 t}(-3c_1\sin 3t + 3c_2\cos 3t). \\
&\implies 8=-1+3c_2 \implies c_2=3 \\
\end{align}

The solution is $y=e^{-\frac 12 t}(2\cos 3t + 3\sin 3t)$. The graph oscillates and decays to 0. 

**Example** Solve the equation $y''+9y=0$. 

$\lambda=0, \mu=3$. So the general solution is $y=c_1\cos 3t + c_2\sin 3t$. The graph of the solution is like a sine wave. 
