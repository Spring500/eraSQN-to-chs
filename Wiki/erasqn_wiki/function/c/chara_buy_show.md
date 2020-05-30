# @CHARA_BUY_SHOW

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 显示梦魔召唤的主菜单

### 所在文件

+ [Shop2.erb](/ERB/SHOP/Shop2.erb#L96-L116)

### 调用关系

**被调用**：

+ `@CHARA_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/chara_buy.md)</sup>

**调用**：

+ `@MONEY_C`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

+ `@PRINT_STR`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

+ `@SET_CHARA_BUY_SHOW`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

+ `@TEXTS`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

### 函数实现

#### 参数

+ ARGS

#### 返回值

+ 无返回值

#### 功能实现

**L124-L127**：

声明变量`LCOUNT`、`LCOUNT2`、`NEXT_LINE`和`SPACES`

**L132**：

将`ITEMSALES:0`置为`0`
（原版日文注释是为了解决某个bug，但是看不懂这段注释）

**L134**：

将换行标志变量`NEXT_LINE`置为`0`

**L136-L173**：

以`LCOUNT`作为迭代数，循环`79`次：（80号以上的角色不显示）

  + 当`FLAG:(1000 + LCOUNT)`大于`0`，且`CONFIG("ユニークキャラの多重召喚")`特殊角色不可重复召唤时：

    + 直接跳过这次循环，并进入下次循环

  + 当`ITEMPRICE:(100 + LCOUNT)`角色售价为`0`时：

    + 直接跳过这次循环，并进入下次循环

  + 将`ITEMSALES:(100 + LCOUNT)`置为`1`，标记角色可出售

  + 如果`ARGS`为`ＥＮＤチェック`时：

    + 以`LCOUNT2`为迭代数，循环`9`次：

      + 将`RESULT`置为`0`

      + 尝试调用`@IS_SINGLE_ENDING_K{LCOUNT}_{LCOUNT2}`

      + 当`RESULT`不为`0`时：

        + 将输出颜色设为`粉红色`

  + *L155-L164*是我为了解决汉化造成的显示角色列表无法对齐的情况而增加的一些代码，其作用时根据不同的角色号码，在显示该角色前显示一定数量的空格，以此来让角色列表显示保持对齐

  + 打印出编号为`ITEMNAME:(100 + LCOUNT)`的角色名称和角色售价

  + 调用引擎命令`RESETCOLOR`将显示颜色重置为默认值

  + `NEXT_LINE`自增`1`

  + 当`NEXT_LINE`对`2`取模的结果为`0`时：<br/>（已经在本行输出了2个角色）

    + 输出一个换行符

**L174-L175**：

当输出完成后，如果`NEXT_LINE`对`2`取模的结果不为`0`：

  + 输出一个换行符
