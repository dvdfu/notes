<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>

#Particular Solution

|Given|Try|
|---|---|
|$e^{ax}$|$c\cdot{}e^{ax}$|
|$x^n$|$k_1x^n+k_2x^{n-1}+\dots+k_{n-1}$|
|$\cos{\omega{x}},\sin{\omega{x}}$|$A\cos{\omega{x}}+B\sin{\omega{x}}$|
|$e^{ax}\cos{\omega{x}},e^{ax}\sin{\omega{x}}$|$e^{ax}(A\cos{\omega{x}}+B\sin{\omega{x}})$|

#Integration by Parts

If $f(t)dt$ can be written as the product $udv$ where $u,v$ are functions of $t$, then $\int{f(t)}dt$ `is expressed as

\[\int{u}dv=uv-\int{v}du\]
\[\int_a^b{u}dv=uv\Big|_a^b-\int_a^b{v}du\]

#Integration Factors

Consider the differential equation $y'+fy=g$, where $y,f,g$ are functions of $t$. We consider a function $\sigma$ of $t$ called an **integrating factor**, such that $\sigma'=\sigma{}f$. We multiply the differential equation by $\sigma$:

\[\sigma{}y'+\sigma{}fy=\sigma{}g\]
\[\sigma{}y'+\sigma'y=\sigma{}g\]

Use the result of integration by parts:

\[(\sigma{}y)'=\sigma{}g\]
\[\sigma{}y+c=\int\sigma{}g\cdot{}dt\]
\[y=\frac{\int\sigma{}g\cdot{}dt+c}{\sigma{}}\]

Calculate $\sigma$, knowing that $\sigma'=\sigma{}f$:

\[\frac{\sigma'}{\sigma}=f\]
\[(\ln(\sigma))'=f\]
\[\ln(\sigma)=\int{}fdt+c\]
\[\sigma=e^{\int{}fdt+c}\]
\[\sigma=c\cdot{}e^{\int{}fdt}\]

#Harmonic Oscillators

Second order linear constant coefficient ODEs often have the form:

\[\ddot{y}+2\zeta\omega_n\dot{y}+\omega_n^2y=f\omega_n^2\]

* $y,f$ are functions of $t$
* $y(0)=y_0$, $\dot{y}(0)=\dot{y}_0$
* $\zeta$ (natural frequency), $\omega_n$ (damping ratio) are nonzero constants

Consider its characteristic equation $\ddot{\lambda}+2\zeta\omega_n\dot{\lambda}+\omega_n^2\lambda=0$ to solve for $\lambda$.

* if $\zeta>1$ then there are 2 real roots. The system is **overdamped** and stable
* if $\zeta=1$ then there are 2 repeated roots. The system is **critically damped** and stable
* if $0<\zeta<1$ then there are complex roots. The system is **underdamped** and stable
* if $\zeta=0$ then there are only complex roots. The system is **undamped** and unstable, creating **resonance**

#Laplace Transforms

\[\mathcal{L}\{f(t)\}=F(s)=\int_0^{\infty}e^{-st}f(t)dt\]
\[\mathcal{L}^{-1}\{F(s)\}=f(t)\]

Both the Laplace transform and its inverse are linear:

\[\mathcal{L}\{af(t)+bg(t)\}=aF(s)+bG(s)\]
\[\mathcal{L}^{-1}\{aF(s)+bG(s)\}=af(t)+bg(t)\]

Some common Laplace transforms include:

|$f(t),t\geq{0}$|$F(s)$|
|---|---|
|$1$|$\frac{1}{s}$|
|$t$|$\frac{1}{s^2}$|
|$t^2$|$\frac{2}{s^3}$|
|$t^n$|$\frac{n!}{s^{n+1}}$|
|$e^{at}$|$\frac{1}{s-a}$|
|$\cos{at}$|$\frac{s}{s^2+a^2}$|
|$\sin{at}$|$\frac{a}{s^2+a^2}$|

##Differential Equations

\[\mathcal{L}\{f'(t)\}=s\mathcal{L}\{f(t)\}-f'(0)\]
\[\mathcal{L}\{f^n(t)\}=s^n\mathcal{L}\{f(t)\}-s^{n-1}f(0)-s^{n-2}f'(0)-\dots-f^{n-1}(0)\]

##Shifting

\[\mathcal{L}\{e^{at}f(t)\}=F(s-a)\]

If a $f(t)$ has the Laplace transform $F(s)$ when $s>\alpha$ then $e^{at}f(t)$ has the Laplace transform $F(s-a)$ when $s-a>\alpha$.

The **Heaviside Step Function** is defined as

\[u(t-a)=\begin{cases}
0 &\mbox{if } t<a \\
1 & \mbox{if } t\geq{a}
\end{cases}\]

If $f_0(t)$ is delayed by $a$ units then $f(t)=f_0(t-a)u(t-a)$.

\[\mathcal{L}\{f(t-a)u(t-a)\}=e^{-as}F(s)\]

##Periodic Signals

If $f(t)$ is a periodic function with period $T$ and interval defined as $g(t)$, then

\[\mathcal{L}\{f(t)\}=\frac{1}{1-e^{-sT}}\int_0^T f(t)e^{-st}dt\]

#PD Controllers

The controller $C(s)=K_P+sK_D$.

For a transfer function $G$ in $Y(s)=G(s)Y_d(S)$, the roots of the numerator polynomial are its **zeroes** and the roots of the denominator polynomial are its **poles**. The poles are significantly more important than the zeroes for system stability.

A transfer function is **Bounded Input-Bounded Output Stable** if for all bounded input $y_d(t)$, the output $y(t)$ is bounded. This is true when all poles of a transfer function are to the left of the imaginary axis.

In a PD controller, we have the relationship

\[Y(s)=\frac{C(s)G(s)}{1+C(s)G(s)}\]

#Convolution

Suppose $H(s)$ is a Laplace transform function that can be separated into two Laplace transform functions $F(s), G(s)$. Suppose the inverse Laplace transforms of $F(s), G(s)$ are $f(t), g(t)$ respectively. By the **Convolution Theorem**,

\[\mathcal{L}^{-1}\{H(s)\}=\mathcal{L}^{-1}\{F(s)G(s)\}=f*g\]

where $f*g$ is a convolution, defined as

\[f*g=\int_0^t{f(t-\tau)g(\tau)d\tau}\]

Integrals of this specific form can be solved more easily using the Convolution Theorem. Conversely, Laplace transform functions that are products of two functions can be solved more easily as well.

#Even, Odd functions

A **periodic** function is a function if $f(t)=f(t+p)$ for any valid $p$ (period). If $f$ is periodic with $p$ then it is also periodic with $2p,3p,4p$, etc. The smallest $p$ is the **fundamental period**.

An **even function** is **symmetric** about $x=0$, or $f(-x)=f(x)$. For example, any even power of $x$, or $\cos$. Additionally, $\int_{-a}^af(x)dx=2\int_0^af(x)dx$ if $f$ is even.

An **odd function** is **antisymmetric** about $x=0$, or $f(-x)=-f(x)$. For example, any odd power of $x$, or $\sin$. Additionally, $\int_{-a}^af(x)dx=0$ if $f$ is odd.

|Equation|Output|
|---|---|
|even + even|even|
|even $\cdot$ even|even|
|odd + odd|odd|
|odd $\cdot$ odd|even|
|even + odd|odd|
|even $\cdot$ odd|even|

Any $\cos$ or $\sin$ function with frequency $\frac{n\pi}{L}$, for any natural number $n$, has a period $2L$. The linear combination of any such functions also has a period $2L$, that is:

\[a_0+a_1\cos{\frac{\pi{x}}{L}}+a_2\cos{\frac{2\pi{x}}{L}}+\dots+b_1\sin{\frac{\pi{x}}{L}}+b_2\sin{\frac{2\pi{x}}{L}}\]
\[=a_0+\sum_{n=1}^{\infty}\Big[a_n\cos{\frac{n\pi{x}}{L}}+b_n\sin{\frac{n\pi{x}}{L}}\Big]\]

has a period $2L$ if it converges. We don't try to proof if it converges (beyond scope of the course).

##Orthogonality Properties Theorem

We want to represent some arbitrary function of period $2L$ like above, with an infinite summation.

\[\int_{-L}^L\cos{\frac{m\pi{x}}{L}}\cos{\frac{n\pi{x}}{L}}dx=0, n\neq{m}\]
\[\int_{-L}^L\sin{\frac{m\pi{x}}{L}}\sin{\frac{n\pi{x}}{L}}dx=0, n\neq{m}\]
\[\int_{-L}^L\sin{\frac{m\pi{x}}{L}}\cos{\frac{n\pi{x}}{L}}dx=0\]
\[\int_{-L}^L\cos^2{\frac{n\pi{x}}{L}}dx=L\]
\[\int_{-L}^L\sin^2{\frac{n\pi{x}}{L}}dx=L\]

Assume $f(x)$ is periodic:

\[f(x)=a_0+\sum_{n=1}^{\infty}\Big[a_n\cos{\frac{n\pi{x}}{L}}+b_n\sin{\frac{n\pi{x}}{L}}\Big]\]

We also assume that we can interchange an integration and infinite summation (not necessarily true). We want to be able to find the 3 coefficients $a_0, a_n, b_n$. These are the **Fourier coefficents** and the resulting summation is the **Fourier Series**.

$a_0$: we integrate from both sides from $-L$ to $L$. $a_0$ is the vertical shift of the periodic signal and represents the 'average' value, so it can usually be determined by observation.

\[a_0=\frac{1}{2L}\int_{-L}^Lf(x)dx\]

$a_n$: we multiply both sides by $\cos{\frac{n\pi{x}}{L}}$ and integrate both sides from $-L$ to $L$.

\[a_n=\frac{1}{L}\int_{-L}^Lf(x)\cos{\frac{n\pi{x}}{L}}dx\]

$b_n$: we multiply both sides by $\sin{\frac{n\pi{x}}{L}}$ and integrate both sides from $-L$ to $L$.

\[b_n=\frac{1}{L}\int_{-L}^Lf(x)\sin{\frac{n\pi{x}}{L}}dx\]
