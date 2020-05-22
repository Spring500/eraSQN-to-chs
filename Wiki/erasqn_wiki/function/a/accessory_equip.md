# @ACCESSORY_EQUIP

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 装上或卸下装饰品

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L633-L643)

### 调用关系

**被调用**：

+ `@ACCESSORY_FIRE`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_fire.md)</sup>

+ `@ACCESSORY_LVUP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_lvup.md)</sup>

+ `@ACCESSORY_PIERISRAPAE`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_pierisrapae.md)</sup>

+ `@ACCESSORY_SET_TALENT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_set_talent.md)</sup>

+ `@ACCESSORY_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_select.md)</sup>

+ `@ACCESSORY_SHOP_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop_buy.md)</sup>

+ `@ACCESSORY_TRASH`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_trash.md)</sup>

**调用**：

+ 不调用其他函数

### 函数实现

#### 参数

+ ARGS

#### 返回值

无返回值

#### 功能实现

**L635-L643**：

以`ARGS`的值作为选择支 ：

  + 当值为`外す`时，<br/>将`FLAG:399`置为`0`，将`FLAG:300～310`都置为`0`。

  + 否则，以`LOCAL`记录迭代数，从初值`0`到终值`9`执行十次循环

    + 将`FLAG:(300 + FLAG:399*10 + LOCAL)`的值赋给`FLAG:(300 + LOCAL)`

    + （将要装备的饰品的所有参数拷贝到`FLAG:300～310`）

    + 说明：`FLAG:399`的值为正在装备的饰品所在的饰品槽号数
