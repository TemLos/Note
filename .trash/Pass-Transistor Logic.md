---
tags:
  - NoteBlock
title: Pass-Transistor Logic
---
## Pass-Transistor Logic
![[image_23.png]]
![](image_17.png)
### Static Properties
- _Less_ transistors and lower design difficulty
	- N transistors instead of 2N.
- Gate is static
	- a path exists to both supply rails under all circumstances
- No static power consumption
- Ratioless
- _Bidirectional_ (versus undirectional)

### Signal Degradation
![[image_27.png]]
Pure PT logic is not regenerative - the signal gradually degrades after passing through a number of PTs. 
![[image_24.png]]
It can be even worse due to _body effect_.
### Static Power Consumption
Threshold voltage drop causes static power consumption (M2 may be weakly conducting forming a path from VDD to GND)

#### Solution #1: Level Restorer
![[image_28.png]]

- Full swing
- No static power consumption
	- No static power by inverter
	- No static backward current path through Level Restorer and PT since restorer is only active when A is high
- _Ratioed_. For correct operation Mr must be sized correctly
	- increases the capacitance at x, slowing down the gate;
	- increase $t_{rise}$, but decrease $t_{fall}$
![[image_29.png]]

#### Solution #2: Multiple VT Transistors

![[image_31.png]]

Impacts static power consumption due to subthreshold currents flowing through the PTs (even if VGS is below VT )

#### Solution #3: Transmission Gates (TGs)
**Most widely used solution**
![[image_30.png]]
- Full swing.
- Bidirectionsl.