---
tags:
  - NoteBlock
---
[9. Short Channel Effect and Reverse Short Channel Effect — devices v1.0 documentation](https://eng.auburn.edu/~niuguof/elec6710dev/html/subthreshold.html)
[关于不同工艺节点mos VTH的短沟道和反短沟道效应解释 - Analog/RF IC 设计讨论 - EETOP 创芯网论坛 (原名：电子顶级开发网) -](https://bbs.eetop.cn/thread-364983-1-1.html)
- Reverse Short Channel Effect (RSCE)

- Inverse Narrow Width Effect (INWE)
Inverse Narrow Width Effect（INCE），即反窄宽度效应，是CMOS器件工艺中的一种现象。在传统的窄宽度效应（Narrow Width Effect）中，随着沟道宽度的变窄，器件的阈值电压Vth会增大。然而，在某些情况下，特别是对于采用浅沟道隔离（Shallow Trench Isolation, STI）技术的MOSFET，随着沟道宽度的减小，阈值电压Vth反而降低，这种现象被称为反窄宽度效应。

反窄宽度效应的物理本质与边缘电场有关。在STI MOSFET中，由于STI wall的作用，沟道宽度方向的边缘电场的电力线实际上是在沟道方向集中，因此会出现阈值电压随着沟宽W的减小而减小的现象。这种现象与具体的集成电路工艺，例如器件采用的隔离方式和隔离区域的掺杂浓度等关系很大。

在文献中提到，对于表面沟道STI MOSFET，随着沟道宽度W的减小，阈值电压Vth降低，这被称为反窄沟道效应（INCE）。与此相反，埋沟道STI MOSFET显示出传统的窄沟道效应，即随着沟道宽度W的减小，阈值电压Vth增加。