# @ACCESSORY_SELECT

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 作用描述

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L376-L493)

### 调用关系

**被调用**：

+ `@ACCESSORY_SHOP_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop_buy.md)</sup>

**调用**：

+ `@ACCESSORY_EQUIP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_equip.md)</sup>

+ `@ACCESSORY_FIRE`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_fire.md)</sup>

+ `@ACCESSORY_HELP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_fire.md)</sup>

+ `@ACCESSORY_LVUP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_lvup.md)</sup>

+ `@ACCESSORY_PIERISRAPAE`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_pierisrapae.md)</sup>

+ `@ACCESSORY_TRASH`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_trash.md)</sup>

+ `@NUM`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/num.md)</sup>

+ `@PRINT_ACCESSORY`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_accessory.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 当持有的饰品为`0`时返回`0`

#### 功能实现

**L497**：

声明变量`MEMO_LINECOUNT`用于记录引擎到目前为止所显示过的行数。

**L499-L500**：

如果玩家持有的饰品数`NUM("所持アクセサリ")`为`0`，则返回`0`。

**L502**：

用`MEMO_LINECOUNT`记录目前引擎显示过的行数。

**L506-L509**：

打印菜单头部提示语。

**L511-L513**：

循环调用`@PRINT_ACCESSORY, LOCAL`打印所有拥有的饰品。

**L515-L520**：

打印饰品升级、整合、返回上层等菜单项目。

**L525-L523**：

声明跳转标记`$INPUT_LOOP`

使用引擎指令`INPUT`，读取玩家输入

**L525-L528**：

如果玩家输入的是`100`:

  + 调用`@ACCESSORY_SET_TALENT`，更新已装备的饰品参数

  + 返回`0`

**L529-L535**：

如果玩家输入的选择`1 <= RESULT <= 8`，且`FLAG:3X0`不为`0`：

  + 当`FLAG:399`与`RESULT`相等时，说明玩家选择了正在装备的饰品

  + 调用`@ACCESSORY_EQUIP, "外す"`将该饰品卸下

否则（玩家选择的是当前未装备的饰品）

  + 将`FLAG:399`置为`RESULT`，装备该饰品

  + 调用`@ACCESSORY_EQUIP`更新已装备的饰品参数

**L536-L537**：

如果玩家输入的是`80`，且`ITEM:砥砺思维之石`的数量大于`0`：

  + 调用`@ACCESSORY_LVUP`进行饰品升级

**L538-L539**：

如果玩家输入的是`81`，且`ITEM:灼烧思考之炎`的数量大于`0`：

  + 调用`@ACCESSORY_FIRE`进行饰品净化

**L540-L541**：

如果玩家输入的是`82`，且`ITEM:纹白蝶`的数量大于`0`，且`NUM("所持アクセサリ")`持有的饰品数量大于或等于`2`：

  + 调用`@ACCESSORY_PIERISRAPAE`进行饰品整合

**L542-L543**：

如果玩家输入的是`98`：

  + 调用`@ACCESSORY_TRASH`丢弃饰品

**L544-L545**：

如果玩家输入的是`99`：

  + 调用`@ACCESSORY_HELP`打印饰品效果一览表

**L546-L547**：

如果玩家输入不合法：

  + 则跳转到声明标记`$INPUT_LOOP`重新读取玩家的输入

**L551**：

调用引擎命令`RESTART`，重新从头执行本函数
