---
tags:
  - NoteBlock
title: Static CMOS Logic
---
## Static CMOS Logic
### Design
### NAND Gate
![](_image/数字集成电路设计_image_81.jpeg)

### NOR Gate 
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
To optimize the critical path, a reference book on timing analysis
[[Timing.pdf]]
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
|Active(Dynamic)|Logic Design<br>Reduced Vdd<br>Transistor Sizing<br>Multi-Vd|Clock Gating|DFS,DVS|
|Leakage(Standby)|Multi-Vt<br>Stach effect<br>Pin ordering|Sleep Transistors<br>Multi-Vdd<br>Variable Vt<br>input control|Variable Vt|



























