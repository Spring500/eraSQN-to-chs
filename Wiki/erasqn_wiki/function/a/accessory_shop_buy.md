# @ACCESSORY_SHOP_BUY

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 饰品店主菜店

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L17-L118)

### 调用关系

**被调用**：

+ `@ACCESSORY_SHOP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop.md)</sup>

**调用**：

+ `@ACCESSORY_FIRE`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_fire.md)</sup>

+ `@ACCESSORY_IDENTIFY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_identify.md)</sup>

+ `@ACCESSORY_LVUP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_lvup.md)</sup>

+ `@ACCESSORY_ORDERMADE_MENU`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_ordermade_menu.md)</sup>

+ `@ACCESSORY_PIERISRAPAE`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_pierisrapae.md)</sup>

+ `@ACCESSORY_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_select.md)</sup>

+ `@ACCESSORY_SET_TALENT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_set_talent.md)</sup>

+ `@MONEY_C`<sup>[说明文件](/Wiki/erasqn_wiki/function/m/money_c.md)</sup>

+ `@NUM`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/num.md)</sup>

+ `@SHOW_BUY_ITEM`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/show_buy_item.md)</sup>

+ `@TEXT_LJ`<sup>[说明文件](/Wiki/erasqn_wiki/function/t/text_lj.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 当玩家选择从饰品店出来时，返回`0`。

#### 功能实现

**L19-L38**：

打印出饰品商店主的菜单，如玩家持有的未鉴定饰品列表及个数、定制饰品、使用`思维之石`以及纹白蝶或更换饰品。

**L40-L41**：

声明跳转标记`$INPUT_LOOP`。

调用引擎指令`INPUT`读取玩家的选择。

**L44-L47**：

当玩家在饰品店主菜单选择`100`时：

  + 调用`@ACCESSORY_SET_TALENT`

  + 打印离店提示

  + 返回`0`

**L49-L69**：

当玩家在饰品店主菜单选择`0 <= RESULT <= 4`时：<br/>（即选中手镯、袖饰、手套、绶带、指环时）

> `@ACCESSORY_BUY()`会在`FLAG:380 == 0`时返回`1`，其余情况均返回`0`。

> 经测试，如果保留此判定条件，会导致在游戏开始或加载后，鉴定完任意一个物品后，无法再鉴定其他物品。

> 暂时未发现`FLAG:380`在代码其他部分会被修改，但通过调试，可以发现此FLAG会改变，但无法通过这些改变来找到规律。

> 需要更多代码来推测意图。

  + 当`ITEM:(320+RESULT)`不为`0`（玩家持有此未鉴定物品）时：

    + 将`LOCAL`置为`100`（鉴定物品的价钱）

  + 否则（玩家未持有此物品时）：

    + 将`LOCAL`置为`ITEMPRICE:(320+RESULT)`（购买物品的价钱）

  + 当玩家的所持金钱小于`LOCAL`时：

    + 输出提示`金钱不足`

  + 否则：

    + 用所持金钱扣减`LOCAL`

    + 如果玩家持有该物品（做鉴定，判定条件参考上面）时：

    	+ `ITEM:(320+RESULT)`扣减`1`

    	+ 调用`@ACCESSORY_IDENTIFY, RESULT*10, "鑑定"`

    + 否则（玩家未持有该物品，购买并立即鉴定）：

    	+ 调用`@ACCESSORY_IDENTIFY, RESULT*10, "鑑定"`

**L74-L84**：

> 此处也包含`@ACCESSORY_BUY()` 返回值判定，说明参考**L49-L69**小节的说明。

当玩家在饰品店主菜单选择`5`时：<br/>（即选中朦胧宝石时）

  + 当玩家的所持金小于`100`时：

    + 打印提示`金钱不足`

  + 否则：

    + 用所持金钱扣减`100`

    + 用朦胧宝石的持有数量`ITEM:325`扣减`1`

    + 调用`@ACCESSORY_IDENTIFY, RESULT*10, "鑑定"`

**L88-L93**：

> 此处也包含`@ACCESSORY_BUY()` 返回值判定，说明参考**L49-L69**小节的说明。

当玩家在饰品店主菜单选择`10`时：<br/>（即选中定制饰品时）

  + 调用`@ACCESSORY_ORDERMADE_MENU`

**L94-L105**：

当玩家在饰品店主菜单选择`20`，且`NUM("所持アクセサリ")`（FLAG:310～390的物品，如果不为`0`，则返回值`+1`）

  + 当玩家的所持金钱`MONEY`小于`ITEMPRICE:砥砺思维之石`砥砺思维之石的价格时：

    + 打印`金钱不足`

  + 否则

    + 打印`要买多少个呢？`

    + 调用`@SHOW_BUY_ITEM, 96`

    + 如果该函数返回`0`

      + 打印`什么嘛，什么都不买吗？`

    + 否则

      + 打印`谢谢惠顾，购买了多少什么什么`

**L106-L107**：

当玩家在饰品店主菜单选择`80`，且`ITEM:砥砺思维之石`持有数大于`0`，且`NUM("所持アクセサリ")`返回值大于`0`

  + 调用`@ACCESSORY_LVUP`

**L108-L109**：

当玩家在饰品店主菜单选择`81`，且`ITEM:砥砺思维之石`持有数大于`0`，且`NUM("所持アクセサリ")`返回值大于`0`

  + 调用`@ACCESSORY_FIRE`

**L110-L111**：

当玩家在饰品店主菜单选择`82`，且`ITEM:纹白蝶`持有数大于`0`，且`NUM("所持アクセサリ")`返回值大于等于`2`

  + 调用`@ACCESSORY_PIERISRAPAE`

**L112-L113**：

当玩家在饰品店主菜单选择`90`，且`NUM("所持アクセサリ")`返回值大于`0`

  + 调用`@ACCESSORY_SELECT`

**L114-L115**：

当玩家在饰品店主菜单的选择不合法时，

  + 声明跳转标记`$INPUT_LOOP`。

**L118**：

调用引擎命令`RESTART`，重新从头执行本函数。
