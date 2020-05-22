# @ACCESSORY_SET_TALENT

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 作用描述

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L645-L703)

### 调用关系

**被调用**：

+ `@ACCESSORY_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_select.md)</sup>

+ `ACCESSORY_SHOP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop.md)</sup>

+ `@ACCESSORY_TRASH`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_trash.md)</sup>

**调用**：

+ `@ACCESSORY_EQUIP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_equip.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 当没有装备饰品或解除装备饰品时，返回`0`

#### 功能实现

**L646**：

声明变量`LCOUNT`。

**L654**：

将`TALENT:MASTER:0`的第500～599个元素设为`0`。

**L656-L661**：

如果`FLAG:399`为`0`（没有装备饰品），

  + 调用`@ACCESSORY_EQUIP, "外す"`，然后返回`0`

否则（装备了饰品），

  + 调用`@ACCESSORY_EQUIP`


**L663-L670**：

以`LCOUNT`记录迭代数，使用FOR循环5次：

  + 将`LOCAL`置为`300+LCOUNT`

  + 假如`FLAG:LOCAL / 1000`的结果为`0`，则直接跳过后面的语句，立即执行下次循环

  + 让`TALENT:MASTER:(500 + FLAG:LOCAL/1000)`在现有的基础上加上`MAX(FLAG:LOCAL % 1000, 1)`（MAX可以接受任意多个参数，并返回其中的最大值）。

  **L673-L676**：

  当`TALENT:MASTER:大根术常态化`与`TALENT:MASTER:大根术常态化`都为`1`时，表示该项能力冲突。此时需要将这两项能力都置为`0`，取消此项能力冲突。

  **L678-L703**：

  以`(FLAG:300 / 10)`的值作为选择支：

  + 当结果为`0`时，为MASTER设置以下天赋

    ```
    TALENT:MASTER:精神力强化 += 25 + FLAG:309 * 10
	TALENT:MASTER:魅力强化 += 5 + FLAG:309 * 5
    ```

  + 当结果为`1`时，为MASTER设置以下天赋

    ```
    TALENT:MASTER:精神力强化 += 5 + FLAG:309 * 5
	TALENT:MASTER:魅力强化 += 25 + FLAG:309 * 10
    ```

  + 当结果为`2`时，为MASTER设置以下天赋

    ```
    TALENT:MASTER:技巧强化 += 15 + FLAG:309 * 5
	TALENT:MASTER:精神力强化 += 5 + FLAG:309 * 5
	TALENT:MASTER:魅力强化 += 15 + FLAG:309 * 5
    ```

  + 当结果为`3`时，为MASTER设置以下天赋

    ```
    TALENT:MASTER:精力强化 += 15 + FLAG:309 * 5
	TALENT:MASTER:精神力强化 += 5 + FLAG:309 * 5
	TALENT:MASTER:魅力强化 += 15 + FLAG:309 * 5
    ```

  + 当结果为`4`时，为MASTER设置以下天赋

    ```
    TALENT:MASTER:精力强化 += 5 + FLAG:309 * 5
	TALENT:MASTER:技巧强化 += 5 + FLAG:309 * 5
	TALENT:MASTER:精神力强化 += 5 + FLAG:309 * 5
	TALENT:MASTER:魅力强化 += 5 + FLAG:309 * 5
    ```

  + 当结果为`5`时，为MASTER设置以下天赋

    ```
    TALENT:MASTER:精力强化 += 5 + FLAG:309 * 5
	TALENT:MASTER:技巧强化 += 5 + FLAG:309 * 5
	TALENT:MASTER:精神力强化 += 5 + FLAG:309 * 5
	TALENT:MASTER:魅力强化 += 5 + FLAG:309 * 5
    ```
