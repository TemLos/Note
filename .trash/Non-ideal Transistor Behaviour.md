---
tags:
  - NoteBlock
---
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
v_{eff}&=v_{sat}=\frac{\mu_{eff}\cdot E_C}{2},\quad for\ E\ge E_C
\end{align}
\end{cases}
$$
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
&=\frac{\mu_{eff}C_{ox}}{1+\frac{V_{DS}}{E_CL}}\cdot \frac{W}{L}\cdot[(V_{GS}-V_t)V’_{DSAT}-]\frac{V^{,2}_{DSAT}}{2}]\\
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
- Short/Narrow Channel Effect
- Drain-Induced Barrier Lowering(DIBL)
		High drain voltage causes current to increase.
$$
V_t’=V_t’-\eta V_{ds}
$$
**How to induce DIBL?**
![](image_73.jpeg)
###### Leakage
![550](image_74.jpeg)

###### Temperature Sensitivity
Current in sub-threshold region
$$
I_{ds}=I_{ds0}\cdot e^{\frac{v_{gs}-V_{t0}+\eta V_{ds}-k_\gamma V_{sb}}{nv_T}(1-e^{(-V_{ds}/v_T)})}
$$
###### Process and Environmental Variations
- Supply voltage
- 
