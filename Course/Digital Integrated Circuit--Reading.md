title: [[Digital Integrated Circuit--Reading]]
date: 2023-09-26 14:19
mdate: 2023-10-12 10:09:13

」= NRE(fixed)costs - design effort
Design costs, Influenced by the design complexity and designer productivity 
    - Design/verification time and effort
    - Mask Generation
    - Fabrication equipment
 - Recurring costs - proportional to product volume
     - silicon processing(also proportional to chip area)
     - packaging
     - final test
  - cost per IC = RE costs per IC + $\frac{NRE costs}{number}$
# Why FInFET and What Next?
MOSFET Scaling Limits
- Gate Oxide Thickness
- Junction Depth
- Dopant Density Fluctuation
**Old rule: Lg Scales with Tox?**
New rule : Lg Scales with Body Thickness




# 引论
- 集成电路的成本
    - 集成电路的成本 = 每个电路可变成本 + $\frac{固定成本}{产量}$
    - 可变成本 = $\frac{芯片成本+测试成本+封装成本}{最终成品率}$
    - 芯片成本 = $\frac{圆片成本}{芯片数 x 芯片成品率}$ = $f(芯片面积)^4$
- 集成电路的功能性与稳定性
    - 电压传输特性
    - 噪声容限
        - $NM_L = V_{IL}-V_{OL}$
        - $NM_H = V_{OH}-V_{OL}$
    - 再生性
        - 受到干扰后经过后续电路能够收敛回额定电平中的一个
    - 抗噪声能力
    - 方向性
        - 一个门的输出电平变化不应出现在该电路的输入上
    - 驱动能力
        - 扇入表示连接到驱动门输出端的负载门数目
        - 扇出表示该门输入数目
- 功耗、能耗
    - 动态功耗
     发生在门开关期间，由于对电容充电和电源短暂接地产生，正比于开关频率。
    - 静态功耗
     发生在任何时候，由于电源和地之间静态导电通路产生或者漏电流。
 [100]
- 制造工艺
    - 设计步骤
        - 硅掺杂
        - 光刻
        - 氧化层
        - 光刻胶
        - 曝光
        - 光刻胶显影和烘干
        - 酸刻蚀
        - 旋转、清洗、干燥
        - 重复步骤
            - 扩散注入、离子注入
            - 淀积
            - 刻蚀
            - 平坦化
        - 去除光刻胶
- 设计规则
    - 最小线宽
    - 工艺层
        - 层内限制规则
        - 层间限制规则
- 集成电路封装
    - Rent 定律
        $P = K \times G^{\beta}$
    - 封装要求
        - 低成本
        - 电气要求
            低电容、低电阻、低电感
        - 机械特性和热特性
            高散热率；芯片、封装、电路板之间连接牢固
[100]










