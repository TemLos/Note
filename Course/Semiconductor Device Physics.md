# First Part —— Semiconductor
# Lecture 2 Elements of Quantum Mechanics
![[Schrodinger Equation]]
## Wave Equation
Classical (Newtonian) Mechanics
$$
\begin{align*}
F=m_{0}a&= m_{0}\frac{d^{2}x}{dt^{2}}= m_{0}\frac{dv}{dt}\\
p&= m_{0}v\\
F&= \frac{dp}{dt}
\end{align*}
$$
For electrostatic force
$$
\begin{cases}
\frac{mv^{2}}{r}=\frac{Zq^{2}}{4\pi\varepsilon_{0}r^{2}} \\
p=mv=\hbar/\lambda \rm\\
2\pi r=n\lambda
\end{cases}
\Rightarrow
\begin{cases}
E_{k}=\frac{mv^{2}}{2}=\frac{Zq^{2}}{8\pi\varepsilon_0r} \\
E_{p}=-\frac{Zq^{2}}{4\pi\varepsilon_{0}r} \\
E=E_{p}+E_{k}=-\frac{Zq^{2}}{8\pi\varepsilon_0r}
\end{cases}
$$
so
$$
E_{electron}=-\frac{Zq^{2}}{8\pi\varepsilon_0r}
$$
To calculate $r$
$$
\begin{cases}
n\lambda=2\pi\lambda \\
p=mv=h/\lambda
\end{cases}
\Rightarrow
mvr=\frac{nh}{2\pi}=n\hbar
$$
$$
\begin{align*}
E_{k}&= \frac{m^{2}v^{2}r^{2}}{2mr^{2}}=\frac{n^{2}\hbar^{2}}{2mr^{2}}=\frac{Zq^{2}}{8\pi\varepsilon_{0}r}\\
r&= \frac{4\pi\varepsilon_{0}n^{2}\hbar^{2}}{Zq^{2}m}
\end{align*}
$$
so
$$
\begin{align*}
E_{k}&= \frac{-mZ^{2}q^{4}}{32\pi^{2}\varepsilon_{0}^{2}n^{2}\hbar^{2}}=\frac{-mZ^{2}q^{4}}{8\varepsilon_{0}^{2}n^{2}h^{2}}\\
&= \frac{Z^{2}}{n^{2}}\frac{-mq^{4}}{8\varepsilon_{0}h^{2}}\\
&= \frac{Z^{2}}{n^{2}}E_{1}\\\\
E_{1}&= -13.6\ eV
\end{align*}
$$
For wave equation
$$
\frac{\partial^{2}y}{\partial t^{2}}=\nu^{2}\frac{\partial^{2}y}{\partial x^{2}}
$$
It has solution
$$
\begin{align*}
y(x,t)&= y_{0}e^{i(kx-\omega t)}\\
\omega^{2}&= \nu^{2}k^{2}
\end{align*}
$$
**To be supplemented**
Considered quantum theory, modeled after the wave equation
$$
\begin{cases}
E=hf=\hbar \omega\ \rm(Planck's\ Law) \\
p=\frac{h}{\lambda}=\hbar k\ \rm (de\ Broglie's\ Law) \\
E=\frac{p^{2}}{2m}+U\ \rm(energy\ of\ particle)
\end{cases}
$$
We can find Schrodinger Equation
$$
i\hbar  \frac{\partial\Psi}{\partial t}=(\frac{-\hbar^{2}\nabla^{2}}{2m}+U)\Psi
$$
Where $\Psi$ ist prbability density of finding particle $\int P(x,t)dx=1$

With solution when free particle (U=0)
$$
\Psi=Ae^{i(kx-\omega t)} =Ae^{i(px-Et)/\hbar}
$$
Bring back to the equation, we then get the dispersion releationship
$$
E=\frac{p^{2}}{2m}=\frac{\hbar^{2}k^{2}}{2m} 
$$

In Shcrodinger Equation, we have usual operators

# Lecture 3 Band Structure

# Second Part —— Device
# PN Junctions


















$$
\frac{\partial^{2}\psi_i}{\partial x^{2}}=-\frac{q}{\vec\varepsilon}[N_{D}-n(x)]
$$
$$
\vec \varepsilon q\frac{\partial \psi_i}{\partial x}=\sqrt{\frac{2qN_{D}}{\varepsilon_{si}}[\psi_{i}(x)-\psi_{io}]+\frac{kT}{q}[e^{q(\psi_{io}-\psi_{i}(x))}]}
$$

$$
C_j=\sqrt{\frac{\varepsilon_{Si} q(\frac{N_{A}N_{D}}{N_{A}N_{D}})}{2(|V_{r}|\Phi_{b}-\frac{2kT}{q})}}
$$
$$
\beta=\frac{I_{c}}{I_{b}}=\frac{J_{n,diff}}{J_{p,diff}}
$$
真空能级 禁带宽度
Generally, take the only current inside BJT are $J_{BEn}$ and $J_{BEp}$
Total current doesn’t change,  but distribution changes.
	By distributing the current, we resize the current amplification.
