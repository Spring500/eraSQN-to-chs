# @CHARA_BUY

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 梦魔召唤入口菜单

### 所在文件

+ [Shop2.erb](/ERB/SHOP/Shop2.erb#L14-L79)

### 调用关系

**被调用**：

+ `@USERSHOP`<sup>[说明文件](Wiki/erasqn_wiki/function/u/usershop.md)</sup>

**调用**：

+ `@CHAR_SAMON_T`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/char_show_t.md)</sup>

+ `@CHARA_BUY_SHOW`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/chara_buy_show.md)</sup>

+ `@CHARA_MANUAL`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/chara_manual.md)</sup>

+ `@IS_SAMONTRBL`<sup>[说明文件](/Wiki/erasqn_wiki/function/i/is_samontrbl.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 当玩家选择`不召唤返回`或函数正常结束时返回`0`

#### 功能实现

**L15**：

声明变量`MEMO_LINECOUNT`。

**L19**：

将`FLAG:99`的第13个二进制位设为`1`，打开角色创建中标志

**L21**：

将引擎到目前为止所显示过的行数`LINECOUNT`赋值给`MEMO_LINECOUNT`

**L24**：

调用函数`@CHARA_BUY_SHOW`显示可召唤的角色列表

**L26-L27**：

声明跳转标记`$INPUT_LOOP`

使用引擎指令`INPUT`，读取玩家输入。

**L29-L30**：

如果玩家输入的是`100`，则返回`0`

**L32-L33**：

如果玩家的输入`RESULT < 0`或`RESULT > 98`时，则输入不合法：

  + 跳转到声明标记`$INPUT_LOOP`重新读取玩家的输入

**L35-L36**：

如果`ITEMSALES:(RESULT + 100)`的值为`0`时，则说明该梦魔（或这个号码的物件）目前不在商店出售：

  + 跳转到声明标记`$INPUT_LOOP`重新读取玩家的输入

**L38-L40**：

当玩家输入的是`34`或`35`且玩家不具备能力`TALENT:MASTER:谜之魅力`时：

  + 提示`未打到调教条件`

  + 跳转到声明标记`$INPUT_LOOP`重新读取玩家的输入

**L42-L44**：

当所持金钱`MONEY`小于`ITEMPRICE:(RESULT + 100)`该梦魔的售价时：

  + 提示`所持金钱不足`

  + 跳转到声明标记`$INPUT_LOOP`重新读取玩家的输入

**L48-L50**:

将玩家的选择`RESULT`赋值给`C`

将`E`置为`0`

**L52**：

调用`@CHARA_MANUAL, C`，显示角色说明

**L54-L60**：

如果`@CHARA_MANUAL`返回`0`：

  + 调用引擎命令`DELCHARA`，删除角色号为`CHARANUM - 1`的角色

  + 调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容。

  + 调用引擎命令`RESATRT`，重新从头执行本函数

**L63-L64**：

当`E`小于`2`时，将`E`置为`0`

**L67-L68**：

将玩家持有的金钱`MONEY`扣减角色价格`ITEMPRICE:(100 + C)`

将调教对象`TARGET`设为新召唤的角色`CHARANUM - 1`

**L71-L75**：

如果发生了召唤事故（`@IS_SAMONTRBL`返回不为`0`）：

  + 当`FLAG:8`不为`0`时：

    + 打印发生了召唤事故

  + 调用`@CHAR_SAMON_T, C`

**L77**：

输出召唤完成的提示

**L79**：

返回`0`
