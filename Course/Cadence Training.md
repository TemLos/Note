

# Day 1 Introduction
# Day 2  Synthesis
# Day 3 Floorplan
# Day 4 Placement and Optimization
- Global placement
	Route for every area, not lay down any metal traces.
- Detail placement
	Create metal traces and try to remove DRV.
- Row 


- Endcap
	用来保证芯片边界标准单元的物理环境保持 一致，确保标准单元不会出现在 阱的边缘。在芯片的边界、硬核周围都需要插入 boundary cell 。
- Well Tap
	tap cell用于消除芯片的闩锁效应，通过固定间距对衬底施加偏置电压减小衬底的寄生电阻，使三极管压无法达到导通要求从而切断闩锁效应的正反馈环路 ，消除闩锁效应
- Filler
	Filler cell用于填充芯片内部的空白部分。物理版图没有标准单元的区域需要插入 Filler cell，filler cell用于连接芯片内部的扩散层和电源线，使 阱保持连续，满足DRC的检查要求。同时也可以对周围的std cell有一定的保护作用。
- DeCap
	Decap cell，中文名去耦单元，这是一种特殊的Filler cell。当电路中大量单元同时翻转时会导致冲放电瞬间电流增大，使得电路动态供电电压下降或地线电压升高，引起动态电压降，俗称IR-drop。
	为了避免IR-drop对电路性能的影响，通常在电源和地线之间放置由MOS管构成的电容，这种电容被称为去耦电容或者去耦单元，它的作用是在瞬态电流增大，电压下降时向电路补充电流以保持电源和地线之间的电压稳定，防止电源线的电压降和地线电压的升高。在电源电压正常的时候，Decap可以充电来存储能量，当电源电压较低的时候就可以放电来起到一定的缓冲作用。
  
- Tie Cells
	Tie cell，又称为钳位单元。常见的有tie high，tie low两种，分别提供电源地电位。
	主要起到ESD保护的功能。通常在placement之后，route之前添加。
	![[image_230.png]]
- Antenna Cells
	天线效应是集成电路制造过程中经常发生的现象，原因在于连接在栅极的金属会不断收集电荷，在某个临界节点将会放电到栅极引起晶体管损坏。
	解决的办法之一就是插入antenna cell来增大栅极的面积，也就是提高承受放电电流的能力。在后端设计中，通常在绕线阶段让工具在发现有antenna violation的时候自动插入antenna cell。
- Spare Cells
	spare cell就是备用的cell。 简单来说，就是每块地方洒一些类似DFF，NAND，AND，XOR，INV等的备用cell, 为以后做function eco和metal eco用。
- MIMCAP
	最后介绍一下MIMCAP，其中MIM指的是Metal-Insulator-Metal，这是一种特殊类型的用来提供电容的cell，区别于DECAP的主要特点是电容量较大，大小也比一般的std cell要大很多，而且使用的金属层一般比较高，可以重叠放在绝大部分类型的cell上而不产生DRC。
	通常在小尺寸的工艺上，mimcap layout的下极板需要先先到top metal，然后再连下去。因为电容在工作过程中，上下极之间存在一定压差，由于MIM之间的介质较薄，容易发生类似天线效应的情况，即把介质层击穿，因此才采用将下极板连接重新接回TOP METAL，以避免类似天线效应的发生。
	![[image_231.png|525]]


## Scan Chain Optimization
- Scan Cells
- Scan Chain
- optimization
### optimization
Timing optimization
- Setup/drv
- Hold
- SI

Transform

# Day 06 CTS
latency
- Source Latency
	From clock source to module
- Network Latency
	Latency exits inside the module

Clock trees
- Physical constraints
- DRV NDR
Skew groups

PreCTS
- ldeal clock
- Virtual skewing
PostCTS
- Propagated clock
- Buffering/sizing to skew

Function of CTS
- Physically
	- Insert buffers or inverters
	- Upsize and downsize clock cells
	- Legalize clock cells
	- Route clock nets
- Timing constraints
	- Latency target
	- Skew target
	- Transition target
	- Max capacitance
	- Max length
# Day 07 Routing
- Track
	No real wire width.
- Pitch
	distance between tracks, defined in TF file.
- Grid Point
	Crosspoint of tracks.
- Trace
	Contains metal real wire with width.

- Channel 
	
- Switch Box
	




