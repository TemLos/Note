# Lecture 1 Introduction
姓名：李忠昶；
问题：模拟信号和数字信号的区别；
答案：区别之一是，模拟信号精度高、信息含量高，但容易受到信道中的噪声干扰，数字信号抗信道噪声干扰的能力较好，且受到干扰后容易恢复。

姓名：胡安喜
问题1：Leff和Ldrawn有什么区别
Leff是有效沟道长度，Ldrawn是版图中的沟道长度。在生产MOS管的过程中，源极和漏极会向栅极下面扩散，导致Leff小于Ldrawn。
问题2：MOS管栅源电压大于阈值电压后，在漏源之间加上电压，沟道的宽度为什么会在源端宽而在漏端窄
漏源之间有电势差，所以从栅极到栅极下面的衬底之间的电压差是是随源极到漏极而变化的，则不同位置的反型层厚度不一样。也可以理解为：靠近漏端的电荷被吸引进漏端了。

姓名：何丁赋；
问题：模拟信号和数字信号的区别；
答案：形态上，模拟信号是幅值和时域上都连续的信号，数字信号是幅值和时域上都离散的信号。

姓名：金勇健 问题：为什么不能用ADC对模拟信号直接采样? 回答：ADC受限于其转换位数和转换速率，无法对任意幅值和频率的信号进行准确的模数转换，因此需要前级模拟电路对微弱信号放大，或对高频信号下变频

姓名：杨亚龙
问题1：为什么能对模拟信号直接采样
答案：在对模拟进行放大、降噪等处理实时性更好，占用的资源更少。
问题2：栅极、源极、漏极如何区分
答案：栅极控制MOS管开关，源极是载流子的来源，载流子从源极流出，流入漏极

# Lecture 2 MOS Device Physics



Transit Frequency
- With Frequency increasing, transconductor becomes less than 1.
- That is because input capacitance decreases, so input voltage decreases and inducing current is lower.
- Lower channel length brings higher $F_{T}$ and larger mismatch.
 - $\omega = 2\pi f_{T}$

MOSFET
$R_{on}=\frac{V_{DS}}{I_{D}}|_{vds}=\left(\partial \frac{I_{D}}{\partial V_{DS}}\right)^{-1}$

$$
\begin{align*}
V_{TH}=\Phi_{MS}+2\Phi_{F}+\frac{Q_{dep}}{C_{ox}}\\
\Phi=\frac{kT}{q}ln(\frac{N_{sub}}{n_{i}})\\
Q_{dep}=\sqrt {4q\varepsilon_{si}|\Phi_{F}|N_{sub}}
\end{align*}
$$
Deep Triode Region
Behave like a variable resistor
![[image_233.png|450]]
$$
\begin{align*}
V_{DS} &\ll 2(V_{GS}-V_{TH})\\
I_{D}&\approx \mu_{n}C_{ox} \frac{W}{L}(V_{GS}-V_{TH})V_{DS}  
\end{align*}
$$
Triode Rergion
$$
\begin{align*}
I_{D}=\mu_{n}C_{ox} \frac{W}{L}[(V_{GS}-V_{TH})V_{DS}- \frac{1}{2}V_{DS}^{2}]
\end{align*}
$$
Saturation Region
$$
\begin{align*}
V_{DS}&\gg V_{GS}-V_{TH}\\ 
I_{Dmax}&= \frac{1}{2}\mu_{n}C_{ox} \frac{W}{L}(V_{GS}-V_{TH})^{2}
\end{align*}
$$
For transconductance
$$
\begin{align*}
g_{m}&= \frac{\partial I_{D}}{\partial V_{GS}}|_{V_{ds},constant}\\
&= \mu_{n}C_{ox} \frac{W}{L}(V_{GS}-V_{TH})\\
&= \sqrt {2\mu_{n}C_{ox} \frac{W}{L}I_{D}}\\
&= \frac{2I_{D}}{V_{GS}-V_{TH}}
\end{align*}
$$
Second Order Effect
Bulk Effect
$$
V_{TH}=V_{TH0}+\gamma (\sqrt{2\Phi_{F}+V_{SB}}-\sqrt{2\Phi_{F}})
$$
Channel Length Modulation
$$
I_{D}\approx \frac{1}{2}\mu_{n}C_{ox} \frac{W}{L}(V_{GS}-V_{TH})^{2}(1+\lambda V_{DS})
$$
$$
\frac{\Delta L}{L}=\lambda V_{DS}
$$
MOS Capasitance
![[image_234.png]]

MOSFET small-signal model


Overdrive Voltage: $V_{GS}-V_{TH}$
Bipolar

$$
\begin{align*}
I_{C}=I_{S}exp\left(\frac{V_{BE}}{V_{T}}\right)\\
V_{T}=kT/q=25mV@300K\\\\
g_{m}=\frac{\partial I_{C}}{\partial V_{BE}}=\frac{I_{C}}{V_{T}}\\
g_{m}r_{\pi}=\beta\\
I_{C}=\beta I_{B}\\
r_{e}=\left(\frac {\partial I_{E}}{\partial V_{BE}}\right)^{-1}=\frac{1}{g_{m}}
\end{align*}
$$

T-Model

$\pi$-Model


姓名：王禁城；
问题：公式里哪一项代表了掺杂浓度；
答案：N

姓名：郑博中；
问题1：模拟信号和数字信号的区别；
答案：传输方式不同，模拟信号是用模拟量的电压或电流来表示的电视信号；数字信号是通过0和1的数字串所构成的数字流来传输的。
问题2：问黑板上的信号图是什么信号
答案：因为信号的幅值有出现小数，虽然跳变但并不是离散的，所以是模拟信号
问题3：为什么不能用ADC对模拟信号直接采样?
答案：猜的是因为要先对光信号，声信号的这些进行信号转化成电信号才能采样

姓名：张蕴川
问题：为什么要有模拟放大器和滤波器
回答：放大器可以在adc前进行阻抗匹配，也用于对抗传输时的衰减。滤波器可以将模拟信号中adc不易处理的部分提前滤除

# Lecture 3 Single Stage Amplifier

[zhuanlan.zhihu.com/p/564083453](https://zhuanlan.zhihu.com/p/564083453)
$r_{o }= \frac{1}{\lambda I_{D}}$
$\frac{1}{g_{m}}\ll r_{o}$                                             
$g_{m} r_{o}$ of short channel device should be 5~10

Method of extracting pole and zero
- Dominant pole
- Open circuit time constant
Common Emitter


Common Source








姓名：兰林涛
Q1: 为什么饱和之后电流还会上升？
A：有效长度减小 沟长调制效应
Q2:为什么gm有可能随着vgs-vth增加而减少
A：id恒定时 gm和vgs-vth倒数关系
Q3:为什么增益电压不能无穷大
A：输入电压以及能量有限 器件受到限制
Q4:为什么噪声不能是零噪声
A：因为非绝对零度的情况下 有分子热运动热噪声

姓名：周雨欣 
问题：为什么运放噪声不能是零？
答案：运放噪声和电路工艺和缺陷有关，不同的工艺会导致不同的电路缺陷

姓名：徐嘉诚
问题：为什么运放的功耗不能是0
答案：mos管工作的时，会有一个最小的使栅极开通的电流，就会产生功耗

姓名：张蕴川
问题1：为什么饱和电流与VDS无关
回答：因为饱和时，电流是载流子由沟道扩散到耗尽区然后被vds产生的加速电场加速而产生，载流子数目由扩散特性如制程材料温度等决定，和加速电压无关

问题2：如何判定使用小信号模型还是大信号模型：
回答：当信号小到在该工作点左右电路可近似认为工作在恒定状态，具有固定性质时，可用小信号模型；当信号大到会导致电路工作状态改变较大，无法近似认为在全部工作点保持同样特性时，用大信号模型

问题3：放大器的压摆率（当时看错，在“压摆”问题回答）为什么不能无限大
回答：电容和电感必然存在，它们的充能需要时间

姓名：薛诚浩
问题：为什么输入阻抗要无穷大 输出阻抗要无穷小？
答案：输入阻抗无穷大 电路分得的电压就无限接近于电源电压 而输出阻抗无穷小 电路可以提供最大功耗給负载

姓名：李忠昶
问题：如何判定使用小信号模型还是大信号模型？
答案：当系统处于稳态状态时，可以使用小信号模型；对应地，当系统处于暂态过程时，需要使用大信号模型。（被指出答案不完善）

姓名：高亦辰
问题：什么情况下可以用小信号模型
答案：一定输入电压、电流幅度范围内可以使用，被指出应该是在工作状态、增益恒定、工作点不变时可以使用

姓名：金勇健
问题1：为什么运放的功耗不能为零？
回答：只要运放是在正常工作的，就会有MOS内部的导通电阻，以及提供直流偏置的电阻元件，这些阻性元件都是耗能的，因此功耗不会为零。
问题2：什么是运放的线性度？
回答：从运放的小信号分析来说，我们希望运放输入的信号摆幅较小，这样可以近似认为运放工作的直流偏置不变，跨导gm不变，提供Id=gm x vgs的线性增益。如果输入信号过大，则gm不能近似认为不变，增益非线性，会导致运放输出失真。

姓名：周雨欣
问题1：源跟随器的作用
回答：输出电流和输入电流一致，（增强驱动力）。

姓名：杨亚龙
问题1：源跟随器的作用
回答：让前端的电路和后端的电路不相关（隔离作用）
问题2：怎么让casocode stage更接近理想电流源（降低两段的压降）
回答：增大宽长比

姓名：王禁城
问题1：源跟随器的增益为什么无法达到1
回答：因为体效应的存在，从公式能直观得到

姓名：程子昂
问题1：为什么source degeneration resistor会使NMOS从drain看如的阻抗大于ro+Rs
回答：Rs引入了Id->Vgs的负反馈，使得动态阻抗增大

姓名：金勇健
问题1：电阻负载的共源极放大器，从MOS的源极看过去输入阻抗是多大？
回答：近似为1/gm。
问题2：Cascode结构的缺点有什么？
回答：由于共栅管需要多消耗一个过驱动电压，致使Cascode结构的输出摆幅减小

姓名：张蕴川
Q1：源级跟随器作用：
A1：阻抗变换
Q2：源级跟随器为什么Av不等于1
A2：Id改变的结果是要以Vgs变化为原因的，所以源级电压不能完全跟随栅极
Q3：cascode的优点
A3：更大的增益，（同增益下）更高的带宽，扩展器件耐压

姓名：何丁赋
问题：为什么传递函数表达式更喜欢比值而不是绝对值？
回答：因为同一批次芯片受工艺影响的偏差是类似的，做比可以抵消一部分工艺偏差的影响，从而让实际电路拥有更高的精度

# Lecture 4 Differential Amplifier

姓名：石擎
问题：单端放大器已经很好了，为什么要用差分放大器？
答：差动放大器通过并联两个单端放大器，可以将电路中产生的部分噪声抵消。但差动放大器并不能消除电路中的全部噪声

姓名：张蕴川
问题：带尾电流源的差分对为什么不放大共模信号
回答：恒流源阻抗极大，电流变化趋势会在其两端产生强烈的电压变化，即两差分管的源级电压也会变化，最终Vgs几乎不变，所以Id几乎不变，共模输入没有被放大到输出信号

姓名：杨亚龙
问题：共模输入高时，为什么差动电路输出的上端平了
回答：输出可能超过了vdd，波形就失真了

姓名：佟雅文
问题：当Vin,cm较小时，M1和M2在什么区间工作
答：饱和区，Vin较小时，M3在线性区工作，P点电压小，总电流小，Vout=Vdd-1/2I,其值较小，导致Vds大。

姓名：李嘉毅
问题：对称电路中Vin1和Vin2差动变化，为什么Vp不变？
答：Vin1和Vin2的变化大小相等方向相反，使得两边流过P点的电流发生变化，且一边电流的减小量等于另一边电流的增加量，两者影响相互抵消（流入P点寄生电容的电荷等于流出的电荷），因此P点电压保持不变。

姓名：兰林涛
Q1:在0-v1区间m3为什么处于triode region
A：因为vp比较小 m3的vds小 处于线性区
Q2：在大于v2区间m1m2为什么处于线性区
A：因为vp继续增大 vout不变 m1m2的vds减小进入线性区

# Lecture 5 Current Mirror
姓名：李卿熠
问题：为什么在控制宽长比时，通常改变宽度而不是长度？
回答：因为对于某一个工艺节点来说，能做到的器件的尺寸L是固定的，此外，在画版图时可以更容易地通过复制、重叠的方式增加W。

姓名：张蕴川
问题：为什么电流源电容不能为0
回答：电流源通常由一根mos管实现，其漏极与栅极、源极之间都有分布电容，而栅、源极相当于交流接地，所以漏级会有对地电容。
问题：为什么电流镜不把另一个mos的漏级也连接到栅极
回答：这样相当于让漏级通过一个vgs直接接地，破坏了其高阻抗特性，也消除了其漏级可作为大压摆负载的能力

姓名：李忠昶
问题：为什么无法使用饱和区MOS管提供任意大电流？
答：当V_DS足够大时，载流子浓度趋向饱和，也就是V_DS等于饱和电压时，会出现饱和漏源电流

姓名：何丁赋
问题：为什么电流镜输出阻抗不能做到无穷大？
答：因为存在沟道长度调制效应，会引入电阻ro，使得电流总会跟随电压变化少许

姓名：佟雅文
问题：为什么在低压共源共栅电流镜中要将Vb设为较小值？
答：因为Vgs1+Vth2需要大于Vb,如果Vb较大，则Vgs1和输出点的电压也会相应比较大，限制了输出电压的摆幅

姓名：王禁城
问题：在低压共源共栅电流镜中要将Vb设为较小还是较大？
答：较大，因为当vgs较大时，W/L较小，整个电路版图的面积也会减小

姓名：杨亚龙
问题1：为什么实际情况下，做不到电压余度为零？
答案：因为cmos工作在饱和区的话必须要有Vds大于过驱动电压，所以headroom不能为零。
问题2：为什么电流不能是无限大的？
答案：因为过大的Vgs或Vds都会损坏晶体管。
问题3：为什么使用电流镜放大电流时经常增大W而非减小L。
答案：因为在工艺上减少L更困难或精度不高

姓名：金勇健  
问题：电流源输出headroom以及大电流两个要求的折中设计体现在哪里？  
回答：MOS管用作电流源要求其工作在饱和区，需要满足VDS>VGS-VTH。同时，根据饱和区电流公式 ![](file:///E:\Tencent\QQ_File\1205361839\nt_qq\nt_data\Pic\2024-05\Ori\7c6b26d038c5204eb209b11f4b778298.png)  
，更大的输出电流往往需要更大的栅源电压，增大了VDS。

姓名：李嘉毅
问题1：输出阻抗和寄生电容的折中设计体现在哪里？
回答：输出阻抗反比于沟道调制系数，r0=1/λI（D），λ正比于delta(L)/L，因此r0越大，λ越小，L变大，面积就会增加，寄生电容就越大。 
问题2：PPT第八页电路图中通过M3的电流是多大？
回答：0.5I（REF），I（T）=5I（REF），流过M1的电流为2.5I（REF），流过M5的电流为2I（REF），因此流过M3的电流为0.5I（REF）

姓名：何洪权
Q：为什么在控制宽长比时，通常控制宽度而非长度？
A：调整宽度比长度更容易且更精确，例如，可以将两个MOS并联得到宽长比为2W/L。

请问mos管导通状态下的总阻抗大概在什么量级呀
导通电阻大概是几kΩ级别（L=45nm，W=90nm）


# Lecture 6 Frequency Response
![[Digital Integrated Circuit#MOS Capacitor]]
One cap brings one pole and one zero.

Find zero: find a freq. at which the output is 0 no matter what $V_{in}$ is.
Find pole: find a freq. at which the output is $\infty$ no matter what $V_{in}$ is.

Gain increases with 20dB/dec when going through a zero
Gain decreases with 20dB/dec when going through a pole

Miller Effect
![[image_235.png]]
_Note_: The gain of this OP is negative.
$$
\begin{align*}
Z_{1}&= \frac{Z}{1+A_{V}}\\
Z_{2}&= \frac{Z}{1+A^{-1}_{V}}
\end{align*}
$$
Only in such conditions can Miller Effect be used: there are more than one path between input and output.

Disadvantages of Miller Effect:
1. It may eliminate zero
2. It may forecast additional pole
3. It is hard to calculate output impedance accurately

姓名：孔震航
Q：模拟电路分析中字母和角标的大小写的含义。
A：字母大小写代表交流或直流，角标大小写代表有效值或瞬时值。

姓名：程子昂
Q：单臂有源负载差分对的差模信号增益表达式中为何出现2ro
A：在交流等效电路中M1与M2呈现串联关系

姓名：李嘉毅
Q：单端输出有源负载差分对的差模信号增益表达式中为何出现2ro？
A：从上往下看串联的电阻1/gm要被放大gm*ro2倍，因此Rout=2ro2

姓名：王禁城
Q：单端输出Vf和vout是否相等
A：相等，因为电流相同的情况下负载也相等，所以电压相等

姓名：张蕴川
问题：Vf和Vout是否相等，理由是什么
回答：假设Vout和Vf之间有连接线，此时电路完全对称，两点电压相等，连线上无电流，根据“去掉无电流的线对电路无影响”的原理，将假想的线去掉，两点电压仍相等

姓名：佟雅文
问题1：为什么在计算偏置电压时都是V和加标都是大写？四种电压符号分别表示什么含义？
答：在通常应用中vDS=VDS+vds。因为计算偏置电压时都是直流大信号，所以都是大写。
问题2：在generate Vb时，怎样设置宽长比使M7的VGS=VTH
答：将W/L设置在较大值，由于流过M7的电流由电流源提供，是恒定值，所以当W/L较大时，需要的（VGS-VTH）较小

姓名：宁晨康
问题：为什么放大器电压伯德图上是20dB/dec下降
答：为了和功率比较相称，P=U^2/R 在10logU^2 即 20logU 转化为10logP

# Lecture 7&13 Noise, Non-linear and Mismatch
姓名：陈洪堃
问题：左平面零点和右平面零点有什么区别？
答：左平面零点在系统中意味着是非因果系统，右平面零点意味着系统是因果系统。左平面零点会引发输入之前的响应，右平面零点会引发输入之后的响应。左右平面代表着不同的相位偏移

姓名：黄珏
问题：如图阻抗里为什么有cgd，cgs，和gm这一项
答：x点通过cgd和cgs两个电容分压在mos栅极产生电压，再通过跨导影响x点的输入电流，最后等效为一个与cgs，cgd以及gm相关的等效电阻。

姓名：何丁赋
问题1：为何高频时源跟随器的输出阻抗约为Rs？
答：因为高频下电容Cgs近乎短路，压控电流源gmV1中的V1约为0，PPT chap6 Page15中的电流I将只从左侧流入，因此输出阻抗约为Rs。
问题2：为何差分对中镜像点处的极点约为gmp/Ce?
答：因为此处的电容表达式为Ce，电阻为二极管连接的M3和M1的漏极电阻并联(1/gmp3)//ro1≈(1/gmp3)。因此极点表达式为1/((1/gmp3)*Ce)=gmp/Ce.

姓名：佟雅文
问题1：为什么在频率为0时source follower的Zout为1/gm?
答:在频率为0时CGS相当于断开，此时Zout为NMOS源端向上看的阻抗，即1/gm。
问题2：为什么cascode中X点的极点表达式中为2CGD1？
答：CGD1在X点的等效密勒电容为（1-1/A）CGD，此处的增益为-gm1/(gm2+gmb2)~-1,因此此处的等效密勒电容为2CGD1。

名：张蕴川
问题：为什么电阻热噪声和R，T有关：
回答：电阻热噪声是电子在导体中迁移时与原子核作用发生散射和碰撞产生的，T高则原子核运动剧烈，R大则原子核相对自由电子浓度高，都会造成迁移电子碰撞概率增加，因此噪声增加。
问题：如何理解mos管电流噪声模型公式中噪声与gm成正比
回答：该模型将实际mos管看作无噪声管和噪声电流源并联，无噪声管内是一个与vgs相关的电流，当源栅都接地时相当于恒流源，gm越大该电流源越理想，即内阻越大，则噪声电流源在其上产生的压降越大，噪声电压越大。反之若gm极小，则管内恒流源极不理想，内阻极低，其电流可任意变化，可将噪声电流完全“吸收”，漏极则不会检出噪声电压。

姓名：程子昂
Q1：为什么等效噪声电流公式中R在分母上？
A1：在电阻的等效噪声电压模型中v^2=4kTR，串联电阻为R，通过诺顿等效为电流源与R并联，等效噪声电流应为v^2/R^2=4kT/R。
Q2：为何RC网络的热噪声与电阻值无关，与电容量呈反比？
A2：因为电阻噪声功率与R呈正比，RC滤波器的截止频率与R呈反比，即RC滤波器传函^2PSD曲线下的面积与R和C分别呈反比，三者共同决定的等效噪声功率中R的作用相抵消，只有C的作用。

姓名：杨亚龙
问题1：信号在滤波前后，从时域波形看有什么变化？
回答：信号的毛刺减少了，即高频成分被滤掉了。
问题2：为什么电阻热噪声噪声4kRT与温度T成正比？
回答：温度越高，电子的热运动越剧烈，所以热噪声越大。

姓名：陈洪堃
问题：为什么MOSFET中随着频率越高，flicker noise越小？
答：因为当频率越高时，载流子运动速度变化很快，整体上来说不容易被俘获，从而不容易产生能态释放效应，进而减少闪烁噪声。

# Lecture 8 Feedback
姓名：何丁赋
问题：slides中的负反馈框图中，若反馈点处的“-”改为“+”，是否还能形成负反馈？
答：可以。如果正向通路与反馈回路使得反馈信号相位恰好滞后原信号180度，则在反馈处会导致同相信号与反相信号相加，形成负反馈

姓名：宁晨康
Q：为什么带源级负反馈的共源极电路线性度更强？
A：当输入信号变大，电流上升，MOS管源级电压上升，VGS下降，形成反馈，电路线性度提升

姓名：孔震航
Q：为什么器件面积越大，工艺导致的阈值电压误差越小
A：面积更大，制造导致的误差占比越小，越不容易受影响

姓名：张蕴川
Q：负反馈为什么能减少非线性失真
A：反馈的信号馈入输入端后再经过放大器放大，由于是负反馈，所以该信号放大时信号本身以及产生的失真相位均与原信号反相，输出时与原信号的放大信号叠加相减输出，所以抵消了一部分失真。

姓名：陈洪堃
问题：为什么negative feedback system 中的馈线是负号？
答：因为负号代表负反馈，只有负反馈的时候这个系统才能稳定。如果是正号，那么系统就是正反馈，一般来说，正反馈会使得信号随着loop逐渐加大，使得系统不稳定

# Lecture 9 Operational Amplifier
姓名：耿加辉
Q1：第一个反馈电路的反馈原理
A：通过R1和R2分压，R2上的电压和输入叠加
Q2:第四个差分放大器反馈电路如何反馈
A：通过R2对Vout分压，加到差分输入的一端，输入电压最后为Vin-Vf
Q3:右边的cascode放大器的增益为什么是左边的两倍
A：差分放大器的两个输出端的相位相反，幅值相同，输出为两边之差

姓名：陈洪堃
第一个问题：ppt 12页左上角图的增益？
答：- gm×Rd

第二个问题：–3dB带宽有什么数学意义？
答：是指信号功率下降到原来的1/2的时候对应的频率，即为-3dB带宽

姓名：佟雅文
问题1：怎样将运放带宽提高十倍
答：通过将gm增大十倍可以提高输出点极点，这需要讲电流增大十倍，即功耗增大十倍
问题2：ppt P12 图2电路增益
答：RD
问题3：ppt P12 图3电路增益
答：gm
问题4：ppt P12 图4电路增益
答：-1
问题5：P14 Voltage addition反馈方式？
答：Vout由Vin-VF决定，通过电阻对Vout分压得到VF，反馈到输入影响输出。

姓名：李嘉毅
问题1：为什么以共源共栅pmos为负载的折叠共源共栅运放x点极点变小？
答：x点总的电容增加，wx=1/RC变得更小。

姓名：陈洪堃
问题：为什么现实中大部分时候都使用两级运放？更多级的运放可能会带来什么问题？
答：因为更多级的运放可能会带来零点漂移，温度漂移的问题。零点漂移可能会让后级中的MOSFET处于截止区的工作状态，导致输出信号失真。

姓名：程子昂
Q1：多级放大器存在哪些设计困难？
A1：开环相位会随着级数增加而增加，为闭环工作的稳定性带来更大的挑战。
Q2：电阻取样共模反馈的电压公式为何是Voutcm = (R1Vout2 + R2Vout1)/(R1 + R2)
A2：可以使用叠加定理进行分析，先认为Vout2为0，只有Vout1作用，得到输出为R2Vout1/(R1 + R2)；同理可得Vout2单独作用时输出为R1Vout2/(R1 + R2)；最后将二者叠加即可。

姓名：李嘉毅
问题1：为什么套筒式共源共栅电路的功耗低？
回答：支路少。
问题2：为什么增益提高运放电路的功耗高？
回答：因为电路中电流源比较多。
问题3：为什么共模反馈电路的开环增益降低？
回答：R1、R2相当于并联在电路中，因此Rout降低，开环增益也降低
# Lecture 10 Stability and Frequency Compensation
姓名：石擎
问题1：为什么N，K两点没有引入极点？
回答：N,K两点会流过大小相等，方向相反的电流，他们会经过各自的Cgd汇合到一起，最终在Vbs那条线上相互抵消，可以看做是交流地（正确答案是在全差分电路中，信号并没有流过N,K两点）
问题2：人为引入的零点为什么要消去第一非主极点？
回答：消去第一非主极点后，原本的第二非主极点将变为第一非主极点，相当于推后了第一非主极点的位置

姓名：李卿熠
问题1：为什么节点N的电容比节点X的电容大？
回答：N节点是处于两个PMOS之间，节点X处于NMOS之间，一般来说在相同的工艺节点下，为了达到相同的导通效果，PMOS宽度比NMOS更大，因此电容会更大。

姓名：杨亚龙
问题1：为什么第二个极点处增益为1的系统的相位裕度为45度？
回答：因为极点对应的位置的相位变化是-45度，而第一个极点带来-90度的相位变化，一起就是-135度的相位变化。
问题2：为什么减少极点数量可以增加相位裕度？
回答：因为极点减少可以减少系统的相移，使PX增加。
问题3：为什么降低主极点位置可以增加相位裕度？
回答：因为主极点位置前移可以使增益更早的下降，使得GX前移。

姓名：黄珏
问题1：为什么等于极点频率处会有45度的相移？
回答：在平面中，在jω轴等于极点频率处，因为极点在横轴上，传输函数的分母会形成一个斜角为45度的向量即会在传输函数中引入-45度的相移。

姓名：陈洪堃
问题一：PPT 15页运算放大器的正反馈和负反馈引脚分别是什么？
答：X和Y
问题二：为什么要叫做带隙基准？带隙指的是什么？
答：带隙指的是硅的能带，PPT19页右边的公式是以硅的带隙为基，和VT有关的变量，故称作带隙基准。

姓名：张蕴川
Q1：为什么二级运放负载电容加大会减少相位裕度，而一级运放负载电容加大会增加相位裕度
A1：可看做有源滤波器，一阶滤波器电容加大只会使衰减点提前而二阶滤波器电容增加会提升q值使幅频曲线在衰减点前隆起尖峰
Q2：为什么bootstraped恒流源要加启动电路设计
A2：若初始上管栅极高电平而下管栅极低电平，则4管全部截止且没有驱使其导通的外力，此时电路可在0电流状态保持稳定

# Lecture 11 Bandgap Reference 

# Lecture 12 Switched Capacitor Circuits
姓名：陈洪堃
问题：为什么M9上的电流是VBE4/R6？
答：因为M11和M9的gate电压是VBE4+VGS11，若M9和M11相同（电流镜的对称性），那么加在R6上的电压为VBE4，而M9和R6串联，则电流相同

姓名：张蕴川
Q：为什么互补开关管采样实际上不可行
A：两管开关无法完全同步，造成两次有时间间隔的阻抗突变，而采样需要精确地一次开关，如果是两次则会无法确定以哪一次为准
Q：为什么电荷补偿管的W是开关管的一半
A：该管需要用整个管（D+S）吸收开关管一半（D或S）的电荷，所以需要开关管一半的电容量，即做成一半尺寸。

李卿熠
Q1：为什么关断mos管后，电容的电压下降了？
answer：因为NOMS再打开状态是，沟道中是电子在导电。关断后，电子迁移到电容正极板，电容正极板的电荷量下降，电压也下降。
Q2：为什么NMOS管作为开关时，传输的电压最大为VDD-Vth？而不是VDD
answer：因为要使NMOS管导通，则Vgs必须大于Vth，当source端电压大于VDD-Vth时，MOS管关断。
# Lecture 14 Oscillators
姓名：李嘉毅
问题1：为什么三级环形振荡器可以发生振荡？
答：三级环形振荡器的直流相移是540度，与频率相关的相移范围是0-270度，因此存在一个频率点使得总相移为720度从而发生振荡。

# Lecture 15 Phase Locked Loop
姓名：宁晨康 
问题1：为什么简单一型PLL是二阶系统？
答：系统有低通滤波器和压控振荡器
问题2：如何提高简单一型PLL相位裕度？
答：增大wlpf
问题3：二阶为什么相位差能到0？
答：因为存在CP结构存在一个电容，能将微小的相位差累积起来 
问题4：cppll增加零点是左平面零点还是右平面零点？为什么？
答1：左平面零点
答2：因为左平面零点提供一个正的S，在相位上是将系统从-180拉到-90

姓名：黄珏
问题1：改变输出频率后相位差会变吗？
答：会，改变输出频率代表vctrl的改变，也就意味着pd的输出dc分量改变，也就是输入的phase error改变
问题2：type-I pll两种增加相位裕度的方法有什么限制？
答：增大lpf极点会导致vctrl纹波增大，最终输出频谱reference spur会变大。减小环路增益会导致反馈强度小，每个周期的相位修正量少最终导致锁定时间变长。

姓名：李嘉毅
问题1：如何提高锁相环稳定性？
答：减小环路增益，即降低|Hopen|的值。

# Lecture 16 DAC