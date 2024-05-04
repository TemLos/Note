
# Lectrue 1
$$
\begin{align*}
u_x &= \frac{u(x+\delta x)-u(x)}{\delta x} \\ 
u_{xx}
 & = \frac{u_x(x + \delta x) - u_x(x)}{\delta x} \\
& = \frac{u(x+\delta x) + u_x(x - \delta x) - 2u_x(x)}{\delta x^2}\\
\end{align*}
$$
# Lecture 2
$$
\begin{cases}
U_t = U_xx ,t\gt 0,x(0,1)\\
U(0,t) = U(1,t) = 0 \\
U(x,0) = U_0(x), 0\le x \le 1
\end{cases}
$$
Analytical Method
$$
\begin{align}
U(x,t) = f(x)g(t) \\
U_t=U_xx \\
fg’ = f’’g \\
\frac{g’}{g} = \frac{f’’}{f} = -C \\
\begin{cases}
f’’+cf=0\\
f(0) = f(1) =0 \\
\end{cases}
\newline
\begin{cases}
g’+cg=0\\
f(x)\cdot g(0) = U_0(x) \\
\end{cases}



\end{align}
$$

forward difference
$$
\triangle_{+t} v(x,t) = v(x,t+\triangle t)-v(x,t)
$$
backward difference
$$\triangle_{-t}v(x,t)=v(x,t)-v(x,t-\triangle t)$$
cental difference
$$\delta_t=v(x,t+\triangle t/2)-v(x,t-\triangle t/2)$$

Second order central difference
$$\delta_x^2 v(x,t)=\delta_x(\delta_x v(x,t))$$
$$\triangle_{ox}v(x,t) = \frac{1}{2}(\triangle_{+t}+\triangle_{-t})v(x,t) \\=\frac{1}{2}(v(x,t+\triangle t)+v(x,t-\triangle t))$$

# Lecture 3
$$
\begin{align}
\triangle_{+t}u(x,t)&=u(x+\triangle x,t)-u(x,t)\\
&=\triangle tu’(x,t)+\triangle t^2\frac{u’’(x,t)}{2}+\triangle x^3\frac{u’’’(x,t)}{6}+o(\triangle t^4)
\end{align}
$$
$$
\begin{align}
\delta ^2_xu(x,t)&=u(x+\triangle x,t)-2u(x,t)+u(x-\triangle x,t)\\&=\triangle x^2(x,t)+\triangle x^4\frac{U_{xxxx}(x,t)}{12}
\end{align}
$$
#### Finite Difference
$$\frac{u^{n+1}_j-u^n_j}{\triangle t}=\frac{u_{j+1}^n-2u^n_j+u_{j-1}^n}{\triangle x^2}$$
$$u^{n+1}_j=u^n_j+\mu(u_{j+1}^n-2u^n_j+u^n_{j-1}),\quad \mu=\frac{\triangle t}{\triangle x^2}$$
#### Truncation Error

$$\begin{align}
T(x,t)&=\frac{\triangle_{+t}u(x,t)}{\triangle t}-\frac{\delta ^2_x u(x,t)}{\triangle x^2}\\&=\triangle t\frac{u_{tt}(x,t)}{2}+o(\triangle t^2)-\triangle x^2\frac{u_{xxxx}(x,t)}{12}+o(\triangle x^3)
\end{align}
$$
consider
$$
\begin{cases}
u_t=u_{xx}\\
u_{tt}=u_{xxt}\\
u_{txx}=u_{xxxx}\\
\end{cases}\\ \\
$$
$$T(x,t)=(\triangle t-\frac{\triangle x2}{6})\frac{u_{tt}(x,t)}{3}+o(\triangle t^2)+o(\triangle x^3)$$
then we have
$$\mu=\frac{1}{6}$$
that is 
$$
\begin{align}
error\quad e^n_j&=u^{n+1}_j-u(j,n+1)\\
&=u^n_j+\mu(u^n_{j+1}-2u^n_j+u^n_{j-1}-[u(x_j,t_n)+\mu(u(x_j,t_n)-2u(x_j,t_n)+u(x_{j-1},t_n))+\triangle t \mu T^n_j])\\
&=(1-2\mu)e^n_j+\mu e^n_{j+1}+\mu e^n_{j-1}-\triangle t T^n_j
\end{align}
$$
Denote
$$E^n=max(|e^n_j|,j=0,1)$$
$$
\begin{align}
E^{n+1}\le |1-2\mu|E^n+2\mu E^n+\triangle t|T^n_j|\\
\end{align}
$$
assume $\mu \le \frac{1}{2}$
$$E^n\le E^n+\triangle t|T^n_j|$$
define $|T^n_j|\le \bar{T}$
$$E^{n+1}\le E^n+\triangle \bar{T}$$
when E(0)=0
$$
\begin{align}
E^1\le E^0+\triangle t \bar{T}=\triangle t\bar{T}\\
E^2\le E^1+\triangle t \bar{T}=2\triangle t\bar{T}\\
E^n\le E^{n-1}+\triangle t \bar{T}=n\triangle t\bar{T}\\
\end{align}
$$
- Amplification Factor
    let $u^n_j=(\lambda)^ne^{ikj\triangle x}$
    $|\lambda|\le1,\ \lim_{n\rightarrow \infty}|\lambda|^n\rightarrow 0$,  if a method is stable
    $|\lambda|\gt1,\ \lim_{n\rightarrow \infty}|\lambda|^n\rightarrow \infty$,  if a method is unstable

- Explicit Method
    $$\frac{u^{n+1}_j-u^n_j}{\triangle t}=\frac{u^n_{j+1}-2u^n_j+u^{n}_{j-1}}{\triangle x^2}$$
- Implicit Method
    $$\frac{u^{n+1}_j-u^n_j}{\triangle t}=\frac{u^{n+1}_{j+1}-2u^{n+1}_j+u^{n+1}_{j-1}}{\triangle x^2}$$
    $$u^n_j=-\mu u^{n+1}_{j-1}+(1+2\mu)u^{n+1}_j-\mu u^{n+1}_{j+1}=u^n_j$$

# Lecture 4
$$Au=f$$
$$u=A/f$$
**$$u=A^{-1}\times f$$**
Consider
$$
\begin{cases}
U_t = U_xx ,t\gt 0,x(0,1)\\
U(0,t) = U(1,t) = 0 \\
U(x,0) = U_0(x), 0\le x \le 1
\end{cases}\\
$$
$$
u^n_j=(\lambda)^ne^{ikj\triangle x}
$$
We have
$$-\mu\lambda e^{-ik\triangle x}+(1+2\mu)\lambda-\mu\lambda e^{ik\triangle x}=1$$
$$
\begin{align}
\lambda -1 &=\mu\lambda (e^{ik\triangle x}-2+e^{ik\triangle x})\\
&=2\mu\lambda [cos(k\triangle x)-1]\\
&=-4\mu \lambda sin^2(\frac{2k\triangle x}{2})
\end{align}
$$
So$$\lambda=\frac{1}{1+4\mu sin^2\frac{2k\triangle x}{2}},\  0\le\lambda\le1\ for\ any\  \mu$$
The implicit method is unconditionally stable
- Explicit Method
$$
\begin{align}
u^{n+1}_j-u^n_j&=\mu\delta^2_x u^n_j\\
&=\frac{u^n_{j+1}-2u^n_j+u^n_{j-1}}{(\Delta x)^2}
\end{align}
$$
- Implicit Method
$$
\begin{align}
u^{n+1}_j-u^n_j&=\mu\delta^2_x u^{n+1}_j\\
&=\frac{u^{n+1}_{j+1}-2u^{n+1}_j+u^{n+1}_{j-1}}{(\Delta x)^2}
\end{align}
$$
####  $\theta$ Method
    $$u^{n+1}_j-u^n_j=\mu(\theta\delta^2_x u^{n+1}_j+(1-\theta)\delta^2_x u^n_j )$$
$$
\begin{align}
-\theta \mu u^{n+1}_{j-1}+(1+2\theta \mu)u^{n+1}_j-\theta \mu u^{n+1}_{j+1}&=[1+(1-\theta)\mu \delta^2_x]u^n_j\\
&=u^n_j+(1-\theta)\mu[u^n_{j+1}-2u^n_j+u^n_{j-1}]
\end{align}
$$
##### Stability
Let $u^n_j=(\lambda)^ne^{ikj\triangle x}$
Then we can derive
$$-\theta \mu\lambda e^{-ik\triangle x}+(1+2\theta\mu)\lambda-\theta\mu\lambda e^{ik\triangle x}= 1+(1-\theta)\mu[e^{ik\triangle x}-2+e^{-ik\triangle x}]$$
$$\lambda = \frac{1-4(1-\theta)\mu sin^2\frac{k\triangle  x}{2}}{1+4\theta\mu sin^2\frac{k\triangle x}{2}},\ \ 0\le \theta \le 1$$
If we require $|\lambda|\le 1$
$$-1\le \frac{1-4(1-\theta)\mu sin^2\frac{k\triangle x}{2}}{1+4\theta\mu sin^2\frac{k\triangle x}{2}}$$
$$\mu(1-2\theta)sin^2\frac{k\triangle x}{2}\le \frac{1}{2}$$
$$
\begin{cases}
\theta \ge \frac{1}{2},\ for\ any\ \mu \\
\theta \lt \frac{1}{2},\ \mu\le\frac{1}{2(1-2\theta)}
\end{cases}
$$
##### Error
To calculate truncation error
we firstly calculate Taylor Expansion at$(x_j, t_n+\frac{\Delta t}{2})$
$$
\begin{align}
u(x_j,t_{n+1})=u^{n+1}_{j}&=[u+\frac{\Delta t}{2}u_t+\frac{1}{2}(\frac{\Delta t}{2})^2u_{tt}+\frac{1}{6}(\frac{\Delta t}{2})^3u_{ttt}+\cdots]^{n+1/2}_j\\
u^{n}_{j}&=[u-\frac{\Delta t}{2}u_t+\frac{1}{2}(\frac{\Delta t}{2})^2u_{tt}-\frac{1}{6}(\frac{\Delta t}{2})^3u_{ttt}+\cdots]^{n+1/2}_j\\
\end{align}
$$
Then we expanse $\delta^2_x u^{n+1}_j$ and $\delta^2_x u^{n}_j$ at $(x_j，x_{n+\frac{1}{2}})$
$$
\begin{align}
\delta_t u_t^{n+\frac{1}{2}}&=u(x,t_{n+\frac{1}{2}}+\frac{\Delta t}{2})-u(x_j,t_{n+\frac{1}{2}}-\frac{\Delta t}{2})\\
&=u^{n+1}_j-u^n_j\\
&=[\Delta tu_t+\frac{\Delta t^3}{24}u_{ttt}+\cdots]^{n+1/2}_j\\ \\
\delta_x^2 u^{n+1}_j&=[(\Delta x)^2 u_{xx}+\frac{1}{12}\Delta x^4 u_{xxxx}+\frac{2}{6!}\Delta x^6u_{xxxxxx}+\cdots]^{n+1}_j \\
&=[(\Delta x)^2u_{xx}+\frac{1}{12}(\Delta x)^4u_{xxxx}+\frac{2}{6!}(\Delta x)^6u_{xxxxxx}+\cdots]\\
&\ +\frac{1}{2}\Delta t[(\Delta x)^2u_{xxt}+\frac{1}{12}(\Delta x)^4u_{xxxxt}+\cdots]\\
&\ +\frac{1}{2}(\frac{1}{2}\Delta t)^2[(\Delta x)^2u_{xxtt}+\cdots]+\cdots
\newline \newline
\theta\delta^2_xu^{n+1}_j&+(1-\theta)\delta^2_xu^n_j=\\
&\ [(\Delta x)^2u_{xx}+\frac{1}{12}(\Delta x)^4u_{xxxx}+\frac{2}{6!}(\Delta x)^6u_{xxxxxx}+\cdots]\\
& \ +(\theta-\frac{1}{2})\Delta t][(\Delta x)^2u_{xxt}+\frac{1}{12}(\Delta x)^4u_{xxxxt}+\cdots]\\
&\ +\frac{1}{8}(\Delta x)^2[u_{xxtt}]+\cdots
\end{align}
$$
hence we get truncation error
$$
\begin{align}
T^{n+\frac{1}{2}}_j &=\frac{\delta_tu^{n+\frac{1}{2}}_j}{\Delta t}-\frac{\theta \delta^2_xu^{n+1}_j+(1-\theta)\delta^2_x u^n_j}{(\Delta x)^2} \\
&=[u_t-u_{xx}]+[(\frac{1}{2}-\theta)\Delta t\ u_{xxt}-\frac{1}{12}(\Delta x)^2u_{xxxx}]\\
&\ \ \ \ +[\frac{1}{24}(\Delta t)^2u_{ttt}-\frac{1}{8}(\Delta t)^2u_{xxtt}]\\
&\ \ \ \ +[\frac{1}{12}(\frac{1}{2}-\theta)\Delta t(\Delta x)^2u_{xxxxt}-\frac{2}{6!}(\Delta x)^4u_{xxxxxx}]\\
&=u_t+o(\Delta t^2)-[u_{xx}+o(\Delta x^2)+(\theta -\frac{1}{2})\Delta tu_{xxt}+o(\Delta t^3)]\\
&=o(\Delta t^2)+o(\Delta x^2)-(\theta-\frac{1}{2})\Delta t u_{xxt}\\
\end{align}
$$
When $\theta = \frac{1}{2}$, $T^{n+\frac{1}{2}}_j$ depends on $\Delta t^2$ and $\Delta x^2$. Which is called Crank-Nicolson Scheme.
##### An Approximation  Scheme
For 2D $\theta$ -method, we have
$$
\begin{align}
u^{n+1}-u^n&=\theta(\mu_x\delta^2_xu^{n+1}+\mu_y\delta_y^2 u^{n+1})+(1-\theta)(\mu_x\delta^2_x u^n+\mu_y\delta^2_yu^n)\\
{\theta=1/2}\Rightarrow &(1-\frac{\mu_x\delta^2_x}{2})(1-\frac{\mu_y\delta^2_y}{2})u^{n+1}=(1+\frac{\mu_x\delta^2_x}{2})(1+\frac{\mu_y\delta^2_y}{2})u^n
\end{align}
$$
Make an intermediate level
$$
\begin{cases}
(1-\frac{\mu_x\delta^2_x}{2})u^{n+\frac{1}{2}}=(1+\frac{\mu_y\delta^2_y}{2})u^n\\
(1-\frac{\mu_y\delta^2_y}{2})u^{n+1}=(1+\frac{\mu_x\delta^2_x}{2})u^{n+\frac{1}{2}}\\
\end{cases}
$$
By using the level, we can derive:
$$
\begin{align}
&(1+\frac{\mu_x\delta^2_x}{2})(1-\frac{\mu_x\delta^2_x}{2})u^{n+\frac{1}{2}}\\
=&(1+\frac{\mu_x\delta^2_x}{2})(1+\frac{\mu_y\delta^2_y}{2})u^{n}\\
=&(1-\frac{\mu_x\delta^2_x}{2})(1-\frac{\mu_y\delta^2_y}{2})u^{n+1}
\end{align}
$$

# Lecture 5
#### Maximum principle
with $0\le \theta \le 1$ and $\mu(1-\theta)\le \frac{1}{2}$
$$
\begin{cases}
U_{min}=min\{U_0^m,\ 0\le m\le n;U^0_j,\ 0\le j\le J;\ U^m_j,\ 0\le m\le n\}\\
U_{max}=max\{U_0^m,\ 0\le m\le n;U^0_j,\ 0\le j\le J;\ U^m_j,\ 0\le m\le n\}\\
\end{cases}
$$
Consider $\theta$-method $U^{n+1}_j-U^n_j=\mu[\theta\delta^2_xU^{n+1}_j+(1-\theta)\delta^2_xU_j^n]$
$$
\begin{align}
-\theta\mu U^{n+1}_{j-1}+(1+2\theta \mu)U^{n+1}_{j}-\theta \mu U^{n+1}_{j+1}&=[1+(1-\theta)\mu \delta^2_x]U^n_j\\
(1+2\mu\theta)U_j^{n+1}&=\theta\mu[U_{j-1}^{n+1}+U^{n+1}_{j+1}]\\
&\quad +(1-\theta)[U_{j-1}^n+U_{j+1}^n]\\
&\quad+[1-2(1-\theta)]U^j_n
\end{align}
$$
make $U^*\le U^n_j,U^n_{j+1},U^n_{j-1},U^{n+1}_{j-1},U^{n+1}_{j+1}$
$$
\begin{align}
(1+2\mu\theta)U^{n+1}_j&\ge(1+2\mu\theta)U^*\\
U^{n+1}_j&\ge U^*
\end{align}
$$
For any refinement path which satisfies this stability condition. the approximation given by (2.75) coverages uniformly on $[0,1] \times [0,t_f]$
$$
\begin{align}
error \qquad e^n_j=U_j^n
-u(x_j,t_n)\\
\Delta T^{n+\frac{1}{2}}_j=\delta_t u^{n+\frac{1}{2}}_j-\mu[\theta \delta^2_x u^{n+1}_j+(1-\theta)\delta^2_x u^{n}_j]
\end{align}
$$
$$
\begin{align}
(1+2\theta\mu)u(x_j,t_{n+1})&=\theta\mu[u(x_{j-1},t_{n+1})+u(x_{j+1},t_{n+1})]\\
&\quad +(1-\theta)[u(x_{j-1},t_n)+u(x_{j+1},t_n)]\\
&\quad +[1-2(1-\theta)\mu]u(x_j,t_n)+T^{n+\frac{1}{2}}_j\Delta t
\end{align}
$$
define
$$
E^n=max|e^n_j|,\qquad T^{n+\frac{1}{2}}=max|T^{n+\frac{1}{2}}_j|
$$
$$
\begin{align}
(1+2\theta\mu)|e^{n+1}_j|&\le 2\theta\mu E^{n+1}+E^n+\Delta tT^{n+\frac{1}{2}}\\
(1+2\theta\mu)E^{n+1}_j&\le 2\theta\mu E^{n+1}+E^n+\Delta tT^{n+\frac{1}{2}}\\
E^{n+1}&\le E^n+\Delta tT^{n+\frac{1}{2}}
\end{align}
$$
if $E^0=0$ we have
$$
\begin{align}
E^n=n\Delta tT^{n+\frac{1}{2}}=t_F\bar{T}
\end{align}
$$
#### A three-time-level scheme
As for
$$
\frac{u^{n+1}_j-u_j^{n-1}}{2\Delta t}=\frac{u^n_{j+1}-2u^n_j+u^n_{j-1}}{(\Delta x)^2}
$$
we can see when $\theta = 1$, the truncation error involves only $O((\Delta x)^2+(\Delta t)^2)$ , but if we consider stability
$$
\begin{align}
let\ u^n_j=\lambda^ne^{ijk\Delta x}\\
\Rightarrow \lambda^2+8\lambda\mu sin^2{\frac{2k\Delta x}{2}}-1=0\\
\end{align}
$$
**？Why not choose the stable one？**
To make it stable, use $\theta$-method
$$
\frac{u^{n+1}_j-u_j^{n-1}}{2\Delta t}=\frac{\theta \delta^2_x u_j^n+(1-\theta)\delta^2_xu^{n+1}_j}{\Delta x^2}
$$
#### More general boundary conditions
to calculate the boundary condition at x=0, consider the formula
$$
\frac{\partial u}{\partial x}=\alpha(t)u+g(t),\quad \alpha(t)\ge 0
$$
that is 
$$
\begin{align}
\frac{U^n_1-U^n_0}{\Delta x}=\alpha^nU^n_0+g^n\\
U^n_0=\beta^nU^n_1-\beta^ng^n\Delta x
\end{align}
$$
where $\beta = \frac{1}{1+\alpha^n\Delta x}$
from the above, we can derivate
$$
\begin{align}
\delta^2_xU^n_1&=U^n_2-2U^n_1+U^n_0\\
&=U^n_2-(2-\beta^n)U^n_1-\beta^ng^n\Delta x
\end{align}
$$
Now we calculate U-u error
$$
\begin{align}
\frac{\Delta x}{\Delta t}-\frac{\partial x}{\partial t}&=\frac{u(x_1,t_n)-u(x_0,t_n)}{\Delta x}-\alpha^n u(x_0,t_n)-g^n\\
&=\frac{[u+\Delta xu_x+\frac{\Delta x^2}{2}u_{xx}+\cdots]^n_0-u(x_1,t_n)}{\Delta x}\\
&=u_x(x_0,t_n)+o(\Delta x)-\alpha^nu(x_0,t_n)-g^n)
\end{align}
$$
calculate truncation error **?n0?**
$$
\begin{align}
T^{n+1/2}_1&=\frac{u^{n+1}_1-u^n_1}{\Delta t}-\frac{\delta^2_xu^n_1}{(\Delta x)^2}\\
&=\frac{u^{n+1}-u_1^n}{\Delta t}-\frac{u^n_2-[(2-\beta^n)u^n_1-\beta^ng^n\Delta x]}{(\Delta x)^2}\\
&=\frac{u^{n+1}_1-u^n_1}{\Delta t}-\frac{\delta^2_x u^n_1}{(\Delta x)^2}-\frac{\beta ^n}{\Delta x}[\frac{u^n_1-u^n_0}{\Delta x}-\alpha^nu^n_0-g^n]\\
&=[\frac{1}{2}\Delta tu_{tt}-\frac{1}{12}(\Delta x)^2u_{xxxx}+\cdots]^n_1-\beta^n[\frac{1}{2}u_{xx}+\cdots]^n_0\\
&\approx-\frac{1}{2}\beta^nu_{xx}
\end{align}
$$

# Lecture 6
Quiz: maximum principle?

Consider $\theta$-method in two dimension
$$
u_t=b\Delta u=b(u_{xx}+u_{yy})
$$
$$U^{n+1}_j-U^n_j=\theta(\mu_x\delta_x^2u^{n+1}+\mu_y\delta_y^2u^{n+1})+(1-\theta)(\mu_x\delta_x^2u^{n+1}+\mu_y\delta_y^2u^{n+1})$$
$$
\begin{align}
(1-\frac{1}{2}\mu_x\delta^2_x-\frac{1}{2}\mu_y\delta^2_y)u^{n+1}&=(1+\frac{1}{2}\mu_x\delta^2_x+\frac{1}{2}\mu_y\delta^2_y)u^n\\
\Downarrow\\
(1-\frac{\mu_x}{2}\delta^2_x)(1-\frac{\mu_y}{2}\delta^2_y)u^{n+1}&=(1-\frac{\mu_x}{2}\delta^2_x)(1-\frac{\mu_y}{2}\delta^2_y)u^n\\
\Downarrow\\
\end{align}
$$
$$
\begin{cases}
(1-\frac{\mu_x}{2}\delta^2_x)u^{n+\frac{1}{2}}=(1+\frac{\mu_y}{2}\delta^2_y)u^n\\
(1-\frac{\mu_y}{2}\delta^2_y)u^n=(1+\frac{\mu_x}{2}\delta^2_x)U^{n+\frac{1}{2}}
\end{cases}
$$
$$
\begin{align}
\Downarrow

\end{align}
$$
# Lecture 7
#### Finite Element Analysis
To solve
$$
\begin{align}
\begin{cases}
-U_{xx}=1 ,\quad 0\lt x\lt 1\newline
U(0)=U(1)=0
\end{cases}
\end{align}
$$
That is, we need to find a solution in $H^2_0(0,1)$ (Sobolev Space)
Let $v \in H^1_0(0,1)$,  $v$: test function
$$
\int^1_0u_xv_x\rm dx=\int^1_0v\mathrm dx,\quad v\in H^1_0(0,1)
$$
**? Why?**
To solve $v$, construct $v\in v^k=\{\Phi_1,\Phi_2,\cdots,\Phi_k\}\subset H^1_0$, $\Phi_k$ basis function.
Let $u_k=\alpha_1\Phi_1+\alpha_2\Phi_2+\cdots+\alpha_k\Phi_k$
$$
\begin{align}
\int^1_0 u_k=\int^1_0(\alpha_1\Phi’_1+\alpha_2\Phi’_2+\cdots+\alpha_k\Phi’_k)\Phi_k’\mathrm dx=\int^1_0\Phi_k\mathrm dx
\end{align}
$$
$$
\begin{align}
\begin{bmatrix}
\int^1_0\Phi’_1\Phi_1’&\int^1_0\Phi_1’\Phi_2’&\cdots\\
\vdots
\end{bmatrix}

\begin{bmatrix}
\alpha_1\\
\alpha_2\\
\vdots
\end{bmatrix}
&=
\begin{bmatrix}
\int^1_0f\Phi_1\\
\int^1_0f\Phi_2\\
\vdots
\end{bmatrix}
\newline
A\alpha&=F
\end{align}
$$
where
$$
\Phi_k=
\begin{cases}
\frac{x-x_{k-1}}{x_k-x_{k-1}},\quad x_{k-1}\le x\le x_{k}\\
\frac{x-x_{k+1}}{x_k-x_{k+1}},\quad x_k\le x\le x_{k+1}\\
0,\quad otherwise
\end{cases}
$$
if we make $\Delta x = h$, there is 
$$
\begin{align}
\int^1_0\Phi_0’\Phi’_0&=\int^h_0\frac{1}{h}\frac{1}{h}+\int^{2h}_h(-\frac{1}{h})(-\frac{1}{h})+0=\frac{2}{h}\\
\int^1_0\Phi_1’\Phi_2’&=-\frac{1}{h}
\end{align}
$$
$$
A_k=
\begin{bmatrix}
\int_k\Phi_k’\Phi_k’&\int_k\Phi_2’\Phi_1’\\
\int_k\Phi_1’\Phi_2’&\int_k\Phi_2’\Phi_2’
\end{bmatrix}
=
\begin{bmatrix}
\frac{1}{h}&-\frac{1}{h}\\
-\frac{1}{h}&\frac{1}{h}
\end{bmatrix}
$$
$$
A=\sum_{k=0}^nA_k=
\begin{bmatrix}
\frac{1}{h}&-\frac{1}{h}&\cdots&\cdots\\
-\frac{1}{h}&\frac{2}{h}&-\frac{1}{h}&\cdots\\
\vdots&-\frac{1}{h}&\frac{2}{h}&\cdots\\
\vdots&\vdots&\vdots&\frac{1}{h}
\end{bmatrix}
$$

#### Gaussian Function 
A kind of application of FEM
$$
\int^1_0g(x)\approx w_1g(x_1)+w_2g(x_2)+\cdots+w_Mg(x_M)

$$
where$\sum w=1$
Generally, making M = 17 is suitable. 
# Lecture 8
#### Hyperbolic Equation
$$
\frac{\partial u}{\partial t}+a\frac{\partial u}{\partial x}=0
$$
$$
\begin{align}
\frac{\partial u}{\partial t}=a(x,t)\quad characteristic\ curve\\
x=at+c
\end{align}
$$
consider a solution of the above formula over a characteristic curve
$$
\begin{align}
\frac{\mathrm du(x(t),t) }{\mathrm dt}&=\frac{\partial u}{\partial t}+\frac{\partial u}{\partial x}\cdot\frac{\partial x}{\partial t}\\
&=\frac{\partial u}{\partial t}+a\cdot \frac{\partial u}{\partial x}=0
\end{align}
$$
So $u(x,t)=C$ , that is, $u(x,t)$ is a constant along the characteristic curve starting from $x(t_0)$
$$
\begin{align}
u(x,t)=u(at+c,t)=u(c,0)=u^0(c)=u^0(x-at)
\end{align}
$$
Use finite difference to solve
$$
\begin{align}
U_t&+aU_x=0\\
\frac{U^{n+1}_j-U^n_j}{\Delta t}&+a\frac{U^n_j-U^n_{j-1}}{\Delta x}=0\\
U^{n+1}_j&=U^n_j-\frac{a\Delta t}{\Delta x}(U^n_j-U^n_{j+1})
\end{align}
$$

### The Domain of Dependence
Form $U^{n+1}_j=U^n_j-\frac{a\Delta t}{\Delta x}(U^n_j-U^n_{j+1})$, we can draw

![](image_51.jpeg)
$U^{n+1}_j$ depend on every point in the triangle, this triangle is the domain of dependence of $U^{j+1}_j$
### The CFL Condition
To make a scheme convergent, the characteristic curve must lie within the domain of dependence.
The CFL condition is not sufficient for stability but a necessary condition.

Now if we consider negative $\alpha$, the CFL condition becomes:
$$
|\alpha|\Delta t\le \Delta x
$$
To cover  $\alpha\gt 0$ and $\alpha \lt 0$ , we might be tempted to use a central difference in space with a forward difference in time to obtain:
$$
\frac{U^{n+1}_j-U_j^n}{\Delta t}+\alpha \frac{U^n_{j+1}-U^n_{j-1}}{2\Delta x}=0
$$
![](image_52.jpeg)
To investigate the stability of the scheme, use Fourier analysis:
$$
U^j_n=\lambda^ne^{ik(j\Delta x)}
$$
Derive from the above, we have
$$
\lambda=1-\alpha\frac{\Delta t}{\Delta x}\ i\ \mathrm{sin} (k\Delta x)
$$
Where $|\lambda|$ is definitely greater than 1. So it‘s unstable.
### Upwind Scheme
The simplest and most compact stable scheme involving these three points is upwind scheme:
$$
U^{n+1}_j=
\begin{cases}
U^n_j-\alpha\frac{\Delta t}{\Delta x}\Delta_{+x}U^n_j,\quad if\ \alpha\lt0\\
U^n_j-\alpha\frac{\Delta t}{\Delta x}\Delta_{-x}U^n_j,\quad if\ \alpha\gt0\\
\end{cases}
$$
So we have $\lambda$

$$
\lambda=1-\alpha\frac{\Delta t}{\Delta x}(1-e^{-ik\Delta x})=1-\nu(1-e^{-ik\Delta x})\\

$$

$$
|\lambda|^2=1-4\nu(1-\nu)sin^2(\frac{k\Delta x}{2})
$$
$\lambda \le 1$, when $0\le \nu \le 1$ ($4\nu(1-\nu)sin^2(x)\le \frac{1}{2}$).
##### Error analysis
For truncation error
$$
\begin{align}
T^n_j&=\frac{u(x_j,t_{n+1}-u(x_j,t_n))}{\Delta t}+\alpha\frac{u(x_j,t_n)-u(x_{j-1},t_{n})}{\Delta x}\\
&\sim [u_t+\frac{1}{2}\Delta tu_{tt}+\cdots]^n_j + [\alpha(u_x-\frac{1}{2}\Delta xu_{xx}+\cdots)]^n_j\\
&=\frac{1}{2}(\Delta tu_{tt}-\alpha \Delta xu_{xx})+\cdots\\
&=\frac{1}{2}(\nu-1)\alpha \Delta x u_{xx}+\cdots
\end{align}
$$
Which means truncation error of this method is first order accurate.
For error
$$
\begin{align}
e^{n+1}_j&=U^{n+1}_j-u^{n+1}_j\\
&=(1-\nu)u^n_j+\nu u^n_{j-1}-(1-\nu)u^n_j-\nu u^n_{j-1}-\Delta tT^n_j\\
&=(1-\nu)e^n_j+\nu e^n_{j-1}-\Delta tT^n_j
\end{align}
$$
Consider $E^{n+1}\lt E^n+\Delta t\ max|T^n_j|$, there is 
$$
E^n\lt n\Delta tT\le t_FT
$$
# Lecture 9
The upwind scheme has low phase error but high dumping, so we have Lax-Wendroff scheme. 
### The Lax-Wendroff scheme
$$
\begin{align}
u^{n+1}_j=&
\begin{cases}
(1+\mu)u^n_j-\mu u^{n+1}_{j+1},\ a\lt0\\
(1-\mu)u^{n}_j+\mu u^n_{j-1},\ a\gt 0
\end{cases}\\\\

u_t&+au_x=0\\
\mu=&\frac{a\Delta x}{\Delta t}
\end{align}
$$

# Lecture 10
### Finite Volume Method
For $u_t+f_x=0$
$$
\begin{align}
\iint_\Omega(u_x+f_x)\mathrm dx\mathrm dt&=\iint_\Omega div(\vec f,\vec u)\mathrm dx\mathrm dt\\
&=\oint_{\partial \Omega}[\vec f\mathrm dt-\vec u\mathrm dx]\\
&=f_{right}\Delta t+(-f_{left})\Delta t-(-u_{top})\Delta x-u_{bottom}\Delta x\\
&=(u_{top}-u_{bottom})\Delta x+(f_{right}-f_{left})\Delta t\\
&=0
\end{align}
$$
Different average $u$ and $f\quad \Rightarrow$   different method 
![](image_53.jpeg)
$$
(u^{n+1}_j-u^n_j)\Delta x+(F^{n+\frac{1}{2}}_{j+\frac{1}{2}}-F^{n-\frac{1}{2}}_{j-\frac{1}{2}})\Delta t=0
$$
So there is 
$$
\begin{align}
u^{n+1}_j&=u^n_j-\frac{\Delta t}{\Delta x}(F^{n+\frac{1}{2}}_{j+\frac{1}{2}}-F^{n-\frac{1}{2}}_{j-\frac{1}{2}})\\
F^{n+\frac{1}{2}}_{j+\frac{1}{2}}&=f(u^n_j)?

\end{align}
$$
### The Box Scheme
To solve equation like
$$
u_t+\alpha u_x=0
$$
There is the box scheme
$$
\frac{\delta_t(u^{n+1}_j+u^{n+\frac{1}{2}}_{j+1})}{2\Delta t}+\frac{\alpha \delta _x(u^n_{j+\frac{1}{2}}+u^{n+1}_{j+\frac{1}{2}})} {2\Delta x}=0
$$
Consider $u_t+f_x=0$, we have
$$
\begin{align}
\frac{\delta_t(u^{n+1}_j+u^{n+\frac{1}{2}}_{j+1})}{2\Delta t}+\frac{\delta_x(F^n_{j+\frac{1}{2}}+F^{n+1}_{j+\frac{1}{2}})} {2\Delta x}=0
\end{align}
$$
Apparently it‘s a kind of the finite volume scheme
![](_image/应用数值计算_image_37.jpeg)
$$
\begin{align}
(u^{n+1}_j-u^n_j+&u^{n+1}_{j+1}-u^n_{j+1})\frac{\Delta x}{2}
\\&+(F^n_{j+1}-F^n_j+F^{n+1}_{j+1}-F^{n+1}_j)\frac{\Delta t}{2}
=\\
\frac{u^{n+1}_j+u^{n+1}_{j+1}}{2}\Delta x&-\frac{u^n_j+u^n_{j+1}}{2}\Delta x
\\&+\frac{F^n_{j+1}+F^{n+1}_{j+1}}{2}\Delta t-\frac{F^n_j+F^{n+1}_j}{2}\Delta t
=0
\end{align}
$$


### Leap-frog scheme

![](_image/应用数值计算_image_38.jpeg)
$$
\frac{U^{^{n+1}_j}-U^{n-1}_j}{2\Delta t}+\frac{f(U^n_{j+1})-f(U^n_{j-1})}{2\Delta x}=0
$$
$$
U^{n+1}_j=U^{n-1}_j-(a\Delta t/\Delta x)[U^n_{j+1}-U^n_{j-1}]
$$
In general, we just have value of $U_0$. This method need ==additional== data (value of $U_1$) to initialize. By using method like Lax-Wendroff scheme, we can get value of $U_1$.

# Lecture 11
For the Poisson equation
$$
-\nabla^2u=f
$$

### Triangular element matrices


To map the stiffness matrix A from $\triangle_*$ onto $\triangle_k$, we define
$$
\begin{align}
x(\xi,\eta)=x_1\chi_1(\xi,\eta)+x_2\chi_2(\xi,\eta)+x_3\chi_3(\xi,\eta)\\
y(\xi,\eta)=y_1\chi_1(\xi,\eta)+y_2\chi_2(\xi,\eta)+y_3\chi_3(\xi,\eta)
\end{align}
$$
Where
$$
\begin{align}
\chi_1(\xi,\eta)=1-\xi-\eta\\
\chi_2(\xi,\eta)=\xi\\
\chi_3(\xi,\eta)=\eta
\end{align}
$$
So we can transform derivatives
$$
\begin{bmatrix}
\frac{\partial \varphi}{\partial \xi}\\
\frac{\partial \varphi}{\partial \eta}

\end{bmatrix}
=\begin{bmatrix}
\frac{\partial x}{\partial \xi}&\frac{\partial y}{\partial \xi}\\
\frac{\partial x}{\partial \eta}&\frac{\partial y}{\partial \eta}
\end{bmatrix}
\begin{bmatrix}
\frac{\partial \varphi}{\partial x}\\
\frac{\partial \varphi}{\partial y}
\end{bmatrix}
$$
![](_image/应用数值计算_image_39.jpeg)

$$
\triangle_*=\frac{1}{2}
$$
$$
\begin{align}
\int_{\triangle} 1=&\int_{\triangle_*}|J|=\triangle=\frac{1}{2}|J|\\
&|J|=2\triangle
\end{align}
$$
For triangular element matrices, there are three points, so we can make
$$
\begin{align}
x(\xi,\eta)&=x_1\kappa_1+x_2\kappa_2+x_3\kappa_3\\
y(\xi,\eta)&=y_1\kappa_1+y_2\kappa_2+y_3\kappa_3\\
\end{align}
$$
$$
\begin{bmatrix}
x\\y\\1
\end{bmatrix}
=\begin{bmatrix}
x_1&x_2&x_3\\
y_1&y_2&y_3\\
1&1&1
\end{bmatrix}
\begin{bmatrix}
\kappa_1\\
\kappa_2\\
\kappa_3
\end{bmatrix}
$$
$$
\begin{bmatrix}
\kappa_1\\
\kappa_2\\
\kappa_3
\end{bmatrix}
=\frac{1}{|J|}\begin{bmatrix}
x_1&x_2&x_3\\
y_1&y_2&y_3\\
1&1&1
\end{bmatrix}^{-1}
\begin{bmatrix}
x\\
y\\
1
\end{bmatrix}
$$


# Lecture 12
### Square Element Matrice 
For  the equation
$$
\begin{cases}
-\nabla^2u=1\\
u=0
\end{cases}
$$

$$
\Phi_i=ax+by+c+dxy=
\begin{cases}
1,\quad x=i\\
0,\quad x\neq i
\end{cases}
$$
![](image_55.jpeg)
For simple computing, make transformation as like
$$
\begin{align}
\chi_1(\xi,\eta)=\frac{(\xi-1)(\eta -1)}{4}\\
\chi_2(\xi,\eta)=-\frac{(\xi+1)(\eta -1)}{4}\\
\chi_3(\xi,\eta)=\frac{(\xi+1)(\eta +1)}{4}\\
\chi_4(\xi,\eta)=-\frac{(\xi-1)(\eta +1)}{4}
\end{align}
$$

Have a mapping as follows:
$$
\begin{align}
x(\xi,\eta)=x_1\chi_1+x_2\chi_2+x_3\chi_3+x_4\chi_4\\
y(\xi,\eta)=y_1\chi_1+y_2\chi_2+y_3\chi_3+y_4\chi_4\\
\end{align}
$$

$$
\begin{align}
a_{ij}&=\int_\square \frac{\partial \Phi_i}{\partial x}\cdot \frac{\partial \Phi_j}{\partial x} + \frac{\partial \Phi_i}{\partial y}\cdot \frac{\partial \Phi_j}{\partial y}\mathrm dx\mathrm dy\\
&=\int_{\square^*}\frac{\partial \kappa_i}{\partial x}\cdot \frac{\partial \kappa_j}{\partial x} + \frac{\partial \kappa_i}{\partial y}\cdot \frac{\partial \kappa_j}{\partial y}\ |J|\ \mathrm dx\mathrm dy\\
&=\int_{\square^*}[(\frac{\partial \kappa_i}{\partial \xi}\frac{\partial \xi}{\partial x}+\frac{\partial\kappa_i}{\partial \eta}\frac{\partial\eta}{\partial x})(\frac{\partial \kappa_j}{\partial \xi}\frac{\partial \xi}{\partial x}+\frac{\partial\kappa_j}{\partial \eta}\frac{\partial\eta}{\partial x})\\&\qquad\qquad+(\frac{\partial \kappa_i}{\partial \xi}\frac{\partial \xi}{\partial y}+\frac{\partial\kappa_i}{\partial \eta}\frac{\partial\eta}{\partial y})(\frac{\partial \kappa_j}{\partial \xi}\frac{\partial \xi}{\partial y}+\frac{\partial\kappa_j}{\partial \eta}\frac{\partial\eta}{\partial y})|J|\mathrm d\xi \mathrm d\eta
\end{align}
$$
Where
$$
J=
\begin{bmatrix}
\frac{\partial x}{\partial \xi}&\frac{\partial y}{\partial \xi}\\
\frac{\partial x}{\partial \eta}&\frac{\partial y}{\partial \eta}\\
\end{bmatrix}
$$
$$
J^{-1}=
\begin{bmatrix}
\frac{\partial \xi}{\partial x}&\frac{\partial \eta}{\partial x}\\
\frac{\partial \xi}{\partial y}&\frac{\partial \eta}{\partial y}\\
\end{bmatrix}
$$