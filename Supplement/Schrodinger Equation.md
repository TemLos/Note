# Wave Function
## Plane Wave and Sphere Wave
## Equation Derivation
$$
\begin{align*}
\frac{\partial^{2}y}{\partial t^{2}}=\nu ^{2}\frac{\partial^{2}y}{\partial x^{2}}
\end{align*}
$$
With solution:
$$
\begin{align*}
y(x,t) &= y_{0}e^{i(kx-\omega t)}\\
\omega^{2} &= \nu^{2}k^{2}
\end{align*}
$$

**Why to take the second order derivative of time or position?**

# Time-dependent Schrdinger Equation
Schrodinger equation is used to find dispersion relationship or E-k relationship, which is related to energy band.
## Equation
$$
\begin{align*}
\frac{\partial^{2}y}{\partial t^{2}}=\nu ^{2}\frac{\partial^{2}y}{\partial x^{2}}
\end{align*}
$$
For plane wave
$$
\begin{align*}
y(x,t)&= Acos(kx-\omega t)+Bsin(kx-\omega t)\\
\omega &= \nu k\\
\nu&= \lambda f  
\end{align*}
$$
To use wave function to describe a **free particles** in microscopic realm, we have de Broglie’s Law and Plank's Law
$$
\begin{align*}
E=hf=\hbar \omega\\
p=\frac{h}{\lambda}=\hbar k
\end{align*}
$$
So we have particle dispersion relationship
$$
\begin{align*}
E=\frac{1}{2}mv^{2}=\frac{m^{2}v^{2}}{2m}=\frac{p^{2}}{2m}\\
E=hf=\hbar \omega\\
p=\frac{h}{\lambda}=\hbar k\\
\hbar \omega=\frac{\hbar^{2}k^{2}}{2m}
\end{align*}
$$
So the wave function we need should satisfy the $\omega-k$ condition.
Consider $\phi(x,t)=e^{i(\omega t-kx)}$, we have
$$
\begin{align*}
\frac{\partial y}{\partial t}&= -i \omega e^{-i(\omega t-kx)}\\\\
\frac{\partial^{2}y}{\partial x^{2}}&= -k^{2}e^{-i(\omega t-kx)}
\end{align*}
$$
Bring back  to dispersion relationship
$$
\begin{align*}
\hbar \omega&= \frac{\hbar^{2}k^{2}}{2m}\\
i\hbar \frac{\partial \phi}{\partial t}&= \frac{-\hbar^{2}}{2m}\frac{\partial ^{2}y}{\partial x^{2}}
\end{align*}
$$
If consider particle in 3-dimension with electrostatic potential power
$$
\begin{align*}
i\hbar \frac{\partial \phi}{\partial t}&= (\frac{-\hbar^{2}}{2m}\nabla^{2}+U)\phi
\end{align*}
$$
**How to understand $\phi$ ?**
![[Nano Electronics#^sch]]
## Operator
An operator can be consider as a matrix.
Use an operator to represent the corresponding physical quantity measured.
$$
\begin{align*}
\hat H &= \frac{-\hbar^{2}}{2m}\nabla^{2}+U\\
\hat p &= -i\hbar \nabla\\
\hat \omega &= i\frac{\partial}{\partial t}\\
\hat x &= x\\
\end{align*}
$$
$$
\rm Commutator\ [\hat A\ \hat B]= \hat A\hat B-\hat B \hat A
$$
Schrodinger equation can also be written as 
$$
\hat \omega\hbar \phi=\hat H \phi
$$
# Time-independent Schrodinger Equation
Find a seperation of variables when potential power is independent of time.
$$
\phi(x,t)=\varphi (x) T(t)
$$
$$
\begin{align*}
i\hbar \frac{\partial \phi}{\partial t}&= (\frac{-\hbar^{2}}{2m}\nabla^{2}+U)\phi\\
i\hbar \varphi T'&= \frac{-\hbar^{2}}{2m}\nabla^{2}\varphi''T+U\varphi \cdot T\\
i\hbar \frac{T'}{T}&= \frac{-\hbar^{2}}{2m}\nabla^{2} \frac{\varphi''}{\varphi}+U
\end{align*}
$$
The left side is function of t, while the right side is function of x. To make them equal, they both need to be a constant.
Take constant E
$$
\begin{cases}
i\hbar \frac{T'}{T}= E \\
\frac{-\hbar^{2}}{2m}\nabla^{2} \frac{\varphi''}{\varphi}+U= E
\end{cases}
\Rightarrow
\begin{cases}
T(t)=Ce^{\frac{-i}{h}Et} \\
\frac{-\hbar^{2}}{2m}\nabla^{2}\varphi''+U\varphi= E\varphi
\end{cases}
$$




