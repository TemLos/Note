# Virtuoso
[cadence virtuoso PEX 寄生参数提取及后仿真\_pex提取寄生参数-CSDN博客](https://blog.csdn.net/weixin_42221495/article/details/134474216)

[ADE后仿真问题 - Analog/RF IC 设计讨论 - EETOP 创芯网论坛 (原名：电子顶级开发网) -](https://bbs.eetop.cn/thread-322566-1-1.html)


"input.scs" 22: The instance \`I129' is referencing an undefined model or subcircuit, \`subcircuit\'. Either include the file containing the definition of \`subcircuit\', or define \`subcircuit\' before running the simulation.
[input.scs没有识别到自己建的原理图 - Layout讨论区 - EETOP 创芯网论坛 (原名：电子顶级开发网) -](https://bbs.eetop.cn/thread-974206-1-1.html)

ERROR (CMI-2440): "/home/hwpll20/tsmc28/tsmcN28/../models/spectre/./cln28ull_1d8_elk_v1d8_3.scs" 24534: I0.MM16@1943:  The length, width, or area of the instance does not fit the given lmax-lmin, wmax-wmin, or areamax-areamin range for any model in the \`[I0.MM16@1943.pch](mailto:I0.MM16@1943.pch)\' group. The channel width is 3.000000e-06 and length is 1.200000e-07. Specify channel width and length that do not exceed the referenced maximal area Lmax=9.001000e-07, Lmin=2.700000e-08, Wmax=2.700100e-06,and Wmin=9.000000e-08. You can choose the nearest model by setting the value of \`soft_bin\' option to \`allmodels\'.
[28nm工艺后仿的时候遇到了管尺寸的问题 - Analog/RF IC 设计讨论 - EETOP 创芯网论坛 (原名：电子顶级开发网) -](https://bbs.eetop.cn/thread-907686-1-1.html)



Explore usage of the ruler
>You would be wise to explore the manual located in $CDS/IC/doc you are looking for the vlehelp folder (find $CDS/IC/doc -name "*vlehelp*" will locate it and you should use this for finding other manuals such as viva the schematic editor (comphelp is the name of the Virtuoso Schematic Editor L). You should look at: Using Rulers (this one is important), Creating Rulers with Smart Snapping, Setting Up Snap Mode, Creating Rulers with Snapping On, and a whole host of others. With rulers, you can cycle through the snap modes (anyAngle -> diagonal -> orthogonal) by pressing the N bindkey or clicking the Synchronized SnapMode icon on the Options toolbar.
### Basic level
>一般的工艺上来说，基本的层次会有以下一些：  
DNW：深N阱层，主要是起隔离的作用  
Nwell：N阱层 ，主要是用来做衬底和隔离  
diff：有源区层，主要是用来做mos管的源、漏和衬底接触。  
poly1：多晶硅层，主要用来做mos管的栅极，电阻，电容等。  
cont：通孔  
metal：金属1  
via12：通孔  
metal2：金属2  
via23：通孔  
metal3：金属3

>以tsmc65N为例：PO是poly[多晶硅](https://zhidao.baidu.com/search?word=%E5%A4%9A%E6%99%B6%E7%A1%85&fr=iknow_pc_qb_highlight)，OD+NP是N+，OD+PP是P+，NW是N井，M1~8是金属1~8，比较常用的就这些吧貌似。
>PO(17) ： poly gate， gdsii number 17 ，  
CO(30), ： contact  
RV(85)：  via between toplevel metal and AP，  
AP,： Alpad，  
CB,： bondpad window  
CB2, ： bondpad window 2 layers  
NP： selected P implantation  
NW ： nwell  
CD, ： critial dimension，  
PP(25) ： P implantation  
SDI分别指代什么意思？ ： esd label，
