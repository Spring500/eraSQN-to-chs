# @ACCESSORY_ORDERMADE_MENU


> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 饰品定制菜单

### 所在文件

+ [Accessory_Ordermade.erb](/ERB/SHOP/Accessory_Ordermade.erb#L1-L120)

### 调用关系

**被调用**：

+ `@ACCESSORY_SHOP_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop_buy.md)</sup>

**调用**：

+ `@DEF_COLOR`<sup>[说明文件](/Wiki/erasqn_wiki/function/d/def_color.md)</sup>

+ `@INPUT_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/i/input_select.md)</sup>

+ `@MONEY_C`<sup>[说明文件](/Wiki/erasqn_wiki/function/m/money_c.md)</sup>

+ `@PRINT_ACCESSORY`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_accessory.md)</sup>

+ `@PRINT_COLORTEXT`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_colortext.md)</sup>

+ `@SET_ACCESSORY_ABILITY`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_accessory_ability.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 当玩家选择`返回`时，返回`0`

#### 功能实现

**L4-L6**：

声明变量`LCOUNT`、`NUM_ACCE`和`MEMO_PRICE`

**L9-L14**：

以`LCOUNT`为迭代数，FOR循环`8`次：<br/>（找出空着的第1个饰品槽）

  + 如果`FLAG:(300 + LCOUNT * 10)`为`0`

    + 将`LCOUNT`赋值给`NUM_ACCE`

    + 立即结束循环

**L16-L26**：

打印定制饰品的头部提示及功能菜单

**L28**：

调用`@INPUT_SELECT, 5, 100`处理玩家的选择

**L300**：

如果玩家选择的是`100`：

  + 返回`0`

**L33**：

将`RESULT * 10`赋值给`FLAG:(300 + NUM_ACCE * 10)`

**L35-L36**：

打印定制时的素材选择提示

**L38-L54**：

以`FLAG:(300 + NUM_ACCE * 10)`作为选择支：

  + 如果结果为`0`，则显示手镯的名称前缀，并调用`@INPUT_SELECT, 4`让玩家选择饰品稀有度

  + 如果结果为`10`，则显示袖饰的名称前缀，并调用`@INPUT_SELECT, 4`让玩家选择饰品稀有度

  + 如果结果为`20`，则显示手套的名称前缀，并调用`@INPUT_SELECT, 3`让玩家选择饰品稀有度

  + 如果结果为`30`，则显示绶带的名称前缀，并调用`@INPUT_SELECT, 3`让玩家选择饰品稀有度

  + 如果结果为`40`，则显示指环的名称前缀，并调用`@INPUT_SELECT, 2`让玩家选择饰品稀有度

**L55**：

在`FLAG:(300 + NUM_ACCE * 10)`，加上`RESULT + 1`，拼接出饰品完整的名字

**L57-L68**：

打印出附加效果数量与收费的关系的相关提示

**L70**：

声明跳转标记`$MAKE_ACCE`

**L72**：

调用`@SET_ACCESSORY_ABILITY, NUM_ACCE`让玩家定制饰品的特殊效果

**L74-L76**：

打印定制特殊效果时的提示

调用`@PRINT_ACCESSORY, NUM_ACCE`打印出当前饰品的定制效果

**L78-L83**：

调用引擎命令将`LOCAL`置为`0`

以`LCOUNT`作为迭代数，FOR循环`5`次：<br/>（统计饰品附加的效果数量）

  + 如果`FLAG:(300 + NUM_ACCE * 10 + LCOUNT)`饰品的当前效果槽位值为`0`，立即跳出循环

  + `LOCAL`自增`1`

**L86-L93**：

以`LOCAL`作为选择支：

  + 当其为`0`时，将定制收费`MEMO_PRICE`置为`0`

  + 当其为`1`时，将定制收费`MEMO_PRICE`置为`5000`

  + 其他情况，将定制收费`MEMO_PRICE`置为`LOCAL * 10000`

**L100-102**：

打印出收费的相关提示和确认购买的选项

**L104-L105**：

声明跳转标记`$ORDER_BUY_ANS`

调用引擎命令`INPUT`，读取玩家选择

**L107-L120**：

当玩家选择`100`时：<br/>（不确认购买，直接退出）

  + 调用引擎命令`VARSET`，将定制饰品的槽位`FLAG:3X0～3X0 + 10`置为`0`，并打印`冷场`


当玩家选择`0`，且时持有的金钱`MONEY`小于`MEMO_PRICE`时：<br/>（确认购买，但钱不够时)

  + 打印`钱不够`的提示

  + 跳转到声明标记`$ORDER_BUY_ANS`重新读取玩家的输入

当玩家选择`0`时<br/>（确认购买，且钱足够）：

  + 打印`谢谢惠顾`

  + 所持金钱`MONEY`扣减`MEMO_PRICE`

当玩家选择`1`时：

  + 跳转到声明标记`$MAKE_ACCE`重新让玩家定制饰品

如果玩家的输入不合法：

  + 跳转到声明标记`$ORDER_BUY_ANS`重新读取玩家的输入
  