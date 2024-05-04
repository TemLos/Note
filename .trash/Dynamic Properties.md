---
title: Dynamic Properties
tags:
  - NoteBlock
---
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
[[Fan-out 4]]