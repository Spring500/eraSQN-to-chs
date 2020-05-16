# @SAVE_CONFIGURE

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 保存游戏的全局设定

### 所在文件

+ [Global.erb](/ERB/Global.erb#L1-L141)

### 调用关系

**被调用**：

+ `@funcname1`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

**调用**：

+ `@INPUT_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/i/input_select.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 当玩家选择不保存全局设定时返回`0`

#### 功能实现

**L2-L5**：

定义变量`LCOUNT`。

调用引擎命令`LOADGLOBAL`加载全局设定。

**L8-L16**：

当`GLOBAL:100`不为`0`时，<br/>（eraSQN的版本号(FLAG:29)，这里不是很懂为什么要用版本号，应该是和不同版本的存档兼容性有关）

  + 打印出是否覆盖当前已存在的全局设定的选项让玩家选择

  + 当玩家选择`不保存`时，返回`0`，终止函数

  + 当玩家选择`保存`时，继续执行函数剩余的部分

**L18**：

将`FLAG:98`（控制显示选项的FLAG）赋值给`GLOBAL:98`。

**L21-26**：

使用引擎命令`GETTIME`，获取当前系统时间并自动存到`RESULT`里。

然后将时间通过计算转换成`YYMMDD`的形式。

然后将转换后的时间赋值给`GLOBAL:98`，将游戏版本号`FLAG:29`赋值给`GLOBAL:100`。

**L29-136**：

将一系列设定`FLAG`赋值给`GLOBAL`。

**L139**：

调用引擎命令`SAVEGLOBAL`保存`GLOBAL`。

**L141**：

打印保存完成的提示。
