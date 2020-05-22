# @ACCESSORY_FIRE

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 消去饰品特殊效果

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L322-L373)

### 调用关系

**被调用**：

+ `@ACCESSORY_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_select.md)</sup>

+ `@ACCESSORY_SHOP_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop_buy.md)</sup>

**调用**：

+ `@ACCESSORY_EQUIP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_equip.md)</sup>

+ `@DEF_COLOR`<sup>[说明文件](/Wiki/erasqn_wiki/function/d/def_color.md)</sup>

+ `@PRINT_ACCESSORY`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_accessory.md)</sup>

+ `@PRINT_COLORTEXT`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_colortext.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 当`ITEM:灼烧思考之炎`小于或等于`0`时，结束函数并返回`0`

#### 功能实现

**L323-L324**：

声明变量`MEMO_LINECOUNT`用于记录引擎到目前为止所显示过的行数。

**L328-L332**：

显示功能简述和`ITEM:灼烧思考之炎`的个数。

**L335-L337**：

以`LOCAL`为迭代数，循环`8`次：

  + 调用`@PRINT_ACCESSORY, LOCAL`，以打印出所有拥有的饰品

**L340-L346**：

如果`ITEM:灼烧思考之炎`数量小于等于`0`时

  + 提示`灼烧思考之炎已经用完了`

  + 调用`@ACCESSORY_EQUIP`，更新之装备的饰品参数<br/>（原因参见[@ACCESSORY_LVUP说明文档](/Wiki/erasqn_wiki/function/a/accessory_lvup.md#L55-L63)）

  + 返回`0`

**L350-L351**：

声明跳转标记`$INPUT_LOOP`

使用引擎指令`INPUT`，读取玩家输入。

**L353-L356**：

如果玩家输入的是`100`：

  + 调用`@ACCESSORY_EQUIP`更新已装备的饰品参数

  + 返回`0`

**L357-L367**：

如果玩家的输入`1 <= RESELT <= 8`，且`FLAG:(300 + RESULT*10`该饰品的第1个FLAG槽不为`0`：

  + 如果该饰品的`FLAG:(300 + RESULT*10 + 1)`第1个效果槽位不为`0`（该饰品至少有1个效果）：

    + `ITEM:灼烧思考之炎`的个数扣减`1`

    + 将此饰品的第1个能力槽位置为`0`，去除该效果

    + 以`LOCAL`为迭代数，循环`4`次：

      + 将饰品的第`LOCAL`个效果槽位与第`LOCAL + 1`个效果槽位交换（将剩余的饰品效果槽向前移动1个位置）

  + 否则（该饰品没有任何效果）

    + 提示`该饰品已经没有效果`

 **L368-L369**：

 如果玩家的输入不合法：

   + 跳转到声明标记`$INPUT_LOOP`重新读取玩家的输入

**L372-L373**：

调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容。

调用引擎命令`RESATRT`，重新从头执行本函数。
