# @ACCESSORY_HELP

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 打印饰品效果描述

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L611-L630)

### 调用关系

**被调用**：

+ `@ACCESSORY_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_select.md)</sup>

**调用**：

+ 不调用其他函数

### 函数实现

#### 参数

+ 无参数

#### 返回值

无返回值

#### 功能实现

**L611-L629**：

调用引擎命令`PRINTL`，输出固定的文字描述

**L630**：

调用引擎命令`WAIT`暂停响应，等待玩家点击或输入