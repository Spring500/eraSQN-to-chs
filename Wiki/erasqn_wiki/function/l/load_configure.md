# @LOAD_CONFIGURE

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 作用描述

### 所在文件

+ [Global.erb](/ERB/Global.erb#L144-L291)

### 调用关系

**被调用**：

+ `@funcname0`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

+ `@funcname1`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

**调用**：

+ `@funcname2`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

+ `funcname3`<sup>[文档](https://osdn.net/projects/emuera/wiki/FrontPage)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 当从全局设定中读取到的版本号比目前游戏的版本号时为异常情况，返回`0`

#### 功能实现

**L145**：

定义变量`LCOUNT`。

**L148**：

调用引擎命令`LOADGLOBAL`加载GLOBAL变量。

**L151-L155**：

当读取到的`GLOBAL:100`读取到的游戏版本号比`FLAG:29`当前游戏版本号大时：

  + 打印出加载失败版本不符的消息。

  + 返回`0`。

**L157-159**：

将`FLAG:98`置为`0`。

从`GLOBAL:98`读取画面显示设定`FLAG:98`。

**L162-L172**：

读取射精场所变更的设定，如果被读取的资料中存在着关于魔法瓶的部分，而当前存档没有持有魔法瓶时，提示`因为没有魔法瓶，所以部分设定无法生效`。

**L175-L189**：

从GLOBAL中读取关于触手、穿着、鞋子、怀孕补丁的设定，并存到对应的FLAG中。

**L192-L199**：

从GLOBAL读取与相思相爱相关的设定，当目前正在游玩的存档，誓约指环数大于`2`时，提示`因为誓约指环数量太多，所以部分设定将无法生效`。

**L210-L286**：

继续读取剩余的设定。

**L291**：

打印提示`已读取全局设定`。
