# @ACCESSORY_IDENTIFY

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 作用描述

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L139-L216)

### 调用关系

**被调用**：

+ `@ACCESSORY_SHOP_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop_buy.md)</sup>

**调用**：

+ `@ACCESSORY_ABL`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_abl.md)</sup>

+ `PRINT_ACCESSORY`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_accessory.md)</sup>

### 函数实现

#### 参数

+ ARG

+ ARGS

#### 返回值

无返回值

#### 功能实现

**L126**：

声明变量`LCOUNT`。

**L142-L147**：

（作用不明，过后研究）

（注释说的是判定要做什么）

（经过旧存档测试似乎第一次`LOCAL`必定为`7`，之后无论怎么循环都为`8`）

（经过新存档测试可以从`1`开始遍历，但超过`8`次后，`LOCAL`就会恒为`8`）

（此标志会被保存，所以……鉴定了`8`次之后一只都会是`8`）

用循环+判断造出`FLAG:310～390（仅整十）`中第一个为`0`的标志。

然后用`LOCAL`记录此标志，并立即跳出循环。

**L151-L163**：

当调用函数传入的`ARGS`为`鑑定`时，以引擎内置的随机数生成器生成`0～9`的随机数作为选择支，

+ 当随机数为`0～5`时，什么都不做

+ 当随机数为`6`时，另`FLAG:(300 + LOCAL*10 + 9) += 1`

+ 当随机数为`7`时，另`FLAG:(300 + LOCAL*10 + 9) += 2`

+ 当随机数为`8`时，另`FLAG:(300 + LOCAL*10 + 9) += 3 + RAND:4`

+ 当随机数为`9`时，另`FLAG:(300 + LOCAL*10 + 9) += 4 + RAND:6`

