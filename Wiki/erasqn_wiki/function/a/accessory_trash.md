# @ACCESSORY_TRASH

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 丢弃饰品

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L496-L551)

### 调用关系

**被调用**：

+ `@ACCESSORY_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_select.md)</sup>

**调用**：

+ `@ACCESSORY_EQUIP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_equip.md)</sup>

+ `@ACCESSORY_SET_TALENT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_set_talent.md)</sup>

+ `@NUM`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/num.md)</sup>

+ `@PRINT_ACCESSORY`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_accessory.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 当用户选择`返回上层菜单`或`@NUM("所持アクセサリ")`饰品数为`0`时，返回`0`

#### 功能实现

**L555-L557**：

声明数组变量`LCOUNT`

声明变量`MEMO_LINECOUNT`，用于记录到目前为止引擎显示过的行数

记录引擎到目前为止显示过的行数

**L561-L562**：

打印丢弃饰品功能菜单的头部提示

**L565-569**：

以`LOCAL`作为迭代数，循环`8`次

  + 调用`@PRINT_ACCESSORY, LOCAL`，打印全部已鉴定的饰品

打印`返回上层菜单`的菜单项

**L571-L572**：

声明跳转标记`$INPUT_LOOP`。

使用引擎指令`INPUT`，读取玩家输入。

**L574-L577**：

如果玩家输入的是`100`：

  + 调用`@ACCESSORY_SET_TALENT`更新MASTER的天赋

  + 返回`0`

**L578-L603**：

如果玩家的输入`1 <= RESULT <= 8`，且`FLAG:3X0`不为`0`（该饰品槽有饰品）：

  + 当`FLAG:399`与玩家的输入相等时：

    + 调用`@ACCESSORY_EQUIP, "外す"`卸下该饰品

  + 当`FLAG:399`大于玩家的输入时：

    + 让`FLAG:399`扣减`1`（先将正在装备的饰品槽标记向前移动一位）

  + 调用引擎命令`VARSET`，将`FLAG:3X0～3X0+10`置为`0`（清空被选择的饰品槽的所有数据）

  + 以`LCOUNT`为迭代数，FOR循环`8`次：

      + 将`LOCAL`置为`300 + CHOICE:2*10 + LCOUNT*10`作为持有饰品前移的指针

      + 当`LOCAL`指针大于或等于`380`时，则说明所有饰品都已经完成移动

        + 以`LCOUNT:1`为迭代数，FOR循环`10`次：

          + 交换`FLAG:(LOCAL + LCOUNT:1),`与`FLAG:(LOCAL + 10 + LCOUNT:1)`的值，被清空的饰品槽后面的饰品向前移动，以防止出现不连贯的已使用饰品槽

    + 如果`NUM("所持アクセサリ")`持有的饰品为`0`

      + 返回`0`

**L604-L605**：

如果玩家的输入不合法：

  + 则跳转到声明标记`$INPUT_LOOP`重新读取玩家的输入

**L608-L609**：

调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容

调用引擎命令`RESTART`，重新从头执行本函数
