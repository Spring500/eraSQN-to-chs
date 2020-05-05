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

L4114：调用引擎内部函数`GETTIME`，此函数会将当前系统时间储存到`RESULT:0`，假如现在是2009年3月28日13時5分23秒678微妙，那么`RESULT:0`就等于`20090328130523678`

L4116-L4130：花式计算时间


