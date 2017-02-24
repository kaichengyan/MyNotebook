
# Intro to Differential Equations

## Chapter 6: Laplace Transform

### 6.1 The Laplace Transform

> **Definition** Let $f(t)$ be a function of $t$. The Laplace transform of $f$, denoted by $\mathcal L \{f(t)\}$ or $F(s)$, is defined by $\mathcal L\{f(t)\}=F(s)=\int^{\infty}_0 e^{-st}f(t)dt$. 

Note that 

1. the original function is in $t$ but $F(s)$ is a function of $s$.
2. We have to define improper integral and find $f$ so that the integral is finite. 
3. Usually $f(t)$ is defined for $t \geq 0$, but $F(s)$ could be defined for $s$ complex. We usually deal with real values. 
4. This is an example of integral transform 
$$Tf(s)=\int^\beta_\alpha K(s, t)f(t)dt$$


**Improper Integrals**

Recall that $\int^\infty_a f(t)dt=\lim_{A\to \infty}\int^A_af(t)dt$. 

If the limit is finite, the improper integral is called convergent. Otherwise, the integral is divergent. 

**Example** Find the Laplace transform $\mathcal L \{e^{ct}\}$.

\begin{align}
\mathcal L\{e^{ct}\}&=\int^\infty_0e^{-st}e^{ct}dt\\
&=\lim_{A\to\infty}\int^A_0 e^{(c-s)t}dt\\
&=\lim_{A\to\infty}{e^{(c-s)t} \over c-s}\lvert^A_0\\
&=\lim_{A\to\infty}{e^{(c-s)A} \over c-s} - {1\over c-s}\\
&={1 \over c-s} \lim_{A\to\infty}e^{(c-s)A} - {1\over c-s}\\
\end{align} 

$$
\lim_{A\to\infty}e^{(c-s)A}=\begin{cases}
\infty,&c-s>0\\
0, &c-s<0
\end{cases}
$$

Note that if $c=s$, $\mathcal L \{e^{ct}\}=\lim_{A\to\infty}=\infty$.

Therefore, when $s>c$, the transform is defined and $\mathcal L\{e^{ct}\}=\frac{1}{s-c}$.

#### Piecewise continuous function

> **Definition** $f$ is piecewise continuous on $[\alpha, \beta]$. If the interval can be partitioned as $[\alpha, t_1)$, $[t_1, t_2)$, ..., $[t_n, \beta]$ such that 

1. $f(t)$ is continuous on $(t_i, t_{i+1})$.
2. $f$ has finite limits on each $t_i$.

**Example**

$$f(t) = \begin{cases}
t^2, &0\leq t < 1\\
2+t, &1<t\leq 2
 \end{cases}$$

For piecewise continuous function $f$, 

$$\int^\beta_\alpha f(t)dt = \sum\int^{t_{i+1}}_{t_i}f(t)dt$$

**Example** Find the Laplace transform of 

$$f(t)=\begin{cases}
1, &0\leq t<1\\
k, &t=1\\
0,&t>1
\end{cases}$$

\begin{align}
\mathcal L \{f(t)\}&=\int^\infty_0e^{-st}f(t)dt\\
&= \int^1_0e^{-st}dt + \int^\infty_1e^{-st}\cdot0dt\\
&=-\frac 1s (e^{-st})^1_0\\
&=-\frac 1s (e^{-s} - 1)
\end{align}

> **Theorem** If $f$ is piecewise continuous on $[0, A]$, $\lvert f \rvert \leq ke^{at} (t\geq M)$, then $\mathcal L\{f(t)\}=F(s)$ is defined for $s>a$.


> **Theorem (Linear Property)** $\mathcal L \{ c_1f_1(t) + c_2f_2(t) \}$$=c_1\mathcal L \{f_1(t)\} + c_2\mathcal L \{f_2(t)\}$.

**Example** Find $\mathcal L \{\cos (at)\}, t>0$.

\begin{align}
\mathcal L \{\cos (at)\}&=\int^\infty_0e^{-st}\cos (at)dt\\
&=\lim_{A\to\infty}\int^A_0e^{-st}\cos(at)dt\\
&=\lim_{A\to\infty}\int^A_0e^{-st}d({\sin at \over a})\\
&=\lim_{A\to\infty}[(e^{-st}{\sin at \over a})^A_0 - \int^A_0{\sin at \over a}de^{-st}]
\end{align}