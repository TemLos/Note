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

[[Landauer Formula]]

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
















