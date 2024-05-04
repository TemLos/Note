---
tags:
  - NoteBlock
---

![](_image/image_59.png)
$$
T_{adder}\approx (N-1)T_{carry}+T_{sum}
$$
So we know $T_{adder}=O(N)$, and  $T_{carry}$ is far more important than $T_{sum}$

![](_image/image_58.png)
For subtraction, we have
$$
A-B=A-\bar B +1
$$
A-B=A+(2’ s complement of B)=A+(1’ s complement of B)+1
2’ s complement: 1000-0001=1111
1’ s complement:1111-0001+0001=1111

## Circuit Design
For a full adder
![](_image/image_60.png)
$$
C_o=AB+BC_i+AC_i
$$
$$
\begin{align}
S&=A\bar B\bar C_i\\
&=ABC_i+\bar C_o(A+B+C_i)
\end{align}
$$

###  Improvement 1 Share Transistors
![](_image/image_61.png)



### Improvement 2 Exploit the Inversion Property
![](_image/image_63.png)


### Improvement 3 Mirror Adder
![](_image/image_62.png)

### Manchester Carry Chain
![](_image/image_64.png)

^MCC
### Fast Carry Chain
![](_image/image_65.png)
### Carry-Bypass (skip) Adder
![](_image/image_66.png)

![](_image/image_67.png)
#### Linear Carry Select
![](_image/image_68.png)

#### Square Root Carry Select Adder
![](_image/image_69.png)

## Look-Ahead Adders


