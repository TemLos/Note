---
tags:
  - NoteBlock
---
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


![[Dynamic CMOS Logic VS Ratioed Logic]]