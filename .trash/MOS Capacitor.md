---
tags:
  - NoteBlock
---
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
At pinch-off point, $V_GC=V_T$**?未完?**, In bottom line, $C_{GCS}=2/3WLC_{ox}$
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
