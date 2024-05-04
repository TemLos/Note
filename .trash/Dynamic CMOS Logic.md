---
tags:
  - NoteBlock
title: Dynamic CMOS Logic
---
## Dynamic CMOS Logic 
![[image_22.png]]
### Static Properties
- Dynamic relies on _temporary_ storage of signal on the capacitance.
- Logic function only implemented by PDN, So the number of transistor is _N+2_ while static CMOS need _2N_.
- Full swintg output.
- Nonratioed
- _Lower_ power dissipation
	- _Fewer_ transistors reduce $C_{int}$ and $C_{ext}$
	- No short circuit, all current provided by $C_L$ when pull-down.
- Note: power dissipation can be significantly _higher_ due to
	- higher transition probabilities
	- extra load on CLK (needs a precharge/evaluate clock)
### Dynamic Properties
- _Faster_ swiching speed 
	- _Fewer_ transistors reduce $C_{int}$ and $C_{ext}$
	- Precharge time can be ignored($t_{pLH}=0$), but the presence of the evaluation transistors slows the $t_{pHL}$.
- _No glitching_. By construction can have at most one transition per cycle

![[Dynamic CMOS Logic VS Ratioed Logic]]