# @CONFIG

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 查询参数所在的FLAG，并返回参数的bit

### 所在文件

+ [Configure.erb](/ERB/Configure.erb#L142-L565)

### 调用关系

**被调用**：

+ `@DAYEV`<sup>[说明文件](/Wiki/erasqn_wiki/function/d/dayev.md)</sup>

**调用**：

+ `@COND`<sup>[说明文件](/Wiki/erasqn_wiki/function/d/dayev.md)</sup>

+ `GETBIT`<sup>[文档](https://osdn.net/projects/emuera/wiki/excom#h5-GETBIT.20.3C.E6.95.B0.E5.BC.8F.3E.2C.20.3C.E6.95.B0.E5.BC.8F.3E)</sup>

### 函数实现

#### 参数

+ ARGS

#### 返回值

返回ARGS对应FLAG的bit

#### 功能实现

使用`SELECTCASE`语法，以传入的`ARGS`作为选项，返回对应FLAG的bit，以此实现查询某个选项的状态
