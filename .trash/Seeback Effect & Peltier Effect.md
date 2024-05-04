---
tags:
  - NoteBlock
title: Seeback Effect & Peltier Effect
---
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



