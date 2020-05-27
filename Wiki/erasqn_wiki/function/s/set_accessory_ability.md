# @SET_ACCESSORY_ABILITY


> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 定制饰品特殊效果

### 所在文件

+ [Accessory_Ordermade.erb](/ERB/SHOP/Accessory_Ordermade.erb#L122-L243)

### 调用关系

**被调用**：

+ `@ACCESSORY_ORDERMADE_MENU`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_ordermade_menu.md)</sup>

**调用**：

+ `@DEF_COLOR`<sup>[说明文件](/Wiki/erasqn_wiki/function/d/def_color.md)</sup>

+ `@MONEY_C`<sup>[说明文件](/Wiki/erasqn_wiki/function/m/money_c.md)</sup>

+ `@PRINT_ACCESSORY`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_accessory.md)</sup>

+ `@PRINT_COLORTEXT`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_colortext.md)</sup>

+ `@TEXT_RJ`<sup>[说明文件](/Wiki/erasqn_wiki/function/t/text_rj.md)</sup>

### 函数实现

#### 参数

+ ARG

#### 返回值

+ 当玩家选择`返回`时，返回`0`

+ 在效果选择时选择`这样就好了`时，返回`1`

#### 功能实现

**L123-L126**：

声明变量`LCOUNT`、`MEMO_PRICE`

声明变量`MEMO_LINECOUNT`，用于记录到目前为止引擎显示过的行数。

**L131-L136**：

调用引擎命令将`LOCAL`置为`0`

以`LCOUNT`作为迭代数，FOR循环`5`次：

  + 当`FLAG:(300 + ARG * 10 + LCOUNT)`为`0`时：<br/>（遇到该饰品位第1个空的饰品效果槽位）

    + 立即跳出循环

  + `LOCAL`自增`1`<br/>（已存在效果的效果槽位个数）

**L139-L146**：

以`LOCAL`作为选择支：

  + 当其值为`0`时，将`MEMO_PRICE`置为`0`

  + 当其值为`1`时，将`MEMO_PRICE`置为`5000`

  + 否则，将`MEMO_PRICE`置为`LOCAL * 10000`

**L148-L157**：

<del>以`LCOUNT`作为迭代数，FOR循环`100`次：<br/>（设置饰品效果时需要参照此FLAG）</del>

（但似乎去除也可以，去除掉可以节省大量的CPU……）

  + <del>以`LCOUNT`作为选择支：</del>

    + <del>当其值为`1～6`、`10～14`、`20～24`、`30～33`和`50～52`时：</del>

      + <del>如果`LOCAL`小于等于`4`，则将`LOCAL:LCOUNT`置为`1`</del>

    + <del>当其值为`99～100`时：</del>

      + <del>如果`LOCAL`不为`0`，则将`LOCAL:LCOUNT`置为`1`</del>

**L159-L176**：

以`LOCAL`作为选择支：

+ 当其值为`0`时：

  + 只打印`要附加怎样的效果`的提示

+ 否则：

  + 打印`目前饰品大概是这样子`的提示

  + 调用`@PRINT_ACCESSORY, ARG`打印出饰品的所有效果

  + 并打印预计需要花费的金钱

+ 以`LOCAL`作为选择支：

  + 当其值为`5`时：

    + 打印`效果已达上限`

  + 否则：

    + 打印`是否继续增加效果`

**L179-L213**：

当`LOCAL`大于等于`5`时，将输出颜色设为`灰色`

输出效果选择菜单项目

调用`RESETCOLOR`，将输出颜色设为默认值

当`LOCAL`的值为`0`时，将输出颜色设为`灰色`

输出`去除效果`和`这样就好`的菜单项目

调用`RESETCOLOR`，将输出颜色设为默认值

**L214-L215**：

声明跳转标记`$INPUT_LOOP`

调用引擎命令`INPUT`，读取玩家选择

**L216-L237**：

<del>当玩家的选择为`1 <= RESULT <= 100`，且`LOCAL:RESULT`不为`0`时：</del>（修改说明参考*L148-L157*）

当玩家的选择为`1 <= RESULT <= 100`时：

  + 以`RESULT`作为选择支：<br/>（设置饰品效果）

    + 如果玩家选择的是`100`，则返回`1`

    + 如果玩家选择的是`99`，则将`FLAG:3X0 + LOCAL`置为`0`

    + 如果玩家选择的事`1～5`，则将`FLAG:3X0 + LOCAL + 1`置为`RESULT * 1000 + 30`

    + 如果玩家选择的事`10～14`，则将`FLAG:3X0 + LOCAL + 1`置为`RESULT * 1000 + 50`

    + 如果玩家选择的事`20`，则将`FLAG:3X0 + LOCAL + 1`置为`RESULT * 1000 + 3`

    + 如果玩家选择的事`21`，则将`FLAG:3X0 + LOCAL + 1`置为`RESULT * 1000 + 7`

    + 如果玩家选择的事`22～24`或`50～52`，则将`FLAG:3X0 + LOCAL + 1`置为`RESULT * 1000 + 20`

    + 否则，则将`FLAG:3X0 + LOCAL + 1`置为`RESULT * 1000`

**L238-L239**：

如果玩家的输入不合法：

  + 则跳转到声明标记`$INPUT_LOOP`重新读取玩家的输入

**L242-L243**：

调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容。

调用引擎命令`RESTART`，重新从头执行本函数。
