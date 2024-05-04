---
tags:
  - NoteBlock
---
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
