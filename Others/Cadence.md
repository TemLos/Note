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