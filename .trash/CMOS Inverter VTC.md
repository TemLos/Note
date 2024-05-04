---
title: CMOS Inverter VTC
tags:
  - NoteBlock
---
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
