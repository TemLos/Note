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





























# Lecture 4 Stats

# Lecture 5 Recombination & Generation

# Lecture 6 Transport

# Second Part —— Device
# Lecture 7 PN Junctions

![[image_218.png|242]]

## Band Diagram in Equilibrium
### Depletion Approximation
PN Junction consists of P-type and N-type piece.

![[image_221.png]]

Consider diffusion dirved by gradients:
$$
\begin{align*}
J_{p,diff}=-qD_{p}\frac{dp}{dx}\\
J_{n,diff}=-qD_{n}\frac{dn}{dx}
\end{align*}
$$
After diffusion, dopers lose electrons and become $N_{D}^{+}$, accepters get electrons and become $N_{A}^{-}$
And it will result in a barrier across the depletion region which is also called _space charge region_

![[image_222.png]]
![[image_220.png]]

$$
\begin{align*}
J_{n}=q\mu _{n}n\xi -qD_{n}\frac{dn}{dx}=n\mu_{n}\frac{dE_{Fn}}{dx}\\
J_{p}=q\mu _{p}p\xi -qD_{p}\frac{dp}{dx}=n\mu_{n}\frac{dE_{Fp}}{dx}
\end{align*}
$$

When calculate depletion region width, to make it easy to understand, usually use _depletion approximation_.
In depletion approximation, there are only ionization center, and no free electrons, thus no generation and recombination.

Free carrier concentration under depletion approximation
$$
n(x)=\begin{cases}
\frac{n^{2}_{i}}{N_{A}}, x\lt -|x_{p}| \\
0, -|x_{p}|\lt x \lt |x_{n}| \\
N_{D}, x\gt |x_{n}|
\end{cases}
$$
$$
p(x)=\begin{cases}
0, x\lt-|x_{p}| \\
-N_{A}, -|x_{p}|\lt x\lt 0 \\
+N_{D}, 0\lt x\lt |x_{n}| \\
0, x\gt |x_{n}|
\end{cases}
$$

_Note_ : Displacement is continuous across the interface ,but field need not to be. 
Because of uneven ionic charge in depletion region, so field can be discontinuous.
Because of free electricity can't be discrete, so displacement should be continuous.

![[image_223.png]]

For 

### Homo-Junction
![[9ece81aeec071bfccd0d409a5ff0386.jpg]]

1. $\chi_{e}$ : Electron Affinity
2. $\Phi_{bi}$ : Building-in voltage approx to _0.7V_
		$q\Phi_{bi}=kTln\frac{N_{A}N_{D}}{N_{V}N_{C}exp(\frac{-E_{g}}{kT})}+(\xi_{p}-\xi_{n})=kTln\frac{N_{A}N_{D}}{n^{2}_{i}} = E_{Fn}-E_{Fp}$
1. $W_{D}$ : Diffusion width
$$
	W_{D}=\sqrt{(\frac{1}{N_{A}}+\frac{1}{N_{D}})\frac{2q\Phi_{bi}}{\varepsilon_{si}}}  
$$
3. $\Phi_{WF}$ : Work-function
4. $E_{g}$ : Band gap
5. $E_{c}$ : Carrier band level
6. $E_{v}$ : Value band level
7. $E_{F}$ : Fermi-level
8. $\Delta E$ : Difference between $E_{F}$ and $E_{c}$ or $E_{v}$. Depends on doping.
$$
\begin{cases}
\Delta E_{1}=kTln\frac{N_{A}}{p} \\
\Delta E_{2}=kTln\frac{n}{N_{D}}
\end{cases}
$$


### Hetero-Junction

## Band Diagram of Homo-Junction with Bias
### Forward Bias

### Reverse Bias












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

