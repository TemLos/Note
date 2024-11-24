---
title: Digital Integrated Circuit
date: 2023-09-26 18:13
mdate: 2023-10-14 20:07:59
tags:
  - Note
  - Hardware
  - Circuit
---
# Lecture 0 Intro
- Planar FET
    ![|475](image_29.jpg)
- FinFET
    ![|271](image_30.jpg)
- GAA FET
    ![|256](image_31.jpg)
- FDSOI
    Fully Depleted Silicon on Insulator.<https://www.bilibili.com/video/BV1M5411Q7zo/?spm_id_from=333.337.search-card.all.click&vd_source=dc4674766076b0c1c7b843aed68f8625>.
    
- Study trend
    - Thermal Issue
    - Variations
        Spatial varation & Temporal varation
    - 3D Integration
        Higher packing density,faster **on-chip** communication, but higher power density.
    - 2.5D Chiplets
    ![|575](image_32.jpg)
        - Low fabrication costs
        - different source, more flexible
        - can’ t improve intergration
      - Security
          IP protection
      - AI Chips
      - Open Source RISC-V
## MIPS Processor Structure
![[image_93.png]]
![[image_94.png]]

# Lectrue 1 Transister

![|550](image_33.jpg)
Current of PN junction flows only in one direction
## BJT Model
![|575](image_34.jpg)
$n^{++}$:Heavy Dopant
$V_{CE}$:make electrons arrive deplete region
$V_{CB}$:make electrons cross deplete region
- Base currents of BJT limit its integration desity. 
## MOSFET Model 
#### MOSFET
![|575](image_35.jpg)
- **Conductor of polysilicon is between metal and semiconductor?**
- FinFET begin to be used at 22nm node.
- Compared with BJT, low power characteristic of MOSFET allows very high integration
![|575](image_36.jpg)
- The body terminal is at low voltage to avoid PN junction breakovering.
- The gate terminal is at low voltage
    - No current flows, the transistor is OFF
- The gate terminal is at a high voltage
    - **Negative** charge attracted to surface and invert a channel under gate to **n-type**
    - **P-type** bulk silicon provides **minor carriers** to build invert channel.
    - Ideally, $I_GB=0$, but it’ s hard to achieve in fact, because of thin and impure insulator.
**Why pursue thiner insulator?**
$SiO_2$ is a plate capacity, the lower thickness, the more carriers, and the more carriers, the greater or faster current.
![](image_37.jpg)
p+Substrate Tap and n+Well Tap are used to set bulk voltage.



### Threshold Voltage
With large enough bias, enough electrons will be pulled to “inverted” the surface(p->n-type)
**How to calculate threshold voltage**
$$
V_{T0}=V_{FB}+\varphi_s+\frac{Q_d}{C_{ox}}+\frac{Q_{ox}}{C_{ox}}
$$
$$
V_T=V_{T0}+\gamma\cdot(\sqrt{\varphi_s+V_{SB}}-\sqrt{\varphi_s})
$$
To control threshold voltage, we have to insulate P and N substrate.
![[image_58.jpeg|500]]

**Subthreshold Swing**
$$
S=\frac{dV_{gs}}{d(lgI_{DS})}=ln10 \frac{dV_{GS}}{d(lnI_{DS})}=\frac{kT}{q}ln10 \frac{dV_{GS}}{dV_{S}}
$$
Less SS refers to greater ON-OFF ratio
### Static Behavors
![[image_59.jpeg|500]]
- Cutoff Region
![[image_60.jpeg|500]]
- Linear Region
![[image_61.jpeg|500]]
In Linear region, $I_{ds}$ depends on concentration and velocity of the charge in the channel.($I=\frac{Q}{t}$) 
Firstly, we calculate Q
$$
Q_{channel}=C\cdot V
$$
Notice that there are two capacity in Linear region——depletion capacity and SiO2 capacity. We use SiO2 capacity.
$$
C=C_g=\frac{\epsilon_{ox}}{t_{ox}}\cdot WL=C_{ox}\cdot WL
$$
![[image_62.jpeg]]
Then we calculate t.
$$
\begin{cases}
E&=\frac{V_{ds}}{L}\\
v&=\mu\cdot E\\
t&=\frac{L}{v}
\end{cases}
$$
So we have
$$
\begin{align}
I_{ds}&=\frac{Q_{channel}}{t}\\
&=\mu C_{ox}\frac{W}{L}(V_{gs}-V_T-\frac{V_{ds}}{2})V_{ds}\\
&=\beta(V_{gs}-V_T-\frac{V_{ds}}{2})V_{ds}\\
\beta&=\mu C_{ox}\frac{W}{L}
\end{align}
$$
we can get maximum of $I_{ds}$ when $V_{ds}=V_{gs}-V_T$ . If we use calculus method, we’ll get the same current formula.
- Saturation
![[image_63.jpeg|550]]
If keep increasing $V_{ds}$ when cuts off:
$V_{ds}$ broadens cutoff region and voltage at cutoff point is equal to $V_{gs}$ .

**How to get R when in saturation region**
![|525](image_64.jpeg)
![|525](image_65.jpeg)
### Dynamic Behavior
- Delay
![[image_66.jpeg|500]]

**Why is $\frac{t_{HL}+t_{LH}}{2}$?**
Not true value table, but engineer consideration——don’t know customer’s usage, so take them equal.
**Why is 90% or 10%?**
1. If higher than 90%: too slow
2. If lower than 10%: too obvious noice
### MOS Capacitor
###### Gate Capacity
![|450](image_67.jpeg)
- Cutoff region
![|450](image_68.jpeg)
Capacitance becomes series combination of gate oxide and deletion capacitance.
- Linear region
![|450](image_69.jpeg)
Channel makes $C_{GCB}$ drops to zero, we model capacitance by splitting oxide cap equally between source and drain.
- Saturation region
![|525](image_70.jpeg)
At pinch-off point, $V_{GD}\lt V_T$, In bottom line, $C_{GCS}=2/3WLC_{ox}$
- Other capacitance
Gate overlap capacitance
$$
C_{GSO}=C_{GDO}=C_{ox}\cdot x_d W
$$
Gate fringe capacitance
###### Diffusion/Junction Capacitance
Junction caps are nonlinear(function of junction bias voltage), to deal with, we have
$$
C_{eq}=\frac{\Delta Q_j}{\Delta V_D}=\frac{Q_j(V_{high})-Q_j(V_{low})}{V_{high}-V_{low}}=K_{eq}C_{j0}
$$
In summary, we have gaga-to-channel capacitance
![|500](image_71.jpeg)
###### Capacitance Model Summery
![|500](image_72.jpeg)
**Is Subthreshold Region the smaller the better?**
- As for high-performance device, the smaller the better.
- As for low-power device, Subthreshold can be taken into design consideration.
### Non-ideal Transistor Behaviour]
###### High Electronic Fields Effects
For long channel device
- Vertical electric field: $E_{vert}=V_{gs}/t_{ox},\quad Q_{channel}\propto E_{vert}$
i- Lateral elecric field: $E_{lat}=V_{ds}/L, \quad v\propto\mu\dot E_{lat}$
###### Mobility Degradation
For short channel device, mobility decreases when vertical electronic fields is too large.
###### Velocity Saturation
For short channel device, because carriers scatter off atoms in silicon lattice, velocity reaches $v_{sat}$ which is :
- Electrons: $10^7cm/s$
- Holes: $8\times 10^6cm/s$
Consider nonlinear velocity model
$$
\begin{cases}
\begin{align}
v_{eff}&=\frac{\mu_{eff}\cdot E}{1+E/E_C},\quad for\ E\le E_C\\
v_{sat}&=\frac{\mu_{eff}\cdot E_C}{2},\quad for\ E\ge E_C
\end{align}
\end{cases}
$$
$$
v_{sat}=\frac{\mu_{eff}E_{c}}{2}
$$
Where $E_C=V_{GS}-V_{TH}/L$
By using the formula, we divide four regions of operation:
(1)cut off, (2)linear, **(3)velocity sat**, (4) current sat
So in linear region, we have
$$
I_{DS}=\frac{\mu_{eff}C_{ox}}{1+\frac{V_{DS}}{E_CL}}\cdot \frac{W}{L}\cdot[(V_{GS}-V_t)V_{DS}-\frac{V^2_{DS}}{2}]
$$
In velocity saturation region, consider
$$
I_{D}
=WQ_{inv}(y)v(y)$$
we have
$$
\begin{align}
I_{DSAT}&=v_{sat}\cdot C_{ox}\cdot W\cdot [V_{GS}-V_t-V'_{DSAT}]\\
&=\frac{\mu_{eff}C_{ox}}{1+\frac{V_{DS}}{E_CL}}\cdot \frac{W}{L}\cdot[(V_{GS}-V_t)V’_{DSAT}-\frac{V^{,2}_{DSAT}}{2}]\\
&=\frac{\mu_{eff}E_c}{2}\cdot C_{ox}\cdot W\cdot[V_{GS}-V_t-V'_{SAT}]
\end{align}
$$
where
$$
V'_{DSAT}=\frac{V_{GS}-V_T}{1+(V_{GS}-V_T)/E_C\cdot L}=K\cdot V_{GT}\lt V_{DSAT}
$$
###### Channel Length Modulation(CLM)
Consider $\Delta L\lt L$
we have 
$$
\frac{1}{L-\Delta L}\approx \frac{1}{L}(1+\frac{\Delta L}{L})=\frac{1}{L}(1+\lambda V_{DS})
$$
$$
\begin{align}
I_{DS}&=\frac{\mu_n C_{ox}}{2}\cdot \frac{W}{L’}(V_{GS}-V_t)^2\\
&=\frac{\mu_n C_{ox}}{2}\cdot \frac{W}{L}(V_{GS}-V_t)^2\cdot (1+\lambda V_{DS})
\end{align}
$$
###### Threshold Voltage Effects
Threshold voltage depends on almost everything:

- Body Effect
$$
V_T=V_{T0}+\gamma\cdot(\sqrt{\varphi_S+V_{SB}}-\sqrt{\varphi_S})
$$
- Short Channel Effect
	In CMOS component process, when channel length reduce to 10~20 nm or even less, with channel length reducing, Vth reduces, carrier surface scaterring, velocity saturation,  ioniztion and hot electrons effect become more obvious.
- Narrow Witdth Effect
	In CMOS process, with the narrowing of channel width, Vth increases.
	It may be caused by $Q_{chw}$(not $Q_{ch}$), which is out of channel but still be abtracted by electric field of gate. Due to such electrons, we need higher electron density to maintain ON state, and when width reduce to a certain point, it can't be ignored.
	![[image_120.png]]
- Drain-Induced Barrier Lowering(DIBL)
		High drain voltage causes current to increase.
$$
V_t=V_t’-\eta V_{ds}
$$
- Others
		 [[INWE、RSCE and halo---
🌻日期🌻: 2024 10 31 21:43:05
🌙星期🌙: Thursday
⌚️时间⌚️: 21:43:05
🌍位置🌍: 上海-浦东新区
☁️天气☁️: 🌅小雨 / 🌃小雨
🌡️温度🌡️: 🌅22.0℃/ 🌃16.0℃
---
>[!quote] 一言
 友谊是一个灵魂对一个灵魂的认可。  —— 《甘地自传》 · 甘地

---
# To do list


# Diary




---
<< [[2024-11-15]] | [[2024-11-17]] >>]]
**How to induce DIBL?**
![](image_73.jpeg)
###### Leakage
![550|525](image_74.jpeg)

###### Temperature Sensitivity
Current in sub-threshold region
$$
I_{ds}=I_{ds0}\cdot e^{\frac{v_{gs}-V_{t0}+\eta V_{ds}-k_\gamma V_{sb}}{nv_T}(1-e^{(-V_{ds}/v_T)})}=I_{ds0}\cdot exp(\frac{V_{gs}}{\varepsilon V_T})
$$
###### Process and Environmental Variations
- Supply voltage
- 


# Lecture 2 Wires
#### Classes of global interconnects
- Global set and reset lines
- System clocks(s)
- Power distribution($V_D$ and GND)

#### The Local Wires

#### Wire Geometry
![](image_75.jpeg)
s: spacing
t: thickness
h: thickness of oxide insulator
w: width
l: length
- Pitch=w+s
- Aspect Ratio: AR=t/w
	Modern AR $\approx$ 2
#### Parasitic Modeling of Interconnect
##### Resistance
- MOS structure resistance - $R_{ON}$
- Source and drain resistance
- Contact (via) resistance
- Wiring resistance
###### Wiring Resistance
$$
R=\rho\frac{L}{A}=\rho\frac{L}{HW}
$$
To make it irrelevant to the designer, we use Sheet Resistance R
![](image_76.jpeg)
**What is Silicide?**
![](image_77.jpeg)
###### Contact Resistance

###### Impact of Wire Resistance
- Power supply
- **As design criteria, Power loss less than 10%?**
#### Capacitance
###### Parallel Plate
$$
C_{pp}=\frac{\varepsilon_{di}}{t_{di}}WL
$$
###### Fringe Capacitance
![](image_78.jpeg)
###### Inter-wire Capacitance
![](image_79.jpeg)

#### Interconnect RC Modeling
###### Elmore Delay
![](image_80.jpeg)
Consider resistance as power driving capacitance(i=5)
- R1 dives C1, C2, C3, C4 ,C5
- R3 drives C3, C4, C5
- R5 drives C5
$$
\begin{align}
\tau = &R_1C_1+R_1C_2+\\
&(R_1+R_3)C_3+\\
&(R_1+R_3)C_4+\\
&(R_1+R_3+R_5)C_5\\
=&R_1(C_1+C_2+C_3+C_4+C_5)+\\
&R_3(C_3+ C_4+C_5)+\\
&R_5C_5
\end{align}
$$

###### The Lumped Model
![](image_81.jpeg)
$$
\Downarrow
$$
![](image_82.jpeg)

$$
\tau = RC
$$
###### The Distributed RC Modeling
![](image_83.jpeg)
Use KCL, we have
$$
\begin{flalign}
&c\Delta L\frac{\partial V_i}{\partial t}=\frac{(V_{i+1}-V_i)+(V_{i-1}-V_i)}{r\Delta L}\\
&\Downarrow\ \Delta L\rightarrow 0\\
&rc\frac{\partial V}{\partial t}=\frac{\partial^2 V}{\partial x^2}
\end{flalign}
$$
$$
\begin{align}
\tau_{DN}&=\sum^N_{l=1}C_l(\sum^l_{j=1}R_j)=\sum^N_{l=1}R_l(\sum^N_{j=l}C_j)\\
&=(\frac{L}{N})^2(rc+2rc+\cdots+Nrc)\\
&=(rcL^2)\frac{N(N+1)}{2N^2}\rightarrow\frac{rcL^2}{2}=\frac{RC}{2}\ (N\rightarrow\infty)\\
&\sim L^2 
\end{align}
$$
_Distributed RC delay is only half of the lumped RC._

# Lecture 3 CMOS Inverter

## Static CMOS Properties
- Full rail-to-rail swing $\Rightarrow$ High noise margin
- Low output impedance $\Rightarrow$ Be able to drive large fan-out
- High input impedance
- No (low) static power dissipation

**How to deign a fast gate**
Consider RC Factor, we can improve swing speed by decreasing resister or capacitance of transistor. 

## Noise
For example, one of  sources of noises: coupling between lines
![](image_84.jpeg)

To see if a gate rejects noise: look at its DC voltage transfer characteristic (VTC)

![](image_85.jpeg)

Define $V_{IH}$ and $V_{IL}$ as the points on the VTC curve where the gain =-1
**Conditions for Regeneration**
![](image_86.jpeg)

## CMOS Inverter VTC
**How to get VTC**
For such inverter circuit
![](image_87.jpeg)
Consider I-V curve of PMOS and NMOS
![](image_88.jpeg)
Transform current and voltage as follows:
$$
I_{dsp}=-I_{dsn}\\
$$
$$
\begin{align}
V_{gsn}=V_{in},\ V_{gsp}=V_{in}-V_{DD}\\
V_{dsn}=V_{out},\ V_{dsp}=V_{out}-V_{DD}
\end{align}
$$
![](image_89.jpeg)
Then draw two curve transformed in one picture
![](image_90.jpeg)
From point of $\{ V_in = 1\ V,\ 1.5\ V,\ \cdots\}$, we can draw VTC
![](image_91.jpeg)

##### Five Operating Regions
![](image_92.jpeg)

- Red line: increasing the width of the PMOS moves $V_M$ towards $V_{DD}$ 
- Blue line: increasing the width of the NMOS moves $V_M$ towards $GND$

![](image_93.jpeg)
Comparing two pictures, it can be find that Inverter can work in sub-threshold region

## Dynamic Properties
**Why are there ”spikes”?**
![](image_18.png)

Consider Miller capacitor from in to out
![](image_19.png)
When input becomes VDD, the output voltage is pulled up by the Miller cap(red).

**How to optimize an inverter‘s delay?**

##### Inverter Chain
![](image_94.jpeg)

For single inverter, we assume that the equivalent resistance of pull-down and pull-up is equal.
![](image_95.jpeg)
The gate capacity of next level is $C_{ext}$ of this level.
![](image_96.jpeg)

**Why is no Miller effect?**
##### Factor $\gamma$  and f
Consider input/loading effect of one inverter:
$$
t_p=t_{p0}(1+\frac{C_{ext}}{C_{int}})=t_{p0}(1+\frac{C_{ext}}{\gamma C_g})=t_{p0}(1+\frac{f}{\gamma})
$$
$$
\gamma = \frac{C_{int}}{C_g}\qquad f=\frac{C_{ext}}{C_g}
$$
For whole inverter chain
![](image_97.jpeg)
$$
t_{p}=t_{p0}\Sigma (1+\frac{C_{g,j}}{\gamma C_{g,j}})\quad C_{g,N+1}=C_L
$$
**How to find the best f and N**
Because $\prod f=C$, if we want to minimize $t_p$, we need to make $f_1=f_2=\cdots=f_N$. So there is 
$$
\begin{align}
C_{g,j}=\sqrt{C_{g,j-1}\cdot C_{g,j+1}}\\
f=\sqrt[N]{C_L/C_{g,1}}=\sqrt[N] F\\
t_p=Nt_{p0}(1+\sqrt[N] F/\gamma)
\end{align}
$$
- If N too large, intrinsic delay of the stages becomes dominate.
- If N too small, effective fan-out of each stage becomes dominate.
$$
\frac{\partial t_p}{\partial N}=0
$$
$$
\Downarrow
$$
$$
\gamma +\sqrt[N] F-\frac{\sqrt[N]FlnF}{N}=0
$$
$$
f*=\sqrt[N] F=e^{(1+N/\gamma)}
$$
$$
\begin{cases}
f=e,\quad \gamma = 0\\
f=3.6,\quad \gamma = 1
\end{cases}
$$
![[Fan-out and Fan-in]]

## Power
### Dynamic Energy Dissipation
![](image_98.jpeg)
$$
\begin{align}
E=\int^\infty_{t=0}V_{DD}\cdot I_{Dp}\cdot \mathrm dt\\
I_{Dp}=C_L\cdot \frac{\mathrm dV}{\mathrm dt}
\end{align}
$$
$$
E=C_L\cdot V^2_{DD}
$$
Dynamic energy is not a function of ==transistor size==.
$C_L$ is not only relevant for speed, but also energy. _That is the reason why we make transistor smaller and smaller_.

**Not Full Swing**
For inverter chain
$$
E_N=C_L\cdot V^2_{DD} \cdot n(N)\
$$
$$
\begin{align}
P_{avg}&=\lim_{N\rightarrow\infty}\frac{E_N}{N}\cdot f_{clk}\\
&=(\lim_{N\rightarrow\infty}\frac{n(N)}{N})\cdot C_L\cdot V^2_{DD}\cdot f_{clk}\\
&=\alpha_{0\rightarrow1}\cdot C_L\cdot V_{DD}^2\cdot f_{clk}

\end{align}
$$

High $V_{DD}$ brings high _energy consumption_ and _high frequency_.
### Short-Circuit Power Comsumption

![](image_99.jpeg)

Consider impact of $C_L$ on $P_{dp}$

### Leakage (static) Power Consumption

![](_image/数字集成电路设计_image_3.png)
![](_image/数字集成电路设计_image_79.jpeg)

### Power summery
![](_image/数字集成电路设计_image_80.jpeg)

#### PDP and EDP
Power-delay product
$$
PDP=C_LV^2_{DD}f_{max}t_p=\frac{C_LV^2_{DD}}{2}\qquad f_{max}=\frac{1}{2t_p}
$$
Energy-delay product
$$
EDP=PDP\times t_p=P_{av}t^2_p=\frac{C_LV_{DD}^2}{2}t_p
$$
# Lecture 4 Complementary CMOS Logic Gates
## Static CMOS Logic
### Design
#### NAND Gate
![](_image/数字集成电路设计_image_81.jpeg)

#### NOR Gate 
![](_image/数字集成电路设计_image_82.jpeg)

- Use series to express AND or NAND
- Use Parallel to express OR and NOR

**Why PMOS for PUN, NMOS for PDN?**
- PMOS for PDN can’t reach GND to give a strong "0".
- NMOS for PUN can’t reach VDD to give a strong "1".

### Performance
### Static property (VTC)
VTC Curve of an CMOS Inverter
![[image_40.png]]
$$
V_M=\frac{(V_{Tn}+\frac{V_{DSATn}}{2})+r(V_{DD}+V_{Tp}+\frac{V_{DSATp}}{2})}{1+r}
$$
where
$$
r=\frac{k_pV_{DSATp}}{k_nV_{DSATn}}=\frac{v_{satp}W_p}{v_{satn}Wn}
$$
For specific static CMOS circuit
![[image_41.png]]

Threshold voltage of M2 higher than M1 due to body effect ($\gamma$)
$$
V_{Tn2}=V_{Tn0}+\gamma (\sqrt{|2\Phi_F|+V_{int}}-\sqrt{|2\Phi_F|})
$$
### Propagation delay of a single gate
To optimize the critical path, a reference book on timing analysis![[Timing.pdf]]
![[image_42.png]]
![[image_43.png]]
When Fan-in > 4, delay deteriorates rapidly, so _avoid Fan-in > 4_.

If we consider Fan-out
![[image_44.png]]
The closer to the ouput the fet is, the smaller the resistance of the fet should be. 

In cascode circuit, different input always cause different delay
![[image_45.png]]

### Delay in combinational networks
$$
\begin{align}
t_{p,INV}&=0.69R_{eq}C_{int}(1+C_{ext}/C_{int})\\
&=t_{p0}(1+f/\gamma)\\
&=0.69R_{eq}C_g(\frac{C_{int}}{C_g}+\frac{C_{ext}}{C_g})\\
&=\tau_{inv}(\gamma_{inv}+\rm Fan-out)
\end{align}

$$
$$
d=g\gamma+gh=p+gh
$$
where
$$
\gamma = \frac{C_{int}}{C_g}
$$
$$
\begin{align}
p&=g\cdot\gamma_{gate}\\
&=\frac{R_{eq,gate}}{R_{eq,INV}}\frac{C_{g,gate}}{C_{g,INV}}\frac{C_{int,gate}}{C_{g,gate}}\\
&=\frac{C_{int,gate}}{C_{int,INV}}\gamma\\
&=\frac{C_{int,gate}}{C_{g,INV}}
\end{align}
$$
$$
g=\frac{R_{eq,gate}}{R_{eq,INV}}\frac{C_{int,gate}}{C_{int,INV}}=\frac{C_{int,gate}}{C_{int,INV}}
$$
$$
h=\frac{C_{ext,gate}}{C_{g,gate}}
$$

| Logical effort | Electrical fan-out | Parasitic delay |Branching effort|
|:--------:|:--------:|:--------:|:--:|
|$g=\frac{C_{int,gate}}{C_{int,INV}}$|$p=\frac{C_{int,gate}}{C_{g,INV}}$|$h=\frac{C_{ext,gate}}{C_{g,gate}}$|$b=\frac{C_{on-path}+C_{off-path}}{C_{on-path}}$|
If we consider branch effort, there is

| Path effort | Path branching effort |
|:--------:|:--------:|
|$F=\amalg g\cdot h\cdot b$|$B=\amalg b_i$|
$$
D_{min}=\sum(g_ih_ib_i+p_i)=\sum(F+P)=\sum(N\cdot f+P)
$$

![[image_46.png]]

### Energy & Power
$$
E=C_LV_{DD}^2P_{0\rightarrow1}+t_{sc}V_{DD}I_{peak}P_{0/1\rightarrow1/0}+V_{DD}I_{peak}
$$
$$
P=C_LV_{DD}^2f+t_{sc}V_{DD}I_{peak}f+V_{DD}I_{peak}
$$
For switching probability of standard 2-input gates.

![[image_47.png]]

By changing logic restructuring

![[image_48.png]]

Chain implementation has a lower overall switching activity than the tree implementation for random inputs.

### Glitching
- Gates have a nonzero propagation delay resulting in spurious transitions or glitches (dynamic hazards) 
- Glitch: Node exhibits multiple transitions in a single cycle before settling to the correct logic value

![[image_49.png]]

Glitching can be transitted  and improved in a chain of gates

![[image_51.png]]
![[image_52.png]]

Glitching is due to a _mismatch_ in the path lengths in the logic network; if all input signals of a gate change simultaneously, no glitching occurs

![[image_50.png]]

### Power/enrgy Design Space

|Power/Energy|Design Time|Non-active Modules|Run Time|
|:--:|:--:|:--:|:--:|
|Active<br>(Dynamic) |Logic Design<br>Reduced Vdd<br>Transistor Sizing<br>Multi-Vd|Clock Gating|DFS,DVS|
|Leakage<br>(Standby) |Multi-Vt<br>Stach effect<br>Pin ordering|Sleep Transistors<br>Multi-Vdd<br>Variable Vt<br>input control|Variable Vt|

## Pass-Transistor Logic
![[image_23.png]]
![](image_17.png)
### Static Properties
- _Less_ transistors and lower design difficulty
	- N transistors instead of 2N.
- Gate is static
	- a path exists to both supply rails under all circumstances
- No static power consumption for itself
- Ratioless
- _Bidirectional_ (versus undirectional)

### Signal Degradation
![[image_27.png]]
Pure PT logic is not regenerative - the signal gradually degrades after passing through a number of PTs. 
![[image_24.png]]
It can be even worse due to _body effect_.
### Static Power Consumption
Threshold voltage drop causes static power consumption (M2 may be weakly conducting forming a path from VDD to GND)

#### Solution #1: Level Restorer
![[image_28.png]]

- Full swing
- No static power consumption
	- No static power by inverter
	- No static backward current path through Level Restorer and PT since restorer is only active when A is high
- _Ratioed_. For correct operation Mr must be sized correctly
	- increases the capacitance at x, slowing down the gate;
	- increase $t_{rise}$, but decrease $t_{fall}$
![[image_29.png]]

#### Solution #2: Multiple VT Transistors

![[image_31.png]]

Impacts static power consumption due to subthreshold currents flowing through the PTs (even if VGS is below VT )

#### Solution #3: Transmission Gates (TGs)
**Most widely used solution**
![[image_30.png]]
- Full swing.
- Bidirectionsl.
## Dynamic CMOS Logic 

[数字集成电路（8）动态CMOS - 墨魂](https://mohun-8052.github.io/2022/05/01/%E6%95%B0%E5%AD%97%E9%9B%86%E6%88%90%E7%94%B5%E8%B7%AF%EF%BC%888%EF%BC%89%E5%8A%A8%E6%80%81CMOS/)
![[image_22.png]]
### Static Properties
- Dynamic relies on _temporary_ storage of signal on the capacitance.
- Logic function only implemented by PDN, So the number of transistor is _N+2_ while static CMOS need _2N_.
- Full swintg output.
- Nonratioed
- _Lower_ power dissipation
	- _Fewer_ transistors reduce $C_{int}$ and $C_{ext}$
	- No short circuit, all current provided by $C_L$ when pull-down.
- Note: power dissipation can be significantly _higher_ due to
	- higher transition probabilities
	- extra load on CLK (needs a precharge/evaluate clock)
### Dynamic Properties
- _Faster_ swiching speed 
	- _Fewer_ transistors reduce $C_{int}$ and $C_{ext}$
	- Precharge time can be ignored($t_{pLH}=0$), but the presence of the evaluation transistors slows the $t_{pHL}$.
- _No glitching_. By construction can have at most one transition per cycle

### Domino Logic

Reference: [[4740_lecture16-domino-logic.pdf]]


![[image_237.png]]
![[image_238.png]]

For dynamic logic, PUN networks can't be cascaded. when cascaded with an equivalent gate, the pre-charged output of the second gate may be discharged before its inputs stabilize.

![[image_239.png]]
![[image_242.png]]

Use domino logic to make sure the pre-charged output is _always high_ or _low to  high_ unless evaluate.

- Disadvantages
	- Only _Non-Inverting_ logic can be implemented
		- Use De Morgan or other logic transforms
		- Use differential logic (dual )
		- Use np-CMOS (zipper or NORA)
	- Larger area than static logic
	- higher power consumption than static.
- Advantages
	- Extremely fast circuits
	- Inverter enable easy use of level restores
![[image_240.png]]![[image_241.png]]
## Ratiod Logic and Ratioless Logic
![[image_32.png]]

- _Ratioless_: $𝑉_{𝑂𝐻}$ and $𝑉_{𝑂𝐿}$ independent of transistor sizes
- _Ratioed_: $𝑉_{𝑂𝐻}$ and $𝑉_{𝑂𝐿}$ depend on transistor sizes
![[image_33.png]]

![[The Depletion NMOS Transistor.pdf]]

- _For area reduction_, use NOR gates, not NAND gates.
- Spend power for speed

![[image_34.png]]
$$
k_n((V_{DD}-V_{Tn})V_{OL}-\frac{V^2_{OL}}{2})=k_p\left((-V_{DD}-V_{Tp})V_{DSAT}-\frac{V^2_{DSAT}}{2}\right)
$$
$$
V_{OL}\approx\frac{k_p(-V_{DD}-V_{{Tp}})V_{DSAT}}{k_n(V_{DD}-V_{Tn})}\approx\frac{\mu_pW_p}{\mu_nW_n}|V_{DSAT}|
$$
$$
P_{low}=V_{DD}I_{low}\approx V_{DD}\cdot k_p\left((-V_DD{-V_{Tp})V_{DSATp}}-\frac{V_{DSATp}^2}{2}\right)
$$
### Improved Loads
![[image_35.png]]
- Rail-to-rail swing 
- No static power in steady state 
- _But still ratioed!_
![[image_36.png]]

### Dynamic CMOS Logic VS Ratioed Logic
Ratioed Logic
![[image_37.png]]

Dynamic Logic
![[image_39.png]]

#### Similarities
- Logic function only implemented by PDN
- Less transistors compared with static CMOS logic circuit.

#### Difference
- Ratioed logic circuit use GND to make sure that the PMOS is always ON.
- Dynamic logic circuit use clk signal to drive $M_P$, which make two -phase operation _Precharge_ and _Evaluate_.
- It's possible for Dynamic logic circuit to _suspend_.
- Due to almost negligible short current, Dynamic logic circuit has lower power dissipation.
- Dynamic logic circuit is ratioless.

# Lecture 5 Datapath Blocks
![[#MIPS Processor Structure]]
## Adder
![](_image/image_59.png)
$$
T_{adder}\approx (N-1)T_{carry}+T_{sum}
$$
So we know $T_{adder}=O(N)$, and  $T_{carry}$ is far more important than $T_{sum}$

![](_image/image_58.png)
For subtraction, we have
$$
A-B=A-\bar B +1
$$
A-B=A+(2’ s complement of B)=A+(1’ s complement of B)+1
2’ s complement: 1000-0001=1111
1’ s complement:1111-0001+0001=1111
### Circuit Design
For a full adder
![](_image/image_60.png)
$$
C_o=AB+BC_i+AC_i
$$
$$
\begin{align}
S&=A\bar B\bar C_i\\
&=ABC_i+\bar C_o(A+B+C_i)
\end{align}
$$

###  Improvement 1 Share Transistors
![](_image/image_61.png)



### Improvement 2 Exploit the Inversion Property
![](_image/image_63.png)


### Improvement 3 Mirror Adder
![](_image/image_62.png)

### Manchester Carry Chain
![](_image/image_64.png)

^MCC
### Fast Carry Chaifn
![](_image/image_65.png)
![](_image/image_66.png)
### Carry-Bypass (skip) Adder
![](_image/image_67.png)
The core idea is before the carry signal arrives, the adder predict output for both conditions. 
#### Linear Carry Select
![](_image/image_68.png)

#### Square Root Carry Select Adder
![](_image/image_69.png)

### Look-Ahead Adders

### Tree Adders
#### Structure of Tree
Brent-Kung Tree
![[image_169.png]]
Radix-2 Koggle-Stone Tree
![[image_170.png]]
Radix-4 Koggle-Stone Tree
![[image_171.png]]






## Multiplier
### General Form
![[image_84.png]]
**How to implement multiplier in binary?**
Multiplication is just a lot of additions.

**How to get the result of additions**
Use “AND” operation.

**Be careful for data overflow**
Add additional bit $p_{11}$

- Shift and add
	- Partial product array rows are accumulated from top to bottom on an M-bit adder.
	- $T_{serial_mult}=O(NT_{adder})=O(MN)$

**How to make it faster**
1. Faster adder
2. Higher _radix_ multiplication
3. Form the partial product array in parallel and add it in parallel.

**How to make it smaller**
1. Easily and efficiently _pipelined_.
2. With only _short_ wires to nearest neighbor cells.
### The Array Multiplier
![[image_79.png]]
![[image_81.png]]
$$
t_{mult}=[(M-1)+(N-2)]\cdot t_{carry}+(N-1)\cdot t_{sum}+t_{and}
$$
### Carry-Save Multiplier
![[image_80.png]]
$$
t_{mult}=t_{and}+(N-1)\cdot t_{carry}+t_{merge}
$$
## Multiplexer

```image-layout-a
![[image_86.png]] 
![[image_78.png]]
```

## Decoder
![[image_79.png]]
Need two inverters, four 2-input nand gate, four inverters plus enable logic.
### Dynamic 2-to-4 NOR Row Decoder
![[image_80.png]]

### Dynamic 2-to-4 NAND Row Decoder
![[image_81.png]]


## Comparator
![[image_83.png]]
![[image_83.png]]
![[image_84.png]]

## Shifter
 - Logical Shift
	 - fills with 0’s
	 - 1011 LSR 1 = 0101.   1011 LSL = 0110.
 - Arithmetic Shift
	 - Right shift sign extends
	 - 1011 ASR 1 = 1101.   1011 ASL 1= 0110.
 - Rotate
	 - Fills with lost bits
	 - 1011 ROR 1 = 1101.   1011 ROL 1 = 0111.
### Logical Shifter
![[image_89.png]]
### Arithmetic Shifter
#### 4-bit Barrel Shifter
![[image_90.png]]
**How to implement arithmetic shifter in more bits**

#### 8-bit Logarithmic Shifter
![[image_91.png]]
![[image_92.png]]

# Lecture 6 Sequential Circuit
![[#MIPS Processor Structure]]

## Timing Metrics
### Three Sequencing Methods
![[image_100.png]]
- Flip-FLops: 
- Pulsed Latches: 
- 2-Phase Transparent Latches:

### Setup and hold time
![[image_101.png]]
- Setup time: To make sure latch switch stably, time required for new signal arriving _before_ clock rise edge
- Hold time: To make sure latch switch stably, time required for new signal arriving _after_ clock rise edge

### Contamination Delay and Propagation Delay
![[image_102.png]]
Contamination Delay:  Delay between input signal(or clock) change and output signal changes.
Propagation Delay:  Delay between input signal(or clock) changes and output signal becomes stable.
### Timing Diagrams
![[image_104.png]]
## Storage Mechanisms
![[image_106.png]]
- Only 4 Transisters
- When $\bar Q=0$ and CLK=0, hold
- S is susceptible to noise
- How to get the capacitor in DIC?
	The capacitor can derive from drain and source capacitor of both transistors.

To improve the circuit, use NMOS to give a stable 0.
![[image_107.png]]
- Both pull-up and pull-down keepers
- _Conflict_ at nodes S whenever new data is written.

**Hard to change voltage at node S (positive feedback)**

### Forcing the State
![[image_109.png]]
### Break the Feedback
![[image_110.png]]
- Feedback turned off when writing to the latch.
- No conflict
- Larger clock load and $E_{sw}$
**Why is the inverter connected to signal D put beyond the transmission gate?**
![[image_112.png]]
1. Complex gate circuit (D signal) refers to low drive ability, so use the inverter to improve driving ability of D signal.
2. To keep delay of two transmission gate as the same.
### Summery
![[image_111.png]]
Dynamic storage (DRAM)
- Store state on _parasitic capacitors_
- Only hold state for short periods of time, _require periodic refresh_ (milliseconds )
- Usually simpler, higher speed and lower power.
Static storage (SRAM)
- Preserve state as long as power on
- Positive feedback (_regeneration_) with an internal connection between output and input.
- Useful when updates are _infrequent_ (clock gating).

## Static Latch/Register (Flip-Flop)

### MUX-Based Latch
#### Transmission Gate Version
![[image_113.png]]
#### Pass Transistor Version
![[image_114.png]]
_Note: Non-overlapping clocks refers to high requirement of clocks_
#### Latch Race Problem
![[image_118.png]]
Signal becomes unstable when frequency of combinational circuit  is higher than latch.
Two solution
1. Use pulse latch.
2. Split clocks .
![[image_119.png]]

### Static Register
#### MUX-Based Master-Slave (Edge-Triggered) Register
![[image_115.png]]
![[image_116.png]]
- Two opposite latches
	- Trigger on edge
- master-slave latch should pair
### Latch vs. Register vs. Flip-flop vs. Pulsed-Latch vs. Pulsed Register

### Timing Properties
![[#Timing Diagrams]]
![[image_117.png]]
- Assume propagation delays are $t_{pd-inv}$ and $t_{pd-trans}$, and contamination delay is 0, and the inverter delay to derive $\bar {clk}$ is 0
- Set-up time
	- time before rising edge of call that D must be valid
	- $t_{su}= 3t_{pd-inv}+t_{pd-trans}$
- Propagation delay
	- time for $Q_{M}$ to reach $Q$
	- $t_{c-q}=t_{pd-inv}+t_{pd-trans}$ 
	- $I_4$ has changed at the same time when $I_2$ get changed, so there is no need to count it.
- Hold time
	- time D must be stable after rising edge of CLK
	- Transmission gate get _OFF_ when falling edge comes
	- $t_{hold}=0$

# Lecture 7 Memory
Word: the smallest address unit
Byte: 

## Memory Cores
### Read-Only Memory (ROM) Cells
![[image_123.png]]
![[image_124.png]]

### Flash EEPROM
![[image_125.png]]
- Write: Put high voltage in G to make electrons in the channel enter the floating gate, so that raises Vth from 3.5V to 7V.
- Read:  Put low voltage (lower than raised Vth), if there is no current, then judge the signal as 1
- Erase:  Extract the electrons in the floating gate to reduce Vth.

### SRAM
![[image_127.png]]

Register break the loop, therefore is _faster_ than SRAM.
![[image_126.png]]
- Fast
- Persistent
- Expensive
- Stable

**Why are SRAMs so important?**
- Memories have better power efficiency compared to logic.
- ~99% transistor will be used for SRAMs
- Company with better SRAM design will dominate.

#### An example about an SRAM Cell
![[image_128.png]]
Three states: Terminology(Hold), Read, Write.
##### Read Operation
![[image_129.png]]
- Large number of cells share the same bit-line and word-line. 
- The initial voltages can be 0, VDD or VDD/2.
![[image_130.png]]
- Bitline Delay $=\frac{C_{bitline}\Delta V_{bitline}}{I_{cell}}$
- $C_{biline}$ is large due to large number of cells attached.
- $I_{cell}$ is small due to high density cells.
- $\Delta V_{bitline}$ has to stop decreasing to sufficient high speed.
	So we use the _sense amplifier_ to finish the job.
#### SRAM Cell Analysis
For SRAM sizing, we should consider the limitation of write operation and read operation.
**Read**
![[image_131.png]]
_Note that $BL$ and $\bar {BL}$ are initialed at VDD(2.5V)._
Read-disturb (read-upset): must limit the voltage rise on $\bar Q$ to prevent read-upsets from occurring, otherwise, the stored signal may be changed when reads.
- M1 must be stronger(smaller resistance) than M5 when storing a 1.
- M3 must be stronger than M6 whe n storing a 0.

![[image_133.png]]
$$
\underset{Saturation\ Region}{K_{n,M5}\left((V_{DD}-\Delta V - V_{Tn})V_{DSATn}-\frac{V^{2}_{DSATn}}{2}\right)}=\underset {Linear\ Region}{k_{n,M1}\left((V_{DD}-V_{Tn})\Delta V-\frac{\Delta V^{2}}{2}\right)}
$$

$$
\Delta V=V_{DSATn}+CR(V_{DD}-V_{tn})-\frac{\sqrt{V^{2}_{DSATn}(1+CR)+CR^{2}(V_{DD}-V_{Tn}})^{2}}{CR}
$$
where CR is the Cell Ratio =$\frac{(W_{1}/L_{1})}{(W_{5}/L_{5})}$ should _greater than 1.2_.
Similar constraints on $\frac{(W_{3}/L_{3})}{(W_{6}/L_{6})}$ when storing a 0.
![[image_134.png]]
**Write**
![[image_132.png]]
To write signal 1, the $\bar Q$ side of the cell cannot be pulled high enough to ensure writing of 0 due to the sizing of M1 and M5, so use M4 and M6. 
- M6 must be able to overpower M4 when storing a 1 and writing a 0.
- M5 must be able to overpower M2 when storing a 0 and writing a 1.

![[image_135.png]]
$$
\underset {Linear\ Region}{k_{n,M6}\left((V_{DD}-V_{Tn})V_{Q}-\frac{V^{2}_{Q}}{2}\right)}=\underset{Saturation\ Region}{ k_{p,M4}\left((V_{DD}-|V_{Tp}|)V_{DSATp}-\frac{V^{2}_{DSATp}}{2}\right)}
$$
$$
V_{Q}=V_{DD}-V_{Tn}-\sqrt{(V_{DD}-V_{Tn})^{2}-2\frac{\mu_{p}}{\mu_{n}}PR\left((V_{DD}-|V_{Tp}|)V_{DSATp}-\frac{V^{2}_{DSATp}}{2}\right)}
$$
where PR is the Pull-up Ratio = $\frac{(W_{4}/L_{4})}{(W_{6}/L_{6})}$ should be _smaller than 1.8_.
Make M4 and M6 minimum size while allowing writes.
![[image_136.png]]
**Summery**
![[image_144.png]]
- weak/med should be _smaller than 1.8_.
- strong/med should be _greater than 1.2_.
![[image_145.png]]
Performance is determined by the read operation
- Since it needs to discharge large bit line capacitance through small transistors.
- To accelerate the read time, SRAMs use sense amplifiers while the bit line doesn’t have to make a full swing.

#### SRAM Metrics
- Functionality
	- Data retention
	- Readability
	- Writability
	- Soft errors
- Area
- Power
	- SRAM is _major_ source of ship static power.
#### Static Noise Margin (SNM)

### Dynamic Random Access Memory (DRAM)
![[image_146.png]]
SRAM is simple and reliable but big. To reduce the area which is dominated by the writing and contacts, we can use resistance
![[image_147.png]]
- Reduce SRAM cell size by ~ 1/3
- To minimize the static power dissipation, we want $R_{L}$ large, but hard to get large $R_{L}$ in integrated circuit . 
**What if remove R?**


![[image_148.png]]
So we get 3T DRAM cell.
### 3T DRAM
![[image_149.png]]
- _Write_: $C_{S}$ is charged (or discharged) by asserting WWL and BL1
	- Value stored at node X when writing a 1 is $V_{WWL}-V_{T}$
	- Raising the voltage to a higher value than VDD.
- _Read_: $C_S$’ is “sensed” by asserting RWL and observing BL2
	- Read is _non-destructive_ and inverting (ratioless)
### 1T DRAM
![[image_150.png]]
- _Write_: $C_{S}$ is charged (or discharged) by asserting WL and BL
	- Value stored at node X when writing a 1 is $V_{WWL}-V_{T}$
	- Raising the voltage to a higher value than VDD.
	- The same as 3T DRAM
- _Read_: Charge redistribution occurs between $C_{BL}$ and $C_{S}$
	- Read operation is _destructive_ for 1T DRAM.
	- Contrast to 3T DRAM
- _Voltage swing is small_: typically around 250mV (with VDD=2.5V)
- $Q=CV$, use $Q_{BL}+Q_{S}$ is constant to draw the $\Delta V_{BL}$
$$
\Delta V_{BL}=V_{BL}-V_{PRE}=\cdots =(V_{BIT}-V_{PRE})\frac{C_{S}}{C_{S}+C_{BL}}
$$
Voltage swing is too small to be detected. 
Use _Sense Amp_ to solve the small voltage swing.
![[image_151.png]]

The capacitor $C_S$ is parasitic resistance and too small,

### CAM

# Lecture 08 Timing
![[#MIPS Processor Structure]]
**What are the Key Benefits when pipelining?**
![[image_172.png]]
- Clock cycle only depends on the longest operation.
- No spare time for every part.
Thus working frequency increases.
- But design becomes more complex
- Load of clock improves
- Single data calculation need more time to finish.

## Cycle time and race margin
### Register
![[image_173.png]]
Clock time (max): $T\gt_{clk-Q}+t_{p,max}+t_{su}$
Race Margin(min): $t_{hd,R2}\lt t_{clk-Q,min}+t_{p,min}$
### Flip-Flops

### Pulsed-Latch
## Clock skew and jitter
### Clock Non-idealities
- Clock Skew
	- Spatial variation in temporally equivalent clock edges
	- Deterministic + random
- Clock Jitter
	- Temporal variation in consecutive edges of the clock signal
	- All random
- Variation of the pulse width
	- Important for level sensitive clocking
 
![[image_175.png]]
- Skew
	- Manufacturing device variations in clock drivers
	- Interconnect variations
	- Environmental variations(power supply and temperature)
- Jitter
	- Imperfect clock generation
	- capacitive loading and coupling
	- Environmental variations(power supply and temperature)
### Positive and Negative Clock Skew
![[image_177.png]]
Positive Clock Skew: Clock and data flow in the same direction
$$
\begin{align*}
T+\sigma&\ge  t_{c-q}+t_{plogic}+t_{su}\\
T&\ge t_{c-q}+t_{plogic}+t_{su}-\sigma\\\\
t_{hold}+\sigma&\le t_{cdlogic}+t_{cdreg}\\
t_{hold}&\le t_{cdlogic}+t_{cdreg}-\sigma
\end{align*}
$$
$\sigma\gt 0$: Improves performance, but makes $t_{hold}$ harder to meet.

![[image_179.png]]
Negative Clock Skew: Clock and data flow in the opposite direction.
$$
\begin{align*}
T+\sigma&\ge  t_{c-q}+t_{plogic}+t_{su}\\
T&\ge t_{c-q}+t_{plogic}+t_{su}-\sigma\\\\
t_{hold}+\sigma&\le t_{cdlogic}+t_{cdreg}\\
t_{hold}&\le t_{cdlogic}+t_{cdreg}-\sigma
\end{align*}
$$
$\sigma\lt 0$: Degrades performance, but $t_{hold}$ is easier to meet(eliminating race conditions).
### Clock Jitter
**Longest Logic Path**
![[image_180.png]]
Cause impact on _cycle time_
$$
t_{clk-Q}+t_{p,max}+t_{su,R2}\lt T-t_{jitter}-t_{jitter}
$$
Worst Case Scenario (_Negative_ Skew)
$$
T\gt t_{clk-Q}+t_{p,max}+t_{su,R2}+2t_{jitter}+\sigma
$$
**Shortest Logic Path**
![[image_181.png]]
Cause impact on _race margin_
$$
t_{clk-Q,min}+t_{p,min}-t_{jitter}\gt t_{hd}+t_{jitter}
$$
Worst Case Scenario (_Positive_ Skew)
$$
t_{hd}+2t_{jitter}+\sigma\lt t_{clk-Q,min}+t_{p,min}
$$
## Latch-based pipeline
![[image_183.png]]
CLB_A should start before ② and end before ④
**Slack-Borrowing**
![[image_182.png]]
In fact, Latch-based pipeline make design more flexible and harder.
A little mismatch can be acceptable.
**Time Borowing**
![[image_184.png]]
## Summery
- Cycle Time
	- Positive skew improves performance
	- Negative skew reduces preformance
	- Jitter reduces performance
	- $T\gt t_{clk-Q}+t_{p,max}+t_{su,R2}+2t_{jitter}-\sigma$
- Race Margin
	- Positive skew reduces race margin
	- Jitter reduces acceptable skew
	- $t_{hd}+2t_{jitter}+\sigma\lt t_{clk-Q,min}+t_{p,min}$
- Clock Skew
	- Deterministic difference at each flip-flop
	- Caused by mainly imperfect balancing of clock tree/mesh
	- Accounted for in STA (Static Timing Analysis)
- Clock Jitter
	- Random difference at each flip-flop
	- Caused by on-die process, $V_{DD}$, temperature, PLL jitter, crosstalk, _STA accuracy, LPE (layout parameter extraction) accuracy
	- Accunted for in STA by subtracting _(~3$\sigma$)_ from the cycle time in long path analysis, and adding to reciving clock arrival time in race margin
- Jitter is always bad, while skew can be helpful or harmful
- Clock Uncentainty $\Delta\equiv skew \pm jitter$
- _Latch-Based_ system
	- Data can pass through latch while it is transparent
	- Long cycle of logic can borrow time into next cycle as long as each loop finished in one cycle
	- Latches (pulsed and level-sensitive) allow _more flexibility_
		- And hence can potentially achieve higher performance
		- Latches can also be made more tolerant of clock uncertainty
- _Flip-Flop_ system
	- Data launches on one rising edge and must arrive before next rising edge
		- If data arrives late, system fails
		- If data arrives early, wasting time
	- Flip-flops have _hard edges_
	- Flip-Flop generally easier to use
		- Most digital ASICs designed with register-based timing
# Lecture 09 Clock

## Generation
![[image_186.png]]
### Phase-Locked-Loops (PLL)
![[image_186.png]]
#### Phase-Detector
![[image_206.png]]
Phase-Detector can detect if phase of both signals are the same, accordingly detect if frequency of both signals are the same.
But it can't detect which signal is faster.
Generally we don't use phase-detector.
#### Phase-Frequency Detector (PFD)
![[image_209.png]]
![[image_210.png]]
1. CLR=1
2. $Q_{A}=Q_{B}=0$
3. CLR=0
4. Faster signal arrives.
5. Both signals arrive.
Not only phase, but PFD can also detect the difference of frequency.
![[image_211.png]]

#### Voltage Controller Oscillator (VCO)
![[image_212.png]]
Control Elmore-Delay or charging current.
A current-starved VCO example is as shown
![[image_213.png]]

### Delay-Locked-Loop (DLL)
![[image_188.png]]
- Generate no new frequency, only change phase.
- VCDL: voltage control delay line.
![[image_190.png]]
DLL-Based Clock Distribution 
DLL is usually used in aligning global clock.
## Distribution
### H-Tree
![[image_214.png]]
Recursive pattern to distribute signals uniformly with equal delay over area
By this tree structure, we can also insert clock gating at mutiple levels in clock tree thus we can shut off entire sub tree.

### Multi-level Mesh (Grid)
```image-layout-a
![[image_215.png]]
![[image_216.png]]
```
- Gridded clock distribution was common on earlier microprocessors.
- Flip-Flop directly connected to the nearest grid segment.
- Skew determined by grid density and not overly sensitive to load position.
- Clock signals are available everywhere.
- Tolerant to process variations.
- Usually yields extremely *low skew values*

# Lecture 10 Low Power Design
![[#Power]]
![[#Power/enrgy Design Space]]
![[image_191.png]]
## Design Time
$$
P_{avg}=\alpha_{0\rightarrow 1}\cdot C_{L}\cdot V^{2}_{DD}\cdot f_{clock} 
$$
Obviously, reducing VDD is the most effective method, but it'll increase delay.
$$
T_{d}=\frac{C_{L}\cdot V_{DD}}{I}
$$
Where $I\sim (V_{DD}-V_{T})^{2}$
### Multiple Supplies voltage

### Reducing Leakage in Design Time
**Longer channel can reduces leakage.**
Doubling L reduces leakage by 5 times.
![[image_192.png]]

**Using multiple threshold at cell level**
In non-critical path, increasing threshold voltage will not cause perfermance and dynamic power costs.
![[image_193.png]]
$$
I_{ds}=I_{off}10^{\frac{V_{gs}+\eta (V_{ds}-V_{DD})-k_{\gamma}V_{sb}}{S}}\left(1-e^{\frac{-V_{ds}}{V_{T}}}\right)
$$
## Standby
![[image_194.png]]
The main source of dynamice power in standby mode is the clock.
### Clock Gating
- _Turning off_ the clock to non-active components
- Disconnecting the inputs.
![[image_195.png]]
### Reducing Leakage in Standby
![[image_200.png]]
**Transistor Stacking**
![[image_196.png|206]]
- Simply use more than one transistor to decrease leakage.
- Should trade-off between transistor leakage and speed.
**Power Gating (Sleep)**
![[image_197.png|181]]
- Disconnect module from supply rails
- Impact on perfomance
**Supply Voltage Ramping (SVR)**
![[image_198.png]]
- Reduce supply voltage of modules in sleep mode

**Dynamic Leakage Biasing**
![[image_199.png]]
- Increasing $V_{T}$ during sleep.
- Can also be used to compensate for threshold variations.
## Runtime
**Core Idea: Adapting Design to Variable Workloads**
Useful dynamic design parameters: Vdd and Vth 
Variable Vdd most effective for dynamic power reduction
### Dynamic Voltage and Frequency Scaling (DVFS)
![[image_204.png]]
Use$V_{DDhigh}$ and $V_{DDlow}$ to change working frequency and power.

![[image_205.png]]
- Operating system sets $F_{DES}$
- Ring oscillator delay-matched to CPU critical paths
- Feedback loop sets $V_{DD}$ so that $F_{ERR}$ -> 0
### Self-Adjusting Threshold Voltage Scheme (SATS)
![[image_202.png]]
- Helps to manipulate and control leakage.
- Helps to manage _process and environmental_ variability.