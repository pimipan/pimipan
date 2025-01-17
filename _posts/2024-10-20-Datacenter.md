---
layout: post
title: 数据中心建设经验
comments: true
author: Pimi
---
## 分类
相比国标中的文字描述，美标中N+X的描述方式更加精准，适合书面沟通。

| **特点**   | **T1**         | **T2**       | **T3**      | **T4**         | **A级**         | **B级**        | **C级**        |
| -------- | -------------- | ------------ | ----------- | -------------- | -------------- | ------------- | ------------- |
| **冗余能力** | 无冗余（N+0）       | 部分冗余（N+1）    | 全冗余（N+1）    | 双重冗余（N+N）      | 完全冗余，容错型       | 部分冗余，冗余型      | 无冗余，基本型       |
| **宕机时间** | 年均28-29小时      | 年均22小时       | 年均1.6小时     | 年均0.5小时        | 电子信息系统运行中断不可接受 | 允许一定的系统中断     | 允许系统中断        |
| **维护能力** | 计划性和非计划性中断均可接受 | 计划性中断可减少     | 计划性中断不影响服务  | 计划性和非计划性中断均可避免 | 运行期间不应中断       | 在冗余能力范围内不应中断  | 允许在正常运行情况下中断  |
| **电源配置** | 单回路供电          | 单回路供电，部分备用   | 双回路供电       | 双回路供电，容错系统     | 双重电源供电         | 单回路供电，部分备用    | 单回路供电         |
| **适用场景** | 成本低，适合小型应用     | 中小型企业，适合一般应用 | 大型企业，适合关键应用 | 大型企业，适合高可用性需求  | 关键任务应用，容错要求高   | 一般任务应用，冗余要求中等 | 非关键任务应用，冗余要求低 |

## 性能
![](https://img.soujianzhu.cn/pic/20181116180049_6471271301.jpg "性能要求")

## 配电系统
**UPS系统包括：** UPS、电池、精密配电柜（列头柜）、工业连接器、PDU、STS静态转化开关（重要的单电源设备）；
**动力系统包括：** ATS双电源转换开关等；

## 空调系统
**动力**：空调主机（冷机/热泵、水泵、板换）、冷却塔；
**新风系统**有过滤、降温、去湿的功能，保证机房的正压和洁净度。（新风机、防火阀）；
**排风系统**用于气体灭火后的排风，人工启动。集中设置排风机的系统，支管处设置电动密闭阀；
**末端设备**有精密空调、加湿器等；
**给排水**管道应采取防渗漏和防结露的措施；
在房间内温度不超限的情况下，空调系统允许中断。

## 气流组织

### 上松风的优点 
1. 上走线方式，机房内没设活动地板，空调机组所需加湿给水管、凝结水排管均为明布置，一旦有漏水现象，能快速发现，及时排除，消除引起机房不安全的因素。

2. 机房内没有活动地板，不易积灰，即使房间有灰尘，清理打扫很方便，从而使空调机组的过滤网使用时间长，减少维护管理的工作量。

3. 机房设备若是分期分批、逐步安装的，空调设备也是与设备同步分批安装，上走线的机房有利于空调设备加湿给水管、凝结水排水管的扩容建设。

### 上送风方式的缺点：
1. 上送风的空调送风方式是由机房的上部送到设备，与热空气交换后，从机房的下部回到空调机组内。机房的送风气流组织与空气流动特性相矛盾，从而使得房间最下部温度偏高，不利于设备的运行。
2. 根据机房的大小，空调机组送风距离的长短，空调上送风具体形式有所不同。需要送风距离较短时，可以用消音送风帽的风口直接送到机房内，机房内的气流组织为上侧送风下侧回风方式。需要送风距离较长时，就需要在机房上部设送风管道，通过空调送风管、送风口把空气送到机房的所需部位，这样，送风管和送风口就需要与设备的各类走线架、照明灯具进行协调，以免相互打架矛盾，给设计、施工带来一定的工作量。
3. 由于上送风方式是直接将风吹到机房内或是用送风管和送风口送到机房，所需送风机的机外余压相对下送风要高，再加上送风没有了活动地板，送风本身的风声也比下送风要高，因此，同样规格的空调机组，上送风型比下送风型噪声要高些。
4. 对于进深较大的通信机房，为了空调送风均匀，需要增加送风管，机房上部因通信走线桥架、空调风管、照明灯具等的布置，显得比较杂乱，没有下送风方式机房整齐美观。

### 下送风方式的优点：
1. 下送风方式是将低温空气直接从底部送到设备内，吸收设备的热量后，从机房顶部回到空调机组顶部。空调风流动方向与空气特性相一致，容易得到好的空调效果。
2. 地板下的空间比风管断面的面积要大许多，这就形成了静压箱，因此下送风方式送风均匀，整个机房区域的温差小。
3. 因为送风是在活动地板内，从而使下风的距离与上送风方式在同等条件下，所需的送风风压低，空调设备和送风噪声相对会低一些。
4. 单从空调专业的角度出发，下送风方式不需送风风管和送风口，对于设计施工来说，相对简单方便，空调设备的摆放就可以灵活的进行调整。由于下送风将通信各类管线，空调专业的管线均隐藏在活动地板内，从而使得机房内显得整齐美观。仅从空调专业投资来说，相对上送风而言投资会低一点。

### 下送风方式的缺点：
1. 因为活动地板主要是给设备布置各类通信管线用的，前期建设的空间不足加上后期新增管线，会减少空调风道面积，从而降低空调效果。
2. 尽管机房密封性较好，活动地板下仍然容易积灰，而且清理很难。如果管理不善，会造成一些部位有灰尘集聚，空调下送风会使灰尘随风进入设备，增加设备故障。
3. 下送风空调方式的加湿给水管、凝结水排水管都布置在活动地板内，出现问题时不易发现，易造成安全隐患。

## PUE
Uptime Institute是Tire等级标准的制定机构，根据它在[网站](https://journal.uptimeinstitute.com/large-data-centers-are-mostly-more-efficient-analysis-confirms/"")公布，装机量越大的数据机房PUE越接近1，呈下图：
![](https://github.com/pimipan/pimipan.github.io/blob/master/assets/img/20241020-2.png?raw=true)
