# @ACCESSORY_PIERISRAPAE

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 整合饰品

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L376-L493)

### 调用关系

**被调用**：

+ `@ACCESSORY_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_select.md)</sup>

+ `@ACCESSORY_SHOP_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop_buy.md)</sup>

**调用**：

+ `@ACCESSORY_EQUIP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_equip.md)</sup>

+ `@NUM`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/num.md)</sup>

+ `@PRINT_ACCESSORY`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_accessory.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

返回值描述

#### 功能实现

**L377-L379**：

声明数组变量`LCOUNT`、`CHOICE`以及整数变量`MEMO_LINECOUNT`

**L381-L382**：

初始化变量`CHOICE`。

用变量`MEMO_LINECOUNT`用于记录引擎到目前位置所显示过的行数

**L392-L394**：

以`LOCAL`为迭代数，循环`8`次：

  + 调用`@PRINT_ACCESSORY, LOCAL`，以打印出所有拥有的饰品

**L397-L408**：

如果`@NUM("所持アクセサリ")`持有的饰品数小于等于`1`：

  + 打印提示`饰品太少无法整合`

  + 然后以`LCOUNT`作为迭代数，循环`8`次

    + 将所`FLAG:3X8`置为`0`，清除纹白蝶FLAG

  + 调用`@ACCESSORY_EQUIP`更新已装备的属性

  + 返回`0`

**L400-L401**：

声明跳转标记`$INPUT_LOOP`

使用引擎指令`INPUT`，读取玩家输入

**L421-L488**：

如果玩家的输入`1 <= RESULT <= 8`，且`FLAG:(300 + RESULT*10)`该饰品槽位第1个FLAG槽不为`0`：

  + 以`CHOICE:2`记录玩家的输入

  + 用引擎命`INVERTBIT`命令对`FLAG:3X8`的第1个二进制位取反

  + 以`LCOUNT`为迭代数，循环`8`次：

    + 当`FLAG:3X8`的第1个二进制位为`0`时，跳过后面的代码直接执行下一次循环

    + 当`LCOUNT`与`CHOICE:2`（玩家的输入）不相等时，用`CHOICE:1`记录目前的`LCOUNT`（目前循环到的饰品槽位）

  > 当玩家第1次选择饰品时，`CHOICE:1`为`0`，而`CHOICE:2`会记录第1次选择的饰品，同时该饰品的标记FLAG会置为`1`。

  > 然后因为`CHOICE:1`为`0`所以整合代码会被跳过。

  > 此时`RESTART`此函数，再做一次选择，`CHOICE:2`会记录第2次选择的槽位，代码到达上面的循环后，就会找出之前被标记的槽位，并将其存到`CHOICE:1`。

  > 至此，`CHOICE:1`与`CHOICE:2`都不为`0`，程序就会执行整合饰品的代码了。

  + 如果`CHOICE:1`与`CHOICE:2`都不为`0`：

    + 调用`@PRINT_ACCESSORY, CHOICE:1`显示第1次选择的饰品

    + 将第2次选择的饰品的`FLAG:3X8`的第1个二进制位重置为`0`

    + 调用`@PRINT_ACCESSORY, CHOICE:2`显示第2次选择的饰品

    + `ITEM:纹白蝶`的数量扣减`1`

    + 第1次选择的饰品槽的等级`FLAG:3X9`变为第1次选择饰品的等级加上`(第2次选择饰品的等级 + 1) / 2`

    + 检查第1次选择的饰品等级此时是否大于`9`，如果大于`9`，就将其置为`9`（10级）

    + 以`LCOUNT`为迭代数，FOR循环5次：

      + 当第1次选择的饰品`FLAG:3X0 + LCOUNT`不为`0`时，跳过后面的代码，直接执行下一次循环

        + 以`LCOUNT:1`为迭代数，FOR循环5次：

          + 判断`LCOUNT`与`LCOUNT:1`两层循环的迭代数总和是否超过了一个饰品最大效果数槽位，如果超过了就立即退出循环

          + 将第2次选择的饰品的效果FLAG`FLAG:(300 + CHOICE:2*10 + 1 + LCOUNT:1)`的值<br/>赋值给第1次选择的饰品空着的效果FLAG`FLAG:(300 + CHOICE:1*10 + LCOUNT + LCOUNT:1)`

      + 然后将`FLAG:(300 + CHOICE:1*10 + 8)`第1次选择的饰品的纹白蝶FLAG重置为`0`

      + 调用`@PRINT_ACCESSORY, CHOICE:1`打印出整合后第1次选择的饰品的最新参数，并提示整合完成

      + 如果玩家之前装备的饰品`FLAG:399`为第2次选择的饰品`CHOICE:2`：

        + 就将正在装备的饰品改成第1次选择的饰品`CHOICE:1`

        + 调用`ACCESSORY_EQUIP`更新已装备的饰品效果参数

      + 否则，当玩家之前装备的饰品`FLAG:399`位于第2次选择的饰品之后的槽位时：

        + 让当前装备的饰品槽位减`1`

      + 调用引擎命令`VARSET`，将第2次选择的饰品的所有FLAG置为`0`（将该饰品删除）

      + 以`LCOUNT`为迭代数，FOR循环`8`次：

        + 将`LOCAL`置为`300 + CHOICE:2*10 + LCOUNT*10`作为持有饰品前移的指针

        + 当`LOCAL`指针大于或等于`380`时，则说明所有饰品都已经完成移动

          + 以`LCOUNT:1`为迭代数，FOR循环`10`次：

            + 交换`FLAG:(LOCAL + LCOUNT:1),`与`FLAG:(LOCAL + 10 + LCOUNT:1)`的值，被清空的饰品槽后面的饰品向前移动，以防止出现不连贯的已使用饰品槽

  + 否则（`CHOICE:1`与`CHOICE:2`其中之一或两者都为`0`）

    + 调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容

    + 调用引擎命令`RESATRT`，重新从头执行本函数，让玩家重新选择要整合的饰品

**L489-L490**：

如果玩家的输入不合法：

  + 则跳转到声明标记`$INPUT_LOOP`重新读取玩家的输入

**L493**：

调用引擎命令`RESATRT`，重新从头执行本函数
