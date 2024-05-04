---
title: MOSFET Model
tags:
  - NoteBlock
---
#### MOSFET
![|575](image_35.jpg)
- **Conductor of polysilicon is between metal and semiconductor?**
- FinFET begin to be used at 22nm node.
- Compared with BJT, low power characteristic of MOSFET allows very high integration
![|575](image_36.jpg)
- The body terminal is at low voltage to avoid PN junction breakovering.
- The gate terminal is at low voltage
    - No current flows, the transistor is OFF
- The gate terminal is at a high voltage
    - **Negative** charge attracted to surface and invert a channel under gate to **n-type**
    - **P-type** bulk silicon provides **minor carriers** to build invert channel.
    - Ideally, $I_GB=0$, but it’ s hard to achieve in fact, because of thin and impure insulator.
**Why pursue thiner insulator?**
$SiO_2$ is a plate capacity, the lower thickness, the more carriers, and the more carriers, the greater or faster current.
![](image_37.jpg)
p+Substrate Tap and n+Well Tap are used to set bulk voltage.

[[Threshold Voltage]]

[[Static Behavors]]

[[Dynamic Behavior]]

[[MOS Capacitor]]

[[Non-ideal Transistor Behaviour]]

