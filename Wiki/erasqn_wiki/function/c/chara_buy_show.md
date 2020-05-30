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

**L98**：

显示游戏内日期

**L98-L103**：

如果`TIME`为`0`：

  + 打印`昼`

否则：

  + 打印`夜`

**L104-L105**：

如果当前选定了调教目标`TARGET`，就打印`XXX调教中`

**L106-L107**：

如果当前设定了助手则打印`助手：XXX`

**L108**：

打印玩家说持有的金钱数量`MONEY`

**L109**：

调用`@PRINT_STR`，打印被两个粉红色心桃字符包围的特殊END提示

**L112**：

调用`@SET_CHARA_BUY_SHOW, "ＥＮＤチェック"`显示可以召唤的角色列表

**L115-L116**：

打印`放弃召唤`的菜单项目

打印让玩家进行选择的文字提示
