---
title: Nano Electronics
tags:
  - Note
  - Hardware
  - "#device"
---
# Lecture 1 Course Briefing
**HOW TO CONNECT TO YOUR RESEARCH**
- Why concern on channel mostly？
    Channel determins electrical characters.
- The Moores’ law states
    the complexity of an integrated circuit, with respect to minimum component cost, will double in about 18 mouths.
-  significant 32nm point
    - above 32nm
        traditional planar CMOS
    - below 32nm(22nm?)
        3D transistor：FinFET、gate-all-around FET
- Hyper- scaling
- Technical difficulty
    - Exponential increase in Leadkage
    - Power & Power Density
    - Variation in Process Parameters
- Solution
    - III-IV materials
        Ge for PMOS
        (In)GaAs for NMOS
    - 2D materials
    - Silicon Photonics
        Use Photon instead of elecrtrons
    - Spin Electronics
        Use electron to burden imformation

TA:yaoshan2022@shanghaitech.edu.cn
mean free path of Si : 50nm
Consider mean free path = 50nm, when channel length < 50nm, how about scatterring?

**Ohm’ s law**
$$
\begin{align}
R=\rho \frac{L}{A} \\
I=\frac{V}{R}=\frac{VA}{\rho L} \\
\frac{I}{A}=J=\rho \frac{V}{L}=\rho E \\
\end{align}
$$
consider 
$$
\begin{align}
I=\frac{Q}{t}=\frac{neAL}{L/v_d} \\
so J=\frac{I}{A}=nev_d \\\\
n:carrier\ density \\  n=\int^\infty_{-\infty}DoE(\epsilon)f(\epsilon)\mathrm d\epsilon \\\\
v_d: drift\ velocity \\ v_d=\frac{F\tau}{m^*}=\frac{Ee\tau}{m^*}\\
\end{align}
$$
then we have Drude Formula
$$
\begin{cases}
J=nev_d \\
v_d=\mu E,  E=\frac{V}{L}\\
\mu=\frac{v_d}{E}=\frac{e\tau}{m^*}
\sigma=ne\mu
\end{cases}
$$
- Diffusive Transport
    - $0.1mm\rightarrow 0.1\mu m$
    - there is obvious lattice scattering and ion scattering
- Ballistic Transport
    - $0.1\mu m\rightarrow 10nm$ 
    - No scatter
- Semi-classical approach
    - $0.1mm \rightarrow 10nm$
- Quantum approach
    - blow or equal 1nm, L comparable to atom radius


**kwant**

# Lecture 2 The New Perspectives
$$D(E)\propto E^{\frac{1}{2}}$$
![](image_63.jpg)
Consider T=300k, we have
$KT\approx 25meV=25\times 10^{-3}\times 1electron(1.6\times 10^{-19}) \times 1V$

Hard to understand if we say that electric field drives electrons, so we use Femi function instead.
![](image_64.jpg)

After flowing, both Femi functions becomes $\mu_2+\frac{qV}{2}$ ， and for the above situation, we think f(E) = 1. **Consider D(E) as diameter of water pipe.** 

Use Infinitesimal Method
$$
\frac{I}{q}\times t(E)=\frac{D(E)\mathrm dE}{2}
$$
$$
\begin{align}
I&=
\int^\infty_{-\infty}\mathrm dE\frac{qD(E)}{2t(E)}\times(f_1(E)-f_2(E))
\end{align}
$$
According to
$$G(E)=\frac{q^2D(E)}{2t(E)}$$
We have
$$
\begin{align}
I=\frac{1}{q}\int^{\infty}_{-\infty}\mathrm dE&\cdot G(E)(f_1(E)-f_2(E))\\
\end{align}
$$
$$
\begin{align}
f_1(E)-f_2(E)&=f_1(E,\mu_1)-f_2(E,\mu_2)\\
consider\ V\ &bias\ is\ small,\ Linear\ response\ approximation
\\&\approx (\frac{\delta f}{\delta \mu})(\mu_1-\mu_2)
\end{align}
$$
Further derive
$$f(E)=\frac{1}{1+e^{(E-\mu)/kT}}=\frac{1}{1+e^x},\quad x=\frac{E-\mu}{kT}$$
![](image_65.jpg)
- Electrons near Femi energy level contribute to electrons flow mostly.
- 4kT is used to make normalization.
- Both y axis are $\frac{E-\mu}{kT}$


###### Ballistic Transport

As for Ballistic Transfort
$$
\frac{DqV}{2}=\frac{I}{q}\times t\Rightarrow G=\frac{I}{V}=\frac{q^2D}{2t}
$$
$$G_B=\frac{q^2D}{2t}=\frac{q^2D\vec{v}}{2L}\propto A$$
![](image_66.jpg)
It seems that G-A curve is linear, but in fact it behavior like as follows:
![](image_67.jpg)
because $G_B=\frac{q^2}{h}\times M$, M is number of modes, and h is Planck constant.
**How to calculate M?**
$M=\frac{A}{l}$, $l$ is wave length of electrons.
The **less** $M$ the material is, the **easier** electric field penetrate the material. 
**Why is difference between Sharvin Resistance and experiment?**
Consider $\frac{D}{2t}=\frac{M}{h}$, there is $\frac{D}{t_B}\times h\propto M$, $t_B=\frac{L}{\bar{v}}$ 
D(E) is Density of Energy which means $\frac{number\ of\ state }{energy}$, so we know $\frac{h}{t}$ means energy(Heisenberg Uncertainty Principle).
#### Diffusive Transport
As for diffusive transport, we define diffusive constant $\bar{D}$, so we have
$$t_D=\frac{L^2}{2\bar{D}}$$
$$G_=\frac{q^2D}{2t}=\frac{A}{L}q^2\frac{D}{AL}\bar{D}=\frac{A}{L}\sigma$$
$$
\sigma = q^2\frac{D}{AL}\bar D
$$
**How to calculate $\bar{D}$**
Consider the concentration gradient difference, it’ s $V_{thermal}$ that drives electrons move. Consider **mfp for backscattering** $\lambda$, so there is 
$$
\begin{aligned}
V_{thermal}=\frac{kT}{e}\\
E_{themal}=\frac{kT}{e\lambda}
\end{aligned}
$$
$$
\begin{align}
v_{diff}=\mu E=\mu\frac{kT}{e}\frac{1}{\lambda}\\
\lambda=v_{diff}\cdot \tau\\
\bar{D}=v^2_{diff}\tau=\mu\frac{kT}{e}
\end{align}
$$
Now we know how to connect ballistic to diffusive transport
$$
\begin{align}
t&=\frac{L}{\bar{v}}+\frac{L^2}{2\bar D}\\
&=t_B(1+\frac{L\bar v}{2\bar D})\\
&=t_B(1+\frac{L}{\lambda}),\qquad where\ \lambda = \frac{2\bar D}{\bar v}
\end{align}
$$
It start with ballistic transport, but there is always obstructs, which make it spend extra $\frac{L}{\lambda}$ second.
define **Transmision**
$$
\begin{align}
T&=\frac{\lambda}{\lambda+L}\\
&=\frac{\lambda}{L}\quad(L\gg \lambda)
\end{align}
$$
we have
$$
\begin{align}
G&=G_B\cdot T\\
t&=t_B/T
\end{align}
$$
Now we calculate $G$
$$
\begin{align}
G=\frac{G_B}{1+\frac{L}{\lambda}}&=\frac{G_B\lambda}{L+\lambda}\\
&=\frac{\frac{q^2D\bar D}{L}}{L+\lambda}\\
&=\frac{\sigma A}{L+\lambda}
\end{align}
$$
Consider ballistic transport, we have
$$
\sigma A=G_B\lambda
$$

# Lecture 3 Energy Band Model
#### E(p) or E(k) relationship
As for kinetic energy  of electrons
$$
\begin{align}
E_K&=\frac{1}{2}m_0v^2 \\
&=\frac{(m_0v)^2}{2m_0}\\
&=\frac{1}{2}\frac{p^2}{m_0}\\
where\quad p&=hk=m_0v
\end{align}
$$
if consider additional voltage, we know
$$
E=\frac{p^2}{2m_0}+U
$$
#### Number of modes
DeBrogile wave length
$$
\lambda_{De Brogile}=\frac{h}{p}
$$
Consider channel length and electric wave length
$$
L=n\frac{h}{p_n}\rightarrow p_n=n\frac{h}{L}(Periodic\ Boundary\ Condition)
$$
which means $\frac{h}{L}$ is step length
State number
$$
N(p)=\frac{2p}{h/L}
$$
consider two dimensions and three dimensions
$$
\begin{align}
2D:\ N(p)=\frac{\pi p ^2}{(h/L)(h/W)}\\
3D:\ N(p)=\frac{4\pi p^3/3}{(h/L)(h/A)}
\end{align}
$$
To make summery
$$
N(p)=\left(\frac{p}{h}\right)^d\{2L\ ,\ \pi WL\ ,\ \frac{4\pi}{3}AL\}
$$
**How to get D(E) if I have N(p)?**
$$
\begin{align}
N(p)&=Ap^d\\\\
&\downarrow\quad E(p)=E_C+Bp^{\alpha}\\\\
N(E)&=A(\frac{E-E_C}{B})^{d/\alpha}\\\\
&\downarrow \quad D(E)=\frac{\mathrm dN(E)}{\mathrm dE}\\\\
D(E)&\sim (E-E_C)^{\frac{d}{\alpha}-1}
\end{align}
$$
As for ballistic conductance
$$
N(p)=\left(\frac{p}{h}\right)^d\{2L\ ,\ \pi WL\ ,\ \frac{4\pi}{3}AL\}
$$
$$
\begin{align}
\frac{\mathrm dN}{\mathrm dp}=p\times\frac{\mathrm dN}{\mathrm dE}\frac{\mathrm dE}{\mathrm dp}&=d\frac{p^{d-1}}{h^d}\{2L,\pi WL,\frac{4\pi}{3}AL\}\times p\\
p\times Dv&=Nd
\end{align}
$$
$$
\begin{align}
G_B&=q^2\frac{D\bar{v}}{2L}=\frac{q^2}{h}M\\
M&=\frac{hDv}{2L}\{1,\frac{2}{\pi},\frac{1}{2}\}\\
&=\frac{h}{2L}\frac{N}{p}d\{1,\frac{2}{\pi},\frac{1}{2}\}\\
&=\frac{1}{2L}(\frac{p}{h})^{d-1}\{2L,4WL,2\pi AL\}\\
&=(\frac{p}{h})^{d-1}\{1,2W,\pi A\}
\end{align}
$$
At low temperature, it’s 
$$
M=(\frac{p}{h})^{d-1}\int(\{1,\frac{W}{h/2p},\frac{\pi}{4}\frac{A}{(h/2p)^2}\})
$$
#### Electron density
$$
\begin{align}
N_0=\int^\infty_{-\infty}\mathrm dE\ D(E)f_0(E)
\end{align}
$$
![](image_130.jpeg)

$$
\begin{align}
N(p)&=\left(\frac{p}{h}\right)^d\{2L\ ,\ \pi WL\ ,\ \frac{4\pi}{3}AL\}\\
n(p)&=\left(\frac{p}{h}\right)^d\{2\ ,\pi\ ,\frac{4\pi}{3}\}
\end{align}
$$
![](image_131.jpeg)
#### Conductivity versus n??
#### Quantum Capacitance
In sub-threshold region, consider **Boltzmann approximation**
![](image_132.jpeg)
$$
\begin{align}
N
&=\int^\infty_{-\infty} \mathrm dE\ D(E)f_0(E+U)\\
&=\int^\infty_{-\infty} \mathrm dE\ D(E)e^{-(E+U-\mu)/kT}
\end{align}
$$
$$
N\approx N_0 e^{-U/kT}\rightarrow ln\frac{N}{N_0}\approx -\frac{U}{kT}\\
$$
$$
U=\beta(-qV_g)\rightarrow \mathrm d(ln\frac{N}{N_0})\approx\frac{q}{kT}\mathrm dV_g\beta
$$
$$
\mathrm dV_G\approx\frac{kT}{\beta q}\mathrm d(ln\frac{N}{N_0})
$$
Which means $\frac{N}{N_0}$ changes with $V_G$ changing in **sub-threshold region**(Sub-threshold Swing).
When T=300k, $\frac{kT}{q}\approx 25mV$, $ln\frac{N}{N_0}\approx 2.3$, that is called **Boltzmann truancy**.

Consider $V_t\le V_g$
![](image_133.jpeg)
$$
N=\int^\infty_\infty \mathrm dE\ D(E)f_0(E+U)
$$
$$
\frac{\mathrm dN}{\mathrm dU}=\int^\infty_\infty\mathrm dE\ D(E)\frac{\partial f_(E+U)}{\partial E}=-D_0
$$
U: enery.  D: dense of state
Define **quantum capacitance**
$$
\frac{\mathrm d(qN)}{\mathrm d(\frac{U}{-q})}=q^2D_0=C_Q
$$
To relationship between $V_G$ and $U$
$$
U=\beta(-qV_G)+U_0(N-N_0)
$$
$$
\begin{align}
\frac{\mathrm dU}{\mathrm d(-qV_G)}&=\beta + U_0\frac{\mathrm dN}{\mathrm d(-qV_G)}\\
&=\beta-U_0D_0\frac{\mathrm dU}{\mathrm d(-qV_G)}
\end{align}
$$
Define **electrostatic capacitance** 
$$
C_E=\frac{q^2}{U_0}
$$
So there is 
$$
\frac{\mathrm U}{\mathrm dV_G}=\frac{\beta}{1+U_0D_0}=\frac{C_E}{C_E+C_Q}\beta
$$
#### Nano Transistor
With $V_{DS}$ improving, for long channel length device, current won’t keep increasing due to band gap(number of modes doesn’t change when $\mu 2$goes into band gap)
![](image_134.jpeg)
note : qV is $V_{DS}$
For short channel device, consider **CLM(Channel Length Modulation)**
$$
U=U_0(N-N_0)+\beta(-qV_G)+\alpha(-qV_{DS})
$$
![](image_135.jpeg)
**?self-consistent?**
###### Drift Diffusion Equation
$$
I=-\frac{\sigma (z)\mathrm\ d\mu}{q\ \mathrm dz}\qquad \frac{\mathrm dI}{\mathrm dz}=0
$$
###### Poisson Equation
$$
\frac{\mathrm d}{\mathrm dz}\left(\varepsilon \frac{\mathrm dU}{\mathrm dz}\right)=q^2(n-n_0)
$$
# Lecture 4 Voltage
As for current dense, it don‘t depend on only electrostatic potential, but electrochemical potential.
$$
J\neq\sigma_0E=\frac{\sigma_0\ \mathrm dU}{q\ \mathrm dz}
$$
$$
J=- \frac{\sigma_0}{q}\frac{\mathrm d\mu}{\mathrm dz}=—\frac{\sigma_0}{q}\frac{\mathrm dU}{\mathrm dz}-q\frac{\mathrm dn}{\mathrm dz}
$$
[[#Lecture 2 The New Perspectives]]
>  **Another view of current in channel**
> ![](image_64.jpg)
> Electrochemical potensial $\mu_1$ want to make the channel into equilibrium, so it makes electrons flow into the channel, $\mu_2$ also want to makes the channel into equilibrium, so it makes electrons flow out of channel. Then current appears.
## Boundary condition

$$
I=-\frac{\sigma_0A}{q}\frac{\mathrm d\mu}{\mathrm dz}=\frac{1}{q}\frac{\sigma_0A}{L}(\mu_1-\mu_2)
$$
At first, people think the  boundary condition should be $\begin{cases} \mu(z=0)=\mu_1\\ \mu(z=L)=\mu_2\end{cases}$, but it eventually proved wrong in very short channel length.
so the boundary condition is correct when $L\gg \lambda$ and when $L\ll \lambda$, we should revive the model as follows:
![](image_7.jpeg)
To revive boundary condition, we consider current as 
$$
I=\frac{1}{q}\frac{\sigma_0A}{L+\lambda}(\mu_1-\mu_2)
$$
Then we find a new boundary condition:
$$
\begin{cases}
\mu(z=0)=\mu_1-\frac{qIR_B}{2}\\
\mu(z=L)=\mu_2+\frac{qIR_B}{2}
\end{cases}
$$
![](image_8.jpeg)
**Why are resistors next to the channel?**
![[image_136.jpeg]]
For constant point X in the channel, we can consider the curve as _average of voltage drop_ from $\mu_1$ to X and from X to $\mu_2$.  
The voltage should not associate to potential but to filling level of energy band.
The resistance of the channel cause the slope of the filling level, just like highway with traffic accident.
## Quasi Fermi Levels

### Landauer Formulas
![](image_8.jpeg)
### What a probe measures
An ideal voltage probe doesn’t effect voltage and current, doesn‘t have interaction with carriers in channel, that is, there is no coupling.
$$
\begin{align}
g^+\frac{\mu_P-\mu^+}{q}=g^-\frac{\mu^—-\mu_P}{q}\\
\mu_P={\frac{g^+}{g^++g^-}\mu^+}+\frac{g^-}{g^++g^-}\mu^-
\end{align}
$$
$$
\begin{bmatrix}
I_1\\I_2\\I_3\\I_4\\
\end{bmatrix}
=\frac{1}{q}\begin{bmatrix}
G_{11}&G_{12}&G_{13}&G_{14}\\
G_{21}&G_{22}&G_{23}&G_{24}\\
G_{31}&G_{32}&G_{33}&G_{34}\\
G_{41}&G_{42}&G_{43}&G_{44}\\
\end{bmatrix}
\begin{bmatrix}
\mu_1\\\mu_2\\\mu_3\\\mu_4
\end{bmatrix}
$$
Consider KVL
$$
\begin{align}
\sum_{i=1}^4 G_{ji}&=\sum^4_{i=1}G_{ij}=0\\
G_{ij}&=G_{ji}
\end{align}
$$

### Electrostatic Potential
Difference between electrostatic potential and electrochemical potential:
- Electrostatic potential effects value band
- Electrochemical potential effects Femi level (electrons filling state), consider 0 K case.
$$
\begin{align}
N&=\int^\infty_{-\infty}\mathrm dE\ D(E-U)f(E-\mu)\\
&=\int^\infty_{-\infty}\mathrm dE\ D(E)f(E-\mu+U)\\\\
\delta N&\approx\delta(\mu-U)\times\int^{\infty}_{-\infty}\mathrm dE(-\frac{\partial f_0}{\partial E})D(E) 
\\\\&\Downarrow \ \ \ \rm linear\ \rm approximation\ \rm in\ \rm samll\ \rm region\\
\\\delta n&=\delta (\mu-U)\times D_0
\end{align}
$$
Form the above derive, we know that the difference between $\mu$ and U depend on electron density.
Consider large $D_0$ and small $D_0$
$$
\begin{align}
\nabla^2(\delta U)&=-\frac{q^2(\delta n)}{\varepsilon}\\
&=-\frac{q^2D_0}{\varepsilon}(\delta \mu -\delta U)\\\\
\lambda_s&\equiv \sqrt{\frac{\varepsilon}{q^2D_0}}
\end{align}
$$
Bring $\lambda_s$ into the above equation
$$
(\nabla^2-\frac{1}{\lambda_s})\delta U=-\frac{\delta \mu}{\lambda_s^2}
$$
$$
\lim_{\lambda_s\rightarrow0}\ \delta U\approx \delta \mu
$$
- For large $D_0$
	It‘s hard to improve $\delta (\mu-U)$
	In general, electrostatic potential is equal to electrochemical potential in metal and improving density of electrons is difficult.
- For small $D_0$
![](_image/纳米电子学_image_8.jpeg)
It’s the screening length that smeared electrostatic potential. 
### Boltzmann Equation 
$$
\begin{align}
I&=-\frac{\sigma_0 A}{q}\frac{\mathrm d\mu}{\mathrm dz}\\

J&=-\frac{\sigma_0}{q}\frac{\mathrm d\mu}{\mathrm dz}
\end{align}
$$

Make moment t is in equilibrium, moment $t-\Delta t$ is not in equilibrium.
Make $\Delta t$ as small as possible.
$$
\begin{align}
f(z,p,t)&=f(z-v_z\Delta t,p_z-F_z\Delta t, t-\Delta t)\\
&\approx f(z,p,t)-\frac{\partial f}{\partial t}\Delta t-\frac{\partial f}{\partial z}v_z\Delta t-\frac{\partial f}{\partial p_z}F_z\Delta t\\

\end{align}
$$
So we have
$$
\frac{\partial f}{\partial t}=0
$$
$$
\frac{\partial f}{\partial p_z}F_z\Delta t+\frac{\partial f}{\partial z}v_z \Delta t =-\frac{\partial f}{\partial t}\Delta t=0
$$
Meanwhile, for moment not in equilibrium, consider _relaxation time_ $\tau$
$$
v_z\frac{\partial f}{\partial z}+F_z\frac{\partial f}{\partial p_z}=-\frac{f-\overline f}{\tau}
$$
where we have _Newton’s Law_
$$
\frac{\mathrm dz}{\mathrm dt}=v_z,\quad \frac{\mathrm dp_z}{\mathrm dt}=F_z
$$
Consider _scattering operator_ $S_{OP}$
$$
v_z\frac{\partial f}{\partial z}+F_z\frac{\partial f}{\partial p_z}=S_{OP}f+0
$$
For Quasi Femi Level
$$
f(z,p_z,E)=\frac{1}{1+e^{(E-\mu(z,p_z))/kT}}
$$
$$
\begin{align}
v_z\frac{\partial f}{\partial z}+F_z\frac{\partial f}{\partial p_z}&=-\frac{f-\overline f}{\tau}\\
&=v_z\frac{\partial f}{\partial z}+\frac{\partial p_z}{\partial t}\frac{\partial f}{\partial p_z}\\
&=v_z\frac{\partial f}{\partial z}
\end{align}
$$
$$
v_z\frac{\partial \mu(z,p_z)}{\partial z}=-\frac{\mu(z,p_z)-\overline\mu(z)}{\tau}
$$
$$
\begin{align}
|v_z|\frac{\mathrm d\mu^+}{\mathrm dz}=-\frac{\mu^+-\overline\mu}{\tau}\\
-|v_z|\frac{\mathrm d\mu^-}{\mathrm dz}=-\frac{\mu^--\overline\mu}{\tau}
\end{align}
$$
$$
\overline\mu=\frac{\mu^+-\mu^-}{2}
$$
$$
\frac{\mathrm d\mu^+}{\mathrm dz}=\frac{\mathrm d\mu^-}{\mathrm dz}=-\frac{\mu^+-\mu^-}{2|v_z|\tau}=-\frac{1}{\lambda}\frac{qI}{G_B}
$$
$$
I=-\frac{G_B\lambda}{q}\frac{\mathrm d\mu^+(\mu^-)}{\mathrm dz}=-\frac{\sigma_0A}{q}\frac{\mathrm d\mu^+(\mu^-)}{\mathrm dz}
$$
# Lecture 5 Heat & Electricity
## Seebeck Coefficient
![[image_20.png]]
Difference of temperature cause difference of voltage.
For PMOS, holes moves from cold region to hot, while NMOS moves from hot region to cold(from high energy to low energy level).

![](_image/纳米电子学_image_18.jpeg)
$$
\begin{align}
I&=\frac{1}{q}\int G(E)(f_1(E)-f_2(E))\mathrm dE\\
&\approx G_0\Delta V+G_S\Delta T
\end{align}
$$
where
$$
\begin{align}
G&=\int^\infty_{-\infty}(-\frac{\partial f_0}{\partial E})G(E)\mathrm dE\\
G_S&=\int^\infty_{-\infty}(-\frac{\partial f_0}{\partial E})G(E)\frac{E-\mu_0}{qT_0}\mathrm dE\\
\Delta f&=(-\frac{\partial f_0}{\partial E})\times (\Delta \mu+\frac{E-\mu_0}{T_0}\Delta T)
\end{align}
$$
![](_image/纳米电子学_image_19.jpeg)
Consider open circuit, $I\approx G_0\Delta V+G_S\Delta T= 0$
$$
\begin{align}
S&\equiv\frac{\Delta V}{\Delta T}=\frac{open\ circuit\ voltage}{temperature\ difference}\\&\approx -\frac{G_S}{G_0}=\frac{\int^\infty_{-\infty}(-\frac{\partial f_0}{\partial E})G(E)\frac{E-\mu_0}{qT_0}\mathrm dE}{\int^\infty_{-\infty}(-\frac{\partial f_0}{\partial E})G(E)\mathrm dE}
\end{align}
$$
Where S is Seeback coefficient.
For increasing $\frac{E-\mu_0}{qT_0}$, we need to use insulator or semiconductor, due to large resistance of insulator, usually we use semiconductor.
## Peltier Effect
![](_image/纳米电子学_image_20.jpeg)



Define heat current 
$$
\begin{align}
I_Q&=\frac{1}{q}\int^\infty_{-\infty}\frac{E-\mu_0}{q}G(E)(f_1(E)-f_2(E))\mathrm dE\\
&\approx G_P\Delta V+G_Q\Delta T
\end{align}
$$
where 
$$
\begin{align}
G_P&=\int^{\infty}_{-\infty}(-\frac{\partial f_0}{\partial E})\frac{E-\mu_0}{q}G(E)\mathrm dE\\
G_Q&=\int^{\infty}_{-\infty}(-\frac{\partial f_0}{\partial E})\frac{(E-\mu_0)^2}{q^2T_0}G(E)\mathrm dE\\
\end{align}
$$
_Note: $I_Q$ refers to energy, not current_.
To connect Seebeck effect and Peltier effect
$$
\begin{align}
G&=\int^\infty_{-\infty}(-\frac{\partial f_0}{\partial E})G(E)\mathrm dE\\
G_S&=\int^\infty_{-\infty}(-\frac{\partial f_0}{\partial E})G(E)\frac{E-\mu_0}{qT_0}\mathrm dE\\
G_P&=\int^{\infty}_{-\infty}(-\frac{\partial f_0}{\partial E})\frac{E-\mu_0}{q}G(E)\mathrm dE\\
G_Q&=\int^{\infty}_{-\infty}(-\frac{\partial f_0}{\partial E})\frac{(E-\mu_0)^2}{q^2T_0}G(E)\mathrm dE\\
\end{align}
$$
Kelvin Relation
$$
G_P=T_0G_S
$$
$$
\begin{align}
I&\approx G_0\Delta V+G_S\Delta T\\
I_Q&\approx G_P\Delta V+G_Q\Delta T
\end{align}
$$
$$
\begin{align}
\Delta V&\approx \frac{1}{G_0}I-\frac{G_S}{G_0}\Delta T \\
&=RI+S\Delta T\\\\
I_Q &\approx \frac{G_P}{G_0}I+(G_Q-\frac{G_PG_S}{G_0})\Delta T\\
&=-\Pi I+G_K\Delta T
\end{align}
$$

## Firset Law
$$
N_1+N_2=0
$$
$$
E_1+E_2=0
$$
## Second Law
![[image_53.png]]
$$
\frac{E_1-\mu_1N_1}{T_1}+\frac{E_2-\mu_2N_2}{T_2}\le0
$$
Combine with the first law, we have
$$
N1(\frac{\varepsilon-\mu_1}{T_1}-\frac{\varepsilon-\mu_2}{T_2})\le0
$$
$$
N_1(f_1(\varepsilon)-f_2(\epsilon))\ge 0
$$
Consider landauer formula

![[#Landauer Formulas]]

$$
I\sim f_1(\varepsilon)-f_2(\varepsilon)
$$
For multi contacts device, it can be

![[image_54.png]]
$$
\begin{cases}
E_0+E_1+E_2=0\\\\
\frac{E_0}{T_0}+\frac{E_1-\mu_1N_1}{T_1}+\frac{E_2-\mu_2N_2}{T_2}\le 0
\end{cases}
$$

if $T_1 = T_2=T_0$
$$
{E_0}+{E_1-\mu_1N_1}+{E_2-\mu_2N_2}\le 0
$$
$$
\mu_1N_1+\mu_2N_2\ge0
$$
$\mu_1N_1+\mu_2N_2$ is the energy we take from battery.

Now, let's derive it from the opposite direction.

![[image_55.png]]

$$
\begin{align}
\frac{P(E_1,N_1)}{P_r(E_1,N_1)}\cdot \frac{P(E_2,N_2)}{P_r(E_2,N_2)}\cdot \frac{P(E_0)}{P_r(E_0)}\ge 1
\end{align}
$$
$$
exp(-\frac{E_0}{T_0}-\frac{E_1-\mu_1N_1}{T_1}-\frac{E_2-\mu_2N_2}{T_2})\ge 1
$$
$$
-\frac{E_0}{T_0}-\frac{E_1-\mu_1N_1}{T_1}-\frac{E_2-\mu_2N_2}{T_2}\ge 0
$$
$$
\frac{E_0}{T_0}+\frac{E_1-\mu_1N_1}{T_1}+\frac{E_2-\mu_2N_2}{T_2}\le0
$$
Again, we get the second law.

$$
\frac{P(E,N)}{P_r(E,N)}=exp(-\frac{E-\mu N}{kT})
$$
if N=0
$$
\frac{P(E)}{P_r(E)}=\exp(-\frac{E}{kT})
$$
That is, when temperature is equal, it's harder to take energy from enviroument than to give.

## Entropy

## Law of Equilibrium

# Lecture 6 Schrodinger Equation
The following content has admitted this formula
$$
E\psi=H\psi
$$
Where eigenvalue refers to energy level, H refers to differential operator, $\psi$ is the wave function and $\psi\psi^*$ is the probability of electron.

^sch


To find DOS , relative m* and so on, we need to know E-K relationship.
To find out E-K relationship, we need to build and solve shcrodinger equation.

**What make it so hard to analyze motivation of electrons?**

![[Crystal]]

## Wave Function
![](_image/image_56.png)
$$
\frac{Zq^{2}}{4 \pi\varepsilon_{0}r^{2}}=\frac{mv^{2}}{r}
$$
$$
E=-\frac{Zq^2}{4\pi\varepsilon_0r}+\frac{mv^2}{2}=-\frac{Zq^2}{8\pi \varepsilon_0r}
$$
$$
\begin{align}
a_0=\frac{4\pi\varepsilon_0h^2}{mq^2}\\
n\lambda=\frac{nh}{mv}=2 \pi r
\end{align}
$$
where $a_{0}$ is _Bohr Radius_, and $\lambda$ is _de Broglie wavelength_

For single atom, we have
$$
E_n=-\frac{Z}{n^2}\frac{q^2}{8\pi \varepsilon_0a_0}
$$
$$
r_n=\frac{4\pi \varepsilon _0 h^2}{mq^2}\times \frac{n^2}{Z}
$$
![](_image/image_57.png)

To find out wave function of N atoms,  we find single atoms firsly. State of single atom can be consider as linear combination of baisis functions.
$$
\begin{cases}
\psi(x)=\sum x_n|x_n>\\
|x_1>,|x_2>…|x_n>
\end{cases}
$$
After that, use _periodic solids assumption_ to find wave function 
$$
\psi_r(x)=\sum\psi_mu_m(\vec r)
$$
So we have wave function
$$
E_{\psi}(\vec r)=\left(-\frac{h^2}{2m_0}\nabla^2+U_0(\vec r)\right)\psi(\vec r)
$$
where $U_0$ is microscopic potential
$$
U(\vec r)=-\frac{Zq^2}{4\pi \varepsilon_0 r}
$$
If we consider _dispersion relation_
$$
 \begin{align*}
E_{\psi({\vec r)}}&=(-\frac{h^2}{2m}\nabla^2+U_0)\psi(\vec r)\\\\
\psi(\vec r)&=e^{+ik_r}\psi_0\\\\
\nabla^2&=\frac{\partial^2 }{\partial ^{2}x}+\frac{\partial^2 }{\partial ^{2}y}+\frac{\partial^2 }{\partial ^{2}z}\\
\\
E(\vec k)&=\frac{h^2}{2m}(k^2_x+k^2_y+k^2_z)+U_0\\
&=\frac{h^2}{2m}(k^2_r)+U_0\\
\end{align*}
$$

For 1-D condition, it's hard to calculate if k can be arbitrary number, so we use  a simple approxiation as follows.
```image-layout-a
![[image_72.png]]
![[image_71.png]]
```
$$
\begin{align*}
E(\vec k)&=\frac{h^2}{2m}(k^2_x+k^2_y+k^2_z)+U_0\\
&=\frac{h^2}{2m}(k^2_r)+U_0\\
\\
\psi(z)&=Ae^{+ik_{z}z}+Be^{-ik_{z}z}\\
&=A(e^{+ik_{z}z}-e^{-ik_{z}z}) \\
&\sim sin\ k_{z}z\\
\\
k_{z}L&=n\pi
\end{align*}
$$
Furtherly, if we broading this approxiation in periodic lattice, we have
![[image_122.png]]
we can see the level near to atom core become discretlevel , but what we care is continuous level (further for atom core, so easy to transport). 
Then we can draw the new wave function by replace mass as effecticve mass.
$$
E{\psi}(\vec r)=\left(-\frac{h^2}{2m}\nabla^2+U(\vec r)\right)\psi(\vec r)
$$
where U is _additonal_ potential, m is _effective_ mass(not $U_{0}$ and $m_0$) 

## Matrix Equation
$$
E{\psi}(\vec r)=\left(-\frac{h^2}{2m}\nabla^2+U(\vec r)\right)\psi(\vec r)
$$
To take Schrödinger Equation into matrix, we firstly consider $\psi(r)$ as a column.
$$
\begin{align*}
\psi(r) &= \begin{pmatrix}\psi_1 \\ \psi_2 \\ \psi_3  \\ \vdots\end{pmatrix}=\sum\limits ^N_{m=1}\psi_{m}u_{m}(\vec r)
\end{align*}
$$
Then we have the First Principle
$$
E[S]\{\psi\}=[H]\{\psi\}
$$
where
$$
\begin{align*}
H_{mn}&=\int \mathrm dV\ u^*_{m}(\vec r)H_{op}u_{n}(\vec r)\\
S_{mn}&= \int \mathrm dV u^*_{m}(\vec r)u_{n}(\vec r)\\
H_{op}&=\left(-\frac{h^2}{2m}\nabla^2+U(\vec r)\right)
\end{align*}
$$

If we consider interaction between single atoms, such as Hydrogen molecule.
![[image_137.jpeg]]
Then we have the equation like this:
$$
E\begin{pmatrix}1&s \\ s&1\end{pmatrix}\begin{pmatrix}\psi_{1} \\ \psi_{2}\end{pmatrix}=\begin{pmatrix}\varepsilon&t \\t& \varepsilon\end{pmatrix}\begin{pmatrix}\psi_1 \\ 
\psi_2\end{pmatrix}
$$
$$
E\begin{bmatrix}\psi_1 \\ \psi_2\end{bmatrix}=\frac{1}{1-s^{2}}\begin{bmatrix}\varepsilon-ts&t-\varepsilon s \\ t-\varepsilon s&\varepsilon-ts\end{bmatrix}\begin{bmatrix}\psi_{1} \\ \psi_{2}\end{bmatrix}
$$
when the diagonal elements are equal, the eigenvalues are simply the diagonal elements plus or minus the magnitude of the off diagonal one.
$$
\begin{align*}
\lambda_1=\frac{\varepsilon-t}{1-s}\\\\
\lambda_2=\frac{\varepsilon+t}{1+s}
\end{align*}
$$
^Hy

**How to broad the matrix?**
Use dispersion relation and periodic boundary condition.
## Dispersion Relation
Although we have the first principle, we can still take S into H when we calculate the parameter because we only care about the final eigenvalues.
$$
E\begin{bmatrix}\psi\end{bmatrix}=[H]\begin{bmatrix}\psi\end{bmatrix}
$$
we have known the condition of Hydrogen molecule, now consider Hydrogen solid.
![[image_138.jpeg]]
atom u1 and u3 don’t have overlap area, so the product of there basis function $u_{1}\cdot u^*_{3}$ should be 0.
So we can draw the equation:
$$
E\begin{bmatrix}\psi_1 \\ \psi_{2} \\ 
\vdots \\ \psi_{N-1} \\ \psi_{N} \end{bmatrix}=\begin{bmatrix}\varepsilon&t&0&\cdots&\cdots&t \\ t&\varepsilon&t&0&\cdots& \\ 0&t&\varepsilon&t&0&\cdots \\ \vdots&\vdots& \vdots\\t& \cdots&\cdots &0&t&\varepsilon  \end{bmatrix}\begin{bmatrix}\psi_{1} \\ \psi_{2} \\ \vdots \\ \psi_{N-1} \\ \psi_N\end{bmatrix}
$$
$$
E\psi_{n}=t\psi_{n-1}+\varepsilon\psi_{n}+t\psi_{n+1}
$$
If we take $\psi_{n}=\psi_{0}e^{+inka}$ into the equation, we have
$$
\begin{align}
E&=t\frac{\psi_{n-1}}{\psi_{n}}+\varepsilon+t\frac{\psi_{n+1}}{\psi_{n}}\\
&=te^{-ika}+\varepsilon+te^{+ika}\\
&=\varepsilon+2tcos(ka+\phi)
\end{align}
$$
which is as follows
![[image_87.png]]
$$
\begin{align*}
E&=te^{-ika}+\varepsilon+te^{+ika}
\\&=\varepsilon +2t\ cos\ ka\\
&=\varepsilon+2t\left(1-\frac{k^{2}a^{2}}{2}+\cdots\right)\\
&\approx E_{c}+\frac{h^{2}k^{2}}{2m}   
\end{align*}
$$
where $a$ is lattice spacing.
Then we make the E-k relationship becomes the format we like(use) more.

Consider periodic condition, only care about single period state.
Can consider k’s only in first Brillouin Zone（$-\pi -> \pi$）, _because lattice is discrete_.
![[image_88.png]]
$$
\begin{align*}
\psi_{n}&=\psi_{0}e^{+inka}\\
\\
k’a &\rightarrow a+2 \pi\\
\\
\psi_{n}’ &=\psi_{0}e^{+inka}e^{+in2\pi}\\
&= \psi_n
\end{align*}
$$
That is 
$$
\begin{align*}
\psi_{0}=\psi_{N}&=\psi_{0}e^{+iNka}\\\\

Nka&=2\pi v\\\\
ka&= \frac{2\pi}{N}v\\\\
k&=\frac{2\pi}{Na} v
\end{align*}
$$
For 2-D condition
$$
\begin{align*}
\psi_{n}&=\psi_{0}e^{+ikr_{n}}\\\\
E\psi_{n}&=\sum\limits_{m}H_{nm}\psi_{m}\\
E\psi_{0}e^{+ikr_{n}}&=\sum\limits _mH_{nm}\psi_{0}e^{+ikr_{n}}\\
E(k)&= \sum\limits_{m}H_{nm}e^{+ik(r_{m}-r_{n})}
\end{align*}
$$
![[image_95.png]]
$$
E(\vec k)=\varepsilon + 2t_{1}cosk_xa+2t_2cosk_{y}b
$$
![[image_96.png]]
## Lattice with a basis
For most solid we calculate, it's universal to be multi-atom structure, for example, if we consider two type atoms structure as follows, $\psi$ becomes a vector about X and O not a number.
![[image_137.png]]
If we consider X and O as an unit, then _per unit have two basis function_ and we only need to care about the interaction between X and O when calculate H, that is t'.
So use Schrodinger Equation, we have
$$
\begin{align*}
E[\psi_{n}]&=\sum\limits_{m}[H]_{nm}[\psi_{m}]\\\\
E[\psi_{0}]e^{ikr_{n}}&= \sum\limits_{m}[H_{nm}]e^{ikr_{m}}[\psi_{0}]\\
\end{align*}
$$
That is 
$$
\begin{align*}
E[\psi_{0}]&= [h(k)]\ [\psi_{0}]\\
&= \sum\limits_{m}[H_{nm}]e^{ik(r_{m}-r_{n})}[\psi_{0}]\\\\
[h(k)]&= \sum\limits_{m}[H_{nm}]e^{ik(r_{m}-r_{n})}\\
\end{align*}
$$
$$
\begin{align*}
[h(k)]&=\begin{bmatrix}0&t'\\
0&0\end{bmatrix}e^{-ikb}+\begin{bmatrix}\varepsilon&t\\
t&\varepsilon\end{bmatrix}+\begin{bmatrix}0&0\\
t'&0\end{bmatrix}e^{+ikb}\\\\
&= \begin{bmatrix}\varepsilon&t+t'e^{-ikb}\\
t+t'e^{+ikb}&\varepsilon\end{bmatrix}\\\\
&= \begin{bmatrix}\varepsilon&h^{*}_{0}\\
h_{0}&\varepsilon\end{bmatrix}
\end{align*}
$$

Where b is the placing of per unit, $\psi_0$ is a vector and H is a 2-D matrix with two eigenvalues.
Two eigenvalues mean _two energy for each k_.
![[image_138.png]]
$$
\begin{align}
E&=\varepsilon \pm|h_0|\\\\
|h_{0}|&=\sqrt{(t+t'e^{ikb})(t+t'e^{-ikb})}\\&=\sqrt{t^{2}+t'^{2}+2tt'coskb}
\end{align}
$$
**What if t=t'?**
![[image_140.png]]
Which is the same as 1-D without basis.
## Graphene
![[image_142.png]]
$$
[h(k)]= \sum\limits_{m}[H_{nm}]e^{i\vec k(\vec r_{m}-\vec r_{n})}
$$
$r_{m}-r_{n}$ mean the vector between two adjacent unit (green arrows). So they are $a\vec x+b\vec y$, $a\vec x -b\vec y$, and so on.
Add them and we'll get
$$
\begin{align*}
h(\vec k)=\begin{bmatrix}\varepsilon &h^{*}_{0}\\
h_{0}&\varepsilon\end{bmatrix}
\end{align*}
$$
$$
E=\varepsilon\pm |h_{0}|
$$
where
$$
\begin{align*}
h_{0}&=t(1+e^{ik_{x}a+ik_{y}b}+e^{ik_{x}a-ik_{y}b})\\
&= t(1+2e^{ik_{xa}}cosk_{y}b)
\end{align*}
$$
What we concern is energy level near the femi level which is the most important for electrons flow, so we try to find $h_{0}=0$
![[image_143.png]]
From the above, we know where the zero point is, so we can use Tyler Expanding to find the concrete value.
$$
\begin{align*}
h_{0}&=t(1+2e^{ik_{x}a}cosk_{y}b)\\
&\approx \left[\frac{\partial h_{0}}{\partial k_{x}}\right]_{0,\frac{2\pi}{3}}(k_{x}-0)+\left[\frac{\partial h_{0}}{\partial k_{y}}\right]_{0,\frac{2 \pi}{3}}\left(k_{y}-\frac{2\pi}{3}\right)\\
&= -iatk_{x}-b\sqrt 3 t \beta_{y}\\
&\approx -iat(k_{x}+i\beta _{y})   
\end{align*}
$$
where
$$
\begin{align*}
\frac{\partial h_{0}}{\partial k_{x}}&=[2iae^{ik_{x}a}\ cosk_{y}b]_{0,\frac{2\pi}{3}}\\\\
\frac{\partial h_{0}}{\partial k_{y}}&= [-2ibe^{ik_{x}a}\ sink_{y}b]_{0,\frac{2\pi}{3}}
\end{align*}
$$
So we have E-k relationship
$$
\begin{align*}
E&=\varepsilon \pm |h_{0}|\\
&=\varepsilon \pm at\sqrt{k^{2}_{x}+\beta^{2}_{y}} \\
\end{align*}
$$
$$
v=\frac{1}{h}\frac{\partial E}{\partial k}=\frac{at}{h}\sim 10^6m/s
$$
Which means that the velocity of electrons in gropene is a constant.

## Reciprocal Lattice / valleys

# Lecture 7 Contact-ing Schrödinger Equation
## Semiclassical Model
```image-layout-a
![[image_99.png]]
![[image_98.png]]

```
$$
\begin{align*}
\frac{\mathrm dN}{\mathrm dt}=&-(v_{1}+v_{2})N\qquad Outflow\\
&+(S_{1}+S_{2})D_{0}\qquad Inflow
\end{align*}
$$
For steady-state
$$
\begin{align*}
\frac{\mathrm dN}{\mathrm dt}&=0\\\\
\frac{N}{D_{0}}&=\frac{S_{1}+S_{2}}{v_{1}+v_{2}}
\end{align*}
$$
To find steady-state current
$$
\begin{align*}
I_{1}&=D_{0}(S_{1}-v_{1}\frac{N}{D_{0}})q\\
& =D_{0}\frac{v_{2}S_{1}-v_{1}S_{2}}{v_{1}+v_{2}}q\\
&= -I_{2}
\end{align*}
$$
If we consider equilibrium, we have
$$
\begin{align*}
\frac{N_{1}}{D_{0}}=\frac{S_{1}}{v_{1}}=f_{1}\\
\frac{N_{2}}{D_{0}}=\frac{S_{2}}{v_{2}}=f_{2}\\\\
S_{1}=v_{1}f_{1}(E)\\
S_{2}=v_{2}f_{2}(E)
\end{align*}
$$

^9595a1

$$
\begin{align*}
I_{1}& =D_{0}\frac{v_{2}S_{1}-v_{1}S_{2}}{v_{1}+v_{2}}q\\
&= q\int^{\infty}_{-\infty}\mathrm dE\ D(E)\frac{v_{1}v_{2}}{v_{1}+v_{2}} (f_{1}-f_{2})\\
&= -I_{2}\\
\\
N&= \int^{\infty}_{-\infty}\mathrm dE\ D(E) \frac{v_{1}f_{1}+v_{2}f_{2}}{v_{1}+v_{2}}
\end{align*}
$$
## Quantum Model
$$
\begin{align*}
ih\frac{d}{dt}\{\tilde \psi\}&= [H]\{\tilde \psi\}\\
\tilde \psi &= \psi e^{{-iEt}/{h}}\\
ih\times -&\frac{iE}{h}= E\\
E[\psi]&= [H][\psi]
\end{align*}
$$
The above format of Schrodinger equation can't find flow.
To bring $\mathrm dt$ into the formula, use time-dependent Schrodinger equation
$$
\begin{align*}
ih\frac{d}{dt}\{\tilde \psi\}&= [H]\{\tilde \psi\}
\end{align*}
$$
From the boundary conditions which will be mentioned later, we have
$$
\begin{align*}
E\{\tilde\psi\}=ih\frac{d}{dt}\{\tilde \psi\}=&[H]\{\tilde\psi\}\\
+&[\Sigma_1+\Sigma_2]\{\tilde\psi\}\qquad &Outflow\\
+ &\{\tilde s_{1}\}+\{\tilde s_{2}\}\qquad &Inflow
\end{align*}
$$

^9cce8b

To connect $dN/dt$ and the equation, use
$$
\begin{align*}
N&= \tilde \psi^+\tilde \psi\\
&= \psi^+\psi
\end{align*}
$$
So For H, we have
$$
\begin{align*}
ih\frac{d}{dt}N&= ih\frac{d}{dt}\tilde \psi^+ \tilde \psi\\
&= (ih\frac{d}{dt}\tilde \psi^{+})\tilde \psi+\tilde\psi^{+}(ih\frac{d}{dt}\tilde \psi)\\
&= -(H\tilde \psi)^{+}\tilde\psi+\tilde \psi^{+}(H\tilde\psi)\\
&= \tilde \psi^{+}(H-H^{+})\tilde\psi 
\end{align*}
$$
Similarly, we have
$$
\begin{align*}
ih\frac{d}{dt}N&= ih\frac{d}{dt}\tilde \psi^+ \tilde \psi\\
&= \tilde\psi^{+}(\Sigma-\Sigma^{+})\tilde \psi\\\\
\Sigma&= \Sigma_{1}+\Sigma_{2}\\
\Gamma&\equiv i(\Sigma-\Sigma^{+})\\\\
ih\frac{d}{dt}N&= ih\frac{d}{dt}\tilde \psi^+ \tilde \psi\\
&= -\tilde s^{+}\tilde \psi+\tilde \psi^{+}\tilde s
\end{align*}
$$

^51929e

Compared with semi-classical model
$$
\begin{align*}
\frac{dN}{dt}&= -\tilde \psi\frac{\Gamma_{1}+\Gamma_{2}}{h}\tilde \psi\qquad Outflow\\
&+\frac{\tilde \psi^{+} \tilde s-\tilde s^{+}\tilde \psi}{ih}\qquad Inflow\\\\
\frac{dN}{dt}&= -(v_{2}+v_{2})N\qquad Outflow\\
&+(s_{1}+s_{2})D_{0}\qquad Inflow
\end{align*}
$$

^111

![[image_152.png]]
Now we get the quantum model, and don't need to care time anymore when we consider steady-state current, so use $\psi$ instead of $\tilde \psi$
$$
\begin{align*}
E\psi= (H+\Sigma)\psi + s_{1}\\
[E-H-\Sigma]\psi=s_{1}
\end{align*}
$$
Use Green's Function Method
$$
\begin{align*}
\psi&= [G^{R}]\{s_{1}\}\\
\psi^{+}&= s_{1}^{+}G^{A}\\\\
G^{R}&= [E-H-\Sigma]^{-1}\\
G^{A}&= [G^{R}]^{+}
\end{align*}
$$

^d3ea95

define
$$
A\equiv i[G^{R}-G^{A}]
$$
we have
$$
\begin{align*}
\frac{I_{1}+I_{2}}{q}= &-\psi^{+}\frac{\Gamma_{1}+\Gamma_{2}}{h}\psi\qquad Outflow\\
&+s_{1}^{+}\frac{A}{h}s_{1}\qquad Inflow
\\\\
\frac{I_{1}+I_{2}}{q}= &-(v_{2}+v_{2})N\qquad Outflow\\
&+(S_{1}+S_{2})D_{0}\qquad Inflow
\end{align*}
$$
Where we can connect $D_0$ to $A$
![[image_153.png]]
We can see the equation becomes a linear equation
$$
E(\psi)=(a+b)(\psi)+c
$$
$s_{1},s_{2}$ refers to probability, so use product to ?
$$
\begin{align*}
\psi&\sim (s_{1}+ s_{2})\\\\
\psi^{+}\psi&\sim(s_{1}+s_{2})\times(s_{1}+s_{2})^{+}\\
&=s^{+}_{1}s_1+s^{+}_{2}s_{2}+s^{+}_{1}s_{2}+s_{2}^{+}s_{1}
\end{align*}
$$
where $s^{+}_{1}s_{2}$ and $s_{2}^{+}s_{1}$ are _non-physical_, so we make them equal to zero. So there is
$$
\psi^{+}\psi=s^{+}_{1}s_1+s^{+}_{2}s_{2}
$$


## NEGF Equations
$$
\begin{align*}
\frac{I_{1}}{q}&= -\psi^{+}\frac{\Gamma_{1}}{h}\psi+s^{+}_{1}\frac{A}{h}s_{1}\\
\\I_{1}&= q\ Tr[-\psi^{+}\frac{\Gamma_{1}}{h}\psi+s^{+}_{1}\frac{A}{h}s_{1}]\\
&= q\ Tr[-\frac{\Gamma_{1}}{h}\psi\psi^{+}+s_{1}s_{1}^{+}\frac{A}{h}]\\
&= \frac{q}{h}Tr  [-\Gamma_{1}G^{n}+\Sigma^{in}_{1}A]
\end{align*}
$$
![[image_153.png]]
![[image_154.png]]
Still compared with semi-classical model, we have
![[image_155.png|350]]
So we know
$$
N=\int^{\infty}_{-\infty}dE\frac{Tr\ [G^{n}(E)]}{2\pi}
$$
$$
\begin{align*}
D&= \int^{\infty}_{-\infty}dE\frac{Tr\ [A(E)]}{2\pi}\\
&= \frac{i}{2\pi}Tr\ \int^{\infty}_{-\infty}dE[G^{R}-G^{A}]
\end{align*}
$$
**Where does $2\pi$ come from?**
Parseval's theorem.
$$
\int dt |\tilde \psi(t)|^{2}=\int \frac{dE}{2\pi}|\psi(E)|^{2}
$$
![[#^9595a1]]
Similar to semi-classical model, for quantum model, we have
$$
\begin{align*}
\Sigma^{in}_{1}=\Gamma_{1}(E)f_{1}(E)\\
\Sigma_{2}^{in}=\Gamma_{2}(E)f_{2}(E)
\end{align*}
$$

^f3a71e

$$
\begin{align*}
\Sigma^{in}&= \Sigma_{1}^{in}+\Sigma^{in}_{2}=\Gamma_{1}f_{1}+\Gamma _{2}f_{2}\\
&= (\Gamma_{1}+\Gamma_{2})f_{0}=\Gamma f_{0}
\end{align*}
$$
Do such derivation
$$
\begin{align*}
[G^{T}]^{-1}&= EI-H-\Sigma \\
[G^{A}]^{-1}=[[G^{R}]^{-1}]^{+}&= Ei-H-\Sigma^{+}\\\\
G^{R}-G^{A}=G^{R}([G^{A}]^{-1}-[G^{R}]^{-1})G^{A}&= G^{R}(\Sigma-\Sigma^{+})G^{A} =-iG^{R}\Gamma G^{A}\\
=G^{A}([G^{A}]^{-1}-[G^{R}]^{-1})G^{R}&= G^{R}(\Sigma-\Sigma^{+})G^{A} =-iG^{A}\Gamma G^{R}\\\\
A=i|G^{R}-G^{A}|&= G^{R}\Gamma G^{A}=G^{A}\Gamma G^{R}
\end{align*}
$$
So we have
$$
\begin{align*}
G^{n}&=  G^{R}\Sigma^{in}G^{A}\\
&= [G^{R}\Gamma G^{A}]f_{0}\\
&= [A]f_{0}
\end{align*}
$$
NEGF is more general and powerful, if there are some conceptual contacts which do not exit physically, we can still use $\Sigma = \Sigma^{in}_{0}+\Sigma^{in}_{1}+\Sigma^{in}_{2}$ to add them, such as depahsing contact of electrons interaction, but be sure that _do not use $\Sigma=\Gamma f$ at the same time_, these contacts don't exit after all, so there is no Femi-function.
For physical contact, it's not necessarily in equilibrium, but for conceptual contact, it must be in equilibrium, and company with _no net current_.
For the dephasing contact, we have
$$
Tr[\Sigma^{in}_{0}A]=Tr [\Gamma_{0}G^{n}]
$$
## Current Operator
![[#^111]]
To find $\frac{dN}{dt}$, we can find a more general solution.
$$
\begin{align*}
\frac{dN}{dt}&= \frac{d}{dt}\tilde \psi^{+}Y\tilde \psi\\
&= \frac{d}{dt}Tr\ \tilde \psi^{+} Y\tilde \psi\\
&= \frac{d}{dt}Tr\ Y\tilde \psi \tilde \psi^{+}\\
&= Tr\ Y \underbrace{\frac{d}{dt}\tilde \psi\tilde \psi^{+}}_{I_{OP}}
\end{align*}
$$
where Y is the matrix of current source. For example, if we want to find the current of electrons spin, then the Y is the matrix of spin.

## Sacttering Theory
![[image_158.png]]
For a simple example with relfection and penetration, what we want to is only about 0~N.
$$
\begin{align*}
\psi_{N}&= B\tau e^{+ikNa}\\
\psi_{N+1}&= B\tau e^{ik(N+1)a}\\
&= e^+ika\psi_{N}\\
\psi_{0}&= B+\rho\\
\psi_{-1}&= Be^{-ika}+\rho e^{+ika}\\
&= \psi_{0}e^{+ika}+B(e^{-ika}-e^{+ika})\\
&= \psi_{0}e^{+ika}+2iB\ sin\ ka
\end{align*}
$$
So we can get rid of $\psi_{-1}$ and $\psi_{N+1}$
$$
\begin{align*}
E\psi_{N}&= t\psi_{N-1}+\varepsilon \psi_{N}+t\psi_{N+1}\\
&= t \psi_{N-1}+(\varepsilon+te^{ika})\psi_{N}\\
E\psi_{0}&= t\psi_{-1}+\varepsilon \psi_{0}+t\psi_{1}\\
&= -2iB\ sin\ ka+(\varepsilon+te^{ika})\psi_{N}+t\psi_{1}\\
\end{align*}
$$
At the same time, we get the boundary condition
![[image_159.png]]
![[#^9cce8b]]
![[#^51929e]]
From the above, we can also find $\Gamma$
$$
\begin{align*}
\Gamma_{1}&= \begin{bmatrix}-2tsin\ ka&0&0\\
0&0&0\\
0&0&0\end{bmatrix}\\\\
\Gamma_{2}&= \begin{bmatrix}0&0&0\\
0&0&0\\
0&0&-2tsin\ ka\end{bmatrix}
\end{align*}
$$
$\Gamma$ refers to probability, so it can't be negative which means t must be negative.
![[image_160.png]]
Now we have $\Sigma_{1}\Sigma_{2}$ which will give us _outflow_ and $\Gamma_{1}\Gamma_{2}$ which will give us _inflow_ by $\Sigma_{in}$.
![[#^f3a71e]]
## Transmission
![[image_161.png]]
![[#^f3a71e]]
$$
\begin{align*}
I_{1}&= \frac{q}{h}Tr[\Sigma^{in}_{1}A-\Gamma_{1}G^{n}]\\
&= \frac{q}{h}Tr [\Gamma_{1}(Af_{1}-G^{n})]
\end{align*}
$$
Now that
$$
\begin{align*}
G^{n}&= G^{R}\Sigma^{in}G^{A}\\
&= G^{R}(\Gamma_{1}f_{1}+\Gamma_{2}f_{2})G^{A}\\\\
A&= G^{R}\Gamma G^{A}\\
&= G^{R}(\Gamma_{1}+\Gamma_{2})G^{A}
\end{align*}
$$
$$
\begin{align*}
I_{1}&= \frac{q}{h}Tr[\Sigma^{in}_{1}A-\Gamma_{1}G^{n}]\\
&= \frac{q}{h}Tr [\Gamma_{1}(Af_{1}-G^{n})]\\
&= \frac{q}{h}Tr [\Gamma_{1}G^{R}\Gamma_{2}G^A (f_{1}-f_{2})]\\
&= \frac{q}{h}\int^{\infty}_{-\infty}dE\ Tr[\Gamma_{1}G^{R}\Gamma_{2}G^A (f_{1}-f_{2})]
\end{align*}
$$
The above formula is for 1-D condition, to find a more general equation, we have
For any number of ports
$$
\Sigma^{in}_{p}=\Gamma_{p}f_{p}(E)
$$
$$
\begin{align*}
I_{p}&= \frac{q}{h}\sum\limits^{N}_{n=1}\ \underbrace{Tr\ [\Gamma_{1}G^{R}\Gamma_{2}G^{A}]}_{\bar T_{pn}(E)} (f_{p}-f_{n})
\end{align*}
$$
```image-layout-a
![[image_166.png]]
![[image_165.png]]
```
Then How to calculate $\bar T_{pn}$ ?
![[#^d3ea95]]

![[image_167.png]]
$$
\begin{align}\\
E&= \varepsilon+2tcoska\\\\
\frac{hv}{a}&= -2tsinka\\\\
G^{R}&= \frac{1}{E-H-\Sigma}\\
&= \frac{1}{E-\varepsilon-U-2te^{ika}}\\
&= \frac{1}{E-\varepsilon- U-2t(coska +isinka)}\\
&= \frac{1}{-U-2itsinka}\\
&= -\frac{1}{U+ihv/a}\\\\
\bar T_{pn}&= Tr\ [\Gamma_{1}G^{R}\Gamma_{2}G^{A}]\\

&= \frac{(hv)^{2}}{U_{0}^{2}+(hv)^{2}}\\
\end{align}
$$

By using E-k relationship $E=\varepsilon + 2t\ cos\ ka$, we find E-Transmission relathioship
![[image_168.png]]
## Resonant Tunneling


