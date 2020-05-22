# @ACCESSORY_LVUP

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 饰品升级

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L275-L320)

### 调用关系

**被调用**：

+ `@ACCESSORY_SHOP_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop_buy.md)</sup>

**调用**：

+ `@ACCESSORY_EQUIP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_equip.md)</sup>

+ `@PRINT_ACCESSORY`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_accessory.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

当`ITEM:砥砺思维之石`数量小于等于`0`时，返回`0`

#### 功能实现

**L276**：

声明变量`MEMO_LINECOUNT`，用于记录到目前为止引擎显示过的行数。

**L277**：

记录引擎到目前为止显示过的行数。

**L282-L283**：

打印饰品升级的相关说明，以及`ITEM:砥砺思维之石`的数量。

**L286-L288**：

以`LOCAL`为迭代数，循环`8`次：

  + 调用`@PRINT_ACCESSORY, LOCAL`，以打印出所有拥有的饰品。

**L291-L297**：

如果`ITEM:砥砺思维之石`数量小于等于`0`

  + 提示`砥砺思维之石已经没有了`

  + 调用`@ACCESSORY_EQUIP`，更新已装备的饰品的参数<br/>（因为已装备的饰品的参数是直接从槽位复制过来的，而如果该槽位的饰品升级了，却又没有重新将相应的参数复制到`FLAG:300～309`，就会导致bug）

  + 返回`0`

**L301-L302**：

声明跳转标记`$INPUT_LOOP`。

使用引擎指令`INPUT`，读取玩家输入。

**L304-L307**：

如果玩家输入的是`100`：

  + 调用`@ACCESSORY_EQUIP`更新已装备的饰品参数

  + 返回`0`

**L308-L314**：

如果玩家的输入`1 <= RESULT <= 8`，且`FLAG:(300 + RESULT*10)`该饰品的第1个FLAG槽不为`0`：

  + 如果该饰品槽的第9个FLAG不大于`28`（饰品等级未达最大）

    + `ITEM:砥砺思维之石`的个数扣减`1`

    + `FLAG:(300 + RESULT*10 + 9)`物品的等级FLAG增加`1`

  + 否则，输出提示`等级已达最大`

**L315-L316**：

如果玩家的输入不合法：

  + 则跳转到声明标记`$INPUT_LOOP`重新读取玩家的输入

**L319-L320**：

调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行以显示的内容。

调用引擎命令`RESTART`，重新从头执行本函数。
