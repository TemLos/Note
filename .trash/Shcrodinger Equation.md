$$
E_{\psi}=H_{\psi}
$$

To find DOS , m* and so on, we need to know E-K relationship.
To find out E-K relationship, we need to build and solve shcrodinger equation.

![[Crystal]]

### Wave Equation
![](_image/image_56.png)

$$
E=-\frac{Zq^2}{4\pi\varepsilon_0r}+\frac{mv^2}{2}=-\frac{Zq^2}{8\pi \varepsilon_0r}
$$
For single atom
$$
E_n=-\frac{Z}{n^2}\frac{q^2}{8\pi \varepsilon_0a_0}
$$
$$
\begin{align}
a_0=\frac{4\pi\varepsilon_0h^2}{mq^2}\\
n=\frac{2\pi r mv}{h}
\end{align}
$$
where r is Bohr Radius
$$
r_n=\frac{4\pi \varepsilon _0 h^2}{mq^2}\times \frac{n^2}{Z}
$$
![](_image/image_57.png)

To find out wave function of N atoms,  we find single atoms firsly
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
E_{\psi}(\vec r)=\left(-\frac{h^2}{2m}\nabla^2+U(\vec r)\right)\psi(\vec r)
$$
where
$$
U(\vec r)=-\frac{Zq^2}{4\pi \varepsilon_0 r}
$$