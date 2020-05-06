# @DAYEV

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/function/README.md)

### 作用描述

+ 日期判断

### 所在文件

+ [Function_Sq.erb](/ERB/TRAIN/Function_Sq.erb#L4100-L4335)

### 调用关系

**被调用**：

+ `@SHOW_SHOP`<sup>[说明文件](/Wiki/function/s/show_shop.md)</sup>

**调用**：

+ `@CONFIG`<sup>[说明文件](/Wiki/function/c/config.md)</sup>

### 函数实现

#### 参数

+ ARGS

+ ARGS:1

#### 返回值

返回值描述

#### 功能实现

L4103-L4122：定义一些存放现实日期的局部变量，如：RYEAR、MONTH_DAY、RDAY、RTIME、WEEKDAY

L4114：调用引擎内部函数`GETTIME`，此函数会将当前系统时间储存到`RESULT:0`，假如现在是2009年3月28日13時5分23秒678微妙，那么`RESULT:0`就等于`2009 03 28 13 05 23 678`（不包含空格）

L4116：`RYEAR = (RESULT / 100 00 00 00 00 000) % 10000` = 2009

L4118：`MONTH_DAY = (RESULT / 10000000) % 1000000` = 3 28 13

L4120：`RDAY = (RESULT / 1000000000) % 100` = 28

L4122：`RTIME = MONTH_DAY%100` = 13

L4124-L4129：

0=日， 1=一， 二=2， 3=三， 4=四， 5=五， 6=六

利用现实世界计算星期？然后放到游戏里用，但似乎跟例子中的日子对不上，20090328应该是星期六，但算出来的结果为0，即周日。不过既然是游戏就不必太认真233。

一二月用以下的公式：

`WEEKDAY = (RYEAR - 1 + (RYEAR - 1)/4 - (RYEAR - 1)/100 + (RYEAR - 1)/400 + (13*(MONTH_DAY/10000 + 12) + 8)/5 + RDAY)%7`

其余月份用一下公式：

`WEEKDAY = (RYEAR + RYEAR/4 - RYEAR/100 + RYEAR/400 + (13*MONTH_DAY/10000 + 8)/5 + RDAY)%7`
