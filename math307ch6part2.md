
### 6.4 Equations with Discontinuous Forcing Functions

Consider spring-mass system $mu''+\gamma u' + ku = F(t)$, when $F(t)$ is piecewise continuous. 

**Example** Find the solution of $y''+4y=g(t)$, where $g(t)=\begin{cases}0 &(0\leq t \lt 30) \\ t-30 &(t \geq 30)\end{cases}$. $y(0)=0$, $y'(0)=10$. 

We solve the system using Laplace transform. 

Step 1: $g(t)=u_{30}(t)(t-30)$. So $\Lap\{g(t)\}=e^{-30s}\Lap\{t\}$

Step 2: 

\begin{align}
\Lap\{y''\}+4\Lap\{y\} &= \Lap\{ u_{30}(t-30) \} \\
s^2\Lap\{y\}-sy(0)-y'(0)+4\Lap\{y\}&=e^{-30s}\Lap\{t\} \\
(s^2+4)\Lap\{y\} - 10&=e^{-30s}\frac{1}{s^2}\\
\Lap\{y\}&={10 \over s^2+4} + {e^{-30s} \over s^2(s^2+4)}\\
\end{align}

Step 3: 

\begin{align}
y &= \Lap^{-1}\Bigl\{ {10 \over s^2+4}\Bigr\} +  \Lap^{-1}\Bigl\{ {e^{-30s} \over s^2(s^2+4)}\Bigr\} \\
&= 5 \Lap^{-1}\Bigl\{ {2 \over s^2 + 2^2 }\Bigr\} + \Lap^{-1} \Bigl\{ \frac 1 4 e^{-30s}\Bigl({1 \over s^2} - {1 \over s^2+4} \Bigr) \Bigr\} \\
&= 5 \sin 2t + \frac 1 4 \Lap^{-1}\{\frac{e^{-30s}}{s^2}\} - \frac 1 4 \cdot \frac 1 2 \cdot \Lap\{ {2e^{-30s} \over s^2+2^2} \}\\
&=5\sin 2t + u_{30}(t)\Bigl(\frac 1 4 (t-30) - \frac 1 8 \sin 2(t-30)\Bigr)
\end{align}

Note: Regular partial fraction decomposition

\begin{align}
{1 \over s^2(s^2+4)}&={A \over s} + {B \over s^2} + {Cs+D \over s^2+4} \\
\end{align}

General Form: 

\begin{align}
{P(s) \over Q(s)} &= {(s-a_1)^{m_1} \cdots (s-a_i)^{m_i} \over (s-b_1)^{n_1} \cdots (s-b_i)^{n_i}} \\
&= {A_1 \over s-b_1}+{A_2 \over (s-b_1)^2} + \cdots + {A_{n_1} \over (s-b_1)^{n_1}} + \cdots
\end{align}

**Example** Find the solution to $y''+2y'+y=$$g(t)=\begin{cases}0 &(0 \leq t \lt 7)\\10\sin(t-7) &(t\geq 7)\end{cases}$. $y(0)=0$, $y'(0)=10$.

Step 1: $g(t)=10u_7(t)\sin(t-7)$. 

Step 2: 

\begin{align}
\Lap\{y''\}+2\Lap\{y'\}+ \Lap\{y\}&= \Lap\{g(t)\}\\
(s+1)^2\Lap\{y\}-10 &= 10e^{-7s}\Lap\{\sin t\}={10e^{-7s} \over s^2+1}
\end{align}

\begin{align}
\therefore \Lap\{y\}&={10 \over (s+1)^2} + {10e^{-7s} \over (s+1)^2(s^2+1)}\\
\therefore y &= \Lap^{-1}\{{10 \over (s+1)^2} \} + \Lap^{-1}\{{10e^{-7s} \over (s+1)^2(s^2+1)} \}\\
&=10te^{-t} + 10u_7(t)\Lap^{-1}\Bigl\{{1\over 2(s+1)} + {1 \over 2(s+1)^2} + {-s \over 2(s^2+1)}\Bigr\}(t-7)\\
&=10te^{-t} + 5u_7(t)( e^{-t+7} + (t-7)e^{-t+7} - \cos (t-7))
\end{align}

Partial fraction decomposition: 

\begin{align}
{1 \over (s+1)^2(s^2+1)} &= {A \over (s+1)}+{B \over (s+1)^2} + {Cs+D \over s^2+1}
\end{align}

### Final Review



> Written with [StackEdit](https://stackedit.io/).