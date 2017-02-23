
### 3.5 Non-homogeneous equations: method of undetermined coefficients

$$ay''+by'+cy=g(t)$$

> **Theorem 3.5.1** $y_1$ and $y_2$ solve $ay''+by'+cy=0(*)$, then $y(t)=c_1y_1(t)+c_2y_2(t)$ also solves the same equation. If $Y_1$ and $Y_2$ solve the non-homogeneous equation $ay''+by'+cy=g(t)(**)$, then $Y(t)=Y_1-Y_2$ solve $(*)$.

> **Theorem 3.5.2 (Non-homogeneous Solution Theorem)** If $y_1,y_2$ are independent solutions (check with Wronskian) to the homogeneous equation $ay''+by'+cy=0(*)$, $Y(t)$ is ANY solution $ay''+by'+cy=g(t)(**)$, then ALL other solutions to $ay''+by'+cy=g(t)(**)$ can be written as $y(t)=c_1y_1+c_2y_2+Y(t)$.

**Example** Solve $y''+2y'-8y=5e^{3t}$.

Step 1: Find $y_1,y_2$ that solve the homogeneous equation $y''+2y'-y=0$. $y_1=e^{-4t}$, $y_2=e^{2t}$.

Step 2: Find a $Y$ that solves the non-homogeneous equation $y''+2y'-8y=5e^{3t}$. Guess $Y(t)=Ae^{3t}$. Then $Y'(t)=3Ae^{3t}$, $Y''(t)=9Ae^{3t}$. Plug into the DE: $9Ae^{3t}+6Ae^{3t}-8Ae^{3t}=5e^{3t}$. So $7A=5$ $\implies$ $A=\frac 57$.

Step 3: We get the general solution: $y(t)=c_1e^{-4t}+c_2e^{2t}+\frac 57 e^{3t}$. Notice that there is no constant before $Y(t)$. 

**Example** Solve $y''+2y'+y=3\cos t$.

Step 1: $y_1=e^{-t}$, $y_2=te^{-t}$. 

Step 2 (wrong guess): Guess $Y(t)=A\cos t$. ... We need $-2A\sin t=3\cos t$ . DOES NOT WORK. 

Step 2 (correct guess): Guess $Y(t)=A\cos t + B \sin t$. $Y'(t)=-A\sin t+ B\cos t$. $Y''(t)=-A\cos t - B\sin t$. 
\begin{align}
\text{LHS}&=-A\cos t - B\sin t + 2(-A\sin t+ B\cos t) + A\cos t + B \sin t\\
&=2B\cos t -2A \sin t \\
&=3\cos t. \\
\implies B&=\frac 32 \\
y(t)&=c_1e^{-t}+c_2te^{-t}+\frac 32 \sin t
\end{align}


**In general, to get a particular solution to $ay''+by'+cy=g(t)$, guess: **

<table>
<tr>
<th>RHS $g(t)$</th><th>Correct Guess for $Y$</th>
</tr>
<tr>
<td>$e^{st}$</td><td>$Ae^{st}$</td>
</tr>
<tr>
<td>$\cos \omega t$ or $\sin \omega t$</td><td>$A\sin\omega t + B \cos \omega t$</td>
</tr>
<tr>
<td>$\alpha t + \beta$</td><td>$At+B$</td>
</tr>
<tr>
<td>$t^2$</td><td>$At^2+Bt+C$</td>
</tr>
</table>

For sums: if $g(t)=t+e^{5t}$, guess $Y(t)=At+B+Ce^{3t}$.
For products: if $g(t)=t^2e^{3t}$, guess $Y(t)=(At^2+Bt+C)e^{3t}$.

If your initial guess is a multiple of a homogeneous solution $y_1$ or $y_2$, then you have to multiply the guess by $t$. 

**Example** $y''-4y=e^{2t}$.

Step 1: $y_1=e^{2t}$, $y_2=te^{2t}$. 

Step 2 (wrong guess): Using the table, guess $Y=Ae^{2t}$. 

$Y=Ae^{2t}$, $Y'=2Ae^{2t}$, $Y''=4Ae^{2t}$. Then $Y''-4Y=0\neq e^{2t}$. DOES NOT WORK. 

Step 2 (correct guess): $Y(t)=Ate^{2t}$. $Y'(t)=Ae^{2t}+2Ate^{2t}$, $Y''(t)=2Ae^{2t} + 2Ae^{2t}+4Ate^{2t}$. Then the terms with $t$ should cancel out: $Y''-4Y=4Ae^{2t}=e^{2t}$, $\implies A=\frac 14$. The particular solution $Y=\frac 14 t e^{2t}$.

Step 3: General solution: $y=c_1e^{2t}+c_2te^{2t}+\frac t4 e^{2t}$.

**Exercise** $y''+3y'-4y=4t-5e^{-4t}$. $y(0)=1, y'(0)=0$.

## 3.7 Mechanical and electrical vibration

**Free vibrations**

A hanging spring has length $l$. When a mass $m$ is attached to the spring, it has displacement $L$. Call $u(t)$ the displacement from rest at time $t$. Down is considered positive. 

Forces: 

1. Gravity: $F_G=mg$ (down is positive).
2. Hooke's law: $F_s=-k\Delta x = -k(L+u(t))$, where $k$ is the spring constant. At rest: $mg-kL=0$ (relationship between the constants). 
3. Damping (friction, resistance from air): $F_d=-\gamma u'(t)$.
4. External forces: $F(t)$. For today, $F(t)=0$. 

Using Newton's second law: $\Sigma F=ma$. 

\begin{align}
mg-kL-ku-\gamma u+F(t)&=mu''\\
F(t)&=mu''+\gamma u' + ku
\end{align}

Suppose $\gamma=0$, $F(t)=0$: 

$$mu''+ku=0$$

The characteristic equation is $mr^2+k=0$ $\implies r=\pm i \sqrt{\frac{k}{m}}$. $\lambda=0, \mu=\sqrt\frac km$. So $u(t)=c_1\cos\sqrt{\frac{k}{m}}t + c_2\sin\sqrt{\frac{k}{m}}t$. 

We want to write this equation in the form $u(t)=R\cos(\omega_0t-\delta)$:

$$u(t)=\sqrt{c_1^2+c_2^2}\cos(\sqrt{\frac{k}{m}}t-\arctan\frac{c_2}{c_1})$$ 

* $R=\sqrt{c_1^2+c_2^2}$ is the **amplitude**
* $\omega_0=\sqrt{\frac{k}{m}}$ is the **natural frequency**
* $T=\frac{2\pi}{\omega_0}$ is the **period**
* $\delta = \arctan\frac{c_2}{c_1}$ is the **phase angle**

From these identities, we can easily draw the graph of $u(t)$.

If $\gamma > 0$, $F(t)=0$:

$$mu''+\gamma u' + ku = 0$$

The characteristic equation: $mr^2+\gamma r + k = 0$. The roots: ${-\gamma \pm \sqrt {\gamma^2-4mk} \over 2m}$.

(1) $\Delta = \gamma ^2 - 4mk > 0$, we have two real negative roots: $r_{1,2}={-\gamma \pm \sqrt {\gamma^2-4mk} \over 2m}$. 

So the general solution is $u(t)=c_1e^{r_1t}+c_2e^{r_2t}$. The solution goes to 0 as $t\to\infty$. This is called "overdamped."

(2) $\Delta = \gamma ^2 - 4mk = 0$, we have one negative root. 

$u(t)=c_1e^{rt}+c_2te^{rt}$, which goes to 0 when $t\to\infty$. This is called "critically damped."

(3) $\Delta = \gamma ^2 - 4mk < 0$, we have two imaginary roots: $r_{1,2} = -\frac{\gamma}{2m} \pm i{\sqrt{4mk-\gamma^2} \over 2m}$.

\begin{align}
u(t)&=e^{\lambda t}(c_1\cos\omega t + c_2\sin\omega t)\\
&=Re^{\lambda t}\cos(\omega t - \delta)
\end{align}

Because amplitude $A=Re^{\lambda t} \to 0$ as $t \to \infty$, $u(t)$ is a decaying oscillation. $\omega$ is called the **quasi-frequency**, and $T=\frac{2\pi}{\omega}$ is the **quasi-period**.
 
**Example** We have an object at rest weighing 4 lbs stretching a spring 6 inches from natural length. We have a damping force of -2 lbs applies when the velocity is 4 ft/s. There is no forcing ($F(t)=0$). The object is initially displaced downward by 3 inches and released (no initial velocity). Find an ODE modelling this. 

* $W=4 \text{ lbs}$
* $L: \frac12 \text{ ft}$
* $k = 8 \frac{\text{lbs}}{\text{ft}}$ from $mg-kL=0$
* $m=\frac 18 \frac{\text{lbs}}{\text{ft}/\text{s}^2}$
* $\gamma = \frac 12 \frac{\text{lbs}}{\text{ft}/\text{s}^2}$
* $u(0)=\frac 14$
* $u'(0)=0$

$$\frac 18 u'' + \frac 12 u' + 8u = 0$$

**Example** A 1 kg object is placed on a spring that has a constant $k=4 \text{N/m}$. The object is pulled down 0.2 m, then pushed downward with velocity of 1 m/s. No damping. Find the period and amplitude. 

\begin{align}
mu''+ku&=0\\
u''+4u&=0\\
u(t)&=c_1\cos 2t + c_2\sin 2t\\
\end{align}

The period: $T=\frac{2\pi}{2}=\pi \text{ seconds}$.

$$\begin{cases}
u(0)&=0\\
u'(0)&=1
\end{cases}\implies \begin{cases}
c_1&=0.2\\
c_2&=0.5
\end{cases}$$

## 3.8 Forced Vibrations

$$mu''+\gamma u' + ku = F(t)$$

Today, we will look at the case when $F(t)=F_0\cos\omega t$.

(1) No damping: $\gamma = 0$

$$mu''+ku=F_0\cos\omega t$$

Step 1: Solve the homogeneous equation. $y_1=\cos \omega_0 t$, $y_2=\sin \omega_0 t$, where $\omega_0 = \sqrt\frac km$

Step 2: Guess $Y(t)=A\cos\omega t + B\sin\omega t$. 

If $\omega \neq \omega_0$, the particular solution $U(t)={F_0\cos\omega t \over m(\omega_0^2 - \omega^2)}$.

If $\omega = \omega_0$, we need to put a $t$ in $Y(t)$, the particular solution is $U(t)={F_0t\sin\omega t \over 2m\omega_0}$.

**Example** $u''+u=60\cos 10t$. $F_0=60,\omega = 10$.

Step 1: $y_1=\cos t$, $y_2=\sin t$.

Step 2: Guess $Y(t)=A\cos 10t + B\sin 10t$. 
$Y'(t)=-10A\sin 10t +10 B \cos 10t$
$Y''(t)=-100\cos 10t - 100 B \sin 10t$

$\therefore -99A\cos 10t -99B\sin 10t = 60\cos 10t$.
$\therefore -99A=60, -99B=0$
$\therefore A=-\frac{60}{99}, B=0$.

Step 3: General Solution is: $u(t)=c_1\cos t + c_2\sin t - \frac{60}{99}\cos 10t$.

(2) Damping : $\gamma > 0$

(i) $0<\gamma<\sqrt{2mk}$: $mu''+\gamma u' + ku = F_0\cos \omega t$

Step 1:  $y_1(t)=e^{\lambda t}\cos\omega_0 t$, $y_2(t)=e^{\lambda t}\sin\omega_0 t$. Notice that $\lambda =  -\frac{\gamma}{2m} < 0$.

Step 2: Guess $Y(t)=A\cos \omega t + B\sin \omega t$. So the general solution will be $u(t)=e^{\lambda t}(c_1\cos\omega_0 t + c_2\sin \omega_0 t) + Y(t)$. 

Since $\lambda < 0$, $(e^{\lambda t}(c_1\cos\omega_0 t + c_2\sin \omega_0 t)) \to 0$ as $t \to \infty$. We call this part the transient solution. We call $Y(t)$ the steady-state solution. 

As $t \to \infty$, $u(t)$ and $Y(t)$ become indistinguishable. 

**Example** A spring has an object of 1kg attached to it. $\gamma = 2 Ns/m$, $k=5N/m$. 

Solve: $u''+2u'+5u=10\cos t$. 

Step 1: $\lambda = -1$, $\omega_0=2$. $\therefore y_1=e^{-t}\cos 2t$, $y_2=e^{-t}\sin 2t$. 

Step 2: Guess $Y(t)=A\cos t + B\sin t$.
$Y'(t)=-A\sin t + B\cos t$.
$Y''(t)=-A\cos t - B\sin t$. 

$\therefore (-A+2B+5A)\cos t + (-B-2A+5B)\sin t = 10\cos t$. 
$\therefore A=2, B-1$.
$\therefore Y(t)=2\cos t + \sin t$.

$\therefore u(t)=e^{-t}(c_1\cos 2t + c_2 \sin 2t) + 2\cos t + \sin t$. As $t \to \infty$, $u(t)$ is almost $Y(t)$.

## Review for Midterm 2

### Substitution (Euler equation)

**(HW Section 3.3 #34)**

$$t^2 {d^2 y \over dt^2} + \alpha t {dy \over dt} + \beta y = 0$$

Show that if $x=\ln t$, the equation can be transformed to

$${d^2 y \over dx^2} + (\alpha-1) {dy \over dx} + \beta y = 0$$

Proof: 

\begin{align}
{dy \over dt} &= {dy \over dx} {dx \over dt} \\
&= \frac 1t{dy \over dx} 
\end{align}

\begin{align}
{d^2y \over dt^2} &= {d \over dt} {dy \over dt} \\
&= {d \over dt} ( \frac 1t{dy \over dx} ) \\
&={ d \over dt}({dy \over dx})\frac 1t - {dy \over dx}{1 \over t^2}  \\
&= ({d^2y \over dx^2}\frac 1t )\frac{1}{t} - {dy \over dx}{1 \over t^2} \\
&= {1 \over t^2} ({d^2y \over dx^2} - {dy \over dx})
\end{align}

Therefore, 

$$t^2 {d^2 y \over dt^2} + \alpha t {dy \over dt} + \beta y = {d^2 y \over dx^2} + (\alpha-1) {dy \over dx} + \beta y$$


### Undetermined Coefficients

**Table 3.5.1 on Page 182**

$$ay''+by'+cy=g(t)$$

<table>
<tr>
<th>RHS $g(t)$</th><th>Initial Guess for $Y(t)$</th>
</tr>
<tr>
<td>$e^{st}$</td><td>$Ae^{st}$</td>
</tr>
<tr>
<td>$\cos \omega t$ or $\sin \omega t$</td><td>$A\sin\omega t + B \cos \omega t$</td>
</tr>
<tr>
<td>$\alpha t + \beta$</td><td>$At+B$</td>
</tr>
<tr>
<td>$t^2$</td><td>$At^2+Bt+C$</td>
</tr>
<tr>
<td>$a_0+a_1t+\cdots+a_nt^n$</td><td>$A_0+A_1t+\cdots+A_nt^n$</td>
</tr>
<tr>
<td>$(a_0+a_1t+\cdots+a_nt^n)e^{\alpha t}$</td><td>$(A_0+A_1t+\cdots+A_nt^n)e^{\alpha t}$</td>
</tr>
<tr>
<td>$(a_0+a_1t+\cdots+a_nt^n)e^{\alpha t}\cos \beta t$ <br> or $(a_0+a_1t+\cdots+a_nt^n)e^{\alpha t}\sin \beta t$</td><td>$(A_0+A_1t+\cdots+A_nt^n)e^{\alpha t}\cos \beta t$ <br> $+ (B_0+B_1t+\cdots+B_nt^n)e^{\alpha t}\sin \beta t$</td>
</tr>
</table>

If the initial guess is a solution to the homogeneous equation, multiply by $t$.

**Example** Find a particular solution of $y''-6y+9y=te^{3t}+e^{-t}$.

Homogeneous solutions: $y_1=e^{3t}$, $y_2=te^{3t}$.

Particular solution: 

First guess: Let $Y(t)=(At+B)e^{3t}+Ce^{-t}$. Because $(At+B)e^{3t}$ is a solution to the homogeneous solution, it won't work. 

Second guess: Let $Y(t)=(At^2+Bt)e^{3t}+Ce^{-t}$. Because $Bte^{3t}$ is still a solution to the homogeneous equation, it won't work.

Third guess: Let $Y(t)=(At^3+Bt^2)e^{3t}+Ce^{-t}$.
$Y'(t)=3At^2e^{3t}+3At^3e^{3t}+2Bte^{3t}+3Bt^2e^{3t}-Ce^{-t}$.
$Y''(t)=\cdots$

Plug into the original equation: 

$$Y''-6Y'+9Y=6Ate^{3t}+2Be^{3t}+16Ce^{-t}$$

So, 

\begin{cases}
6A &= 1\\
2B &= 0\\
16C &= 1\\
\end{cases}

So the particular solution is $Y(t)=\frac 16 t^3e^{3t} + \frac {1}{16}e^{-t}$.

### Reduction of Order

Note 1: This works for general linear equation $y''+p(t)y'+q(t)y=g(t)$. Given one solution $y_1(t)$, find another one. Let $y_2(t)=v(t)y_1(t)$.

Note 2: Review how to solve separable equations and first order linear equations.

### Application: Spring Vibration

$$mu''+\gamma u' + ku = F(t)$$

Know the meaning of each parameter, and know how to find them in a problem. Get familiar with terms such as natural frequency, amplitude, etc. 

**Example** A 1kg mass is attached to a spring. The spring constant is $k=25 kg/s$. The quasi-period is $\frac{2\pi}{3}$, find the damping constant. 

Quasi period: $T=\frac{2\pi}{\mu}$, where $\mu={\sqrt{4mk-\gamma^2} \over 2m}$. Because $\mu = 3$, $m = 1$, $k = 25$, we know that $\gamma = 8$.