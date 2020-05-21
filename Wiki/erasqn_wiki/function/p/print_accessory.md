# @PRINT_ACCESSORY

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 打印饰品的名称及特性

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L222-L272)

### 调用关系

**被调用**：

+ `@ACCESSORY_SHOP_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop_buy.md)</sup>

**调用**：

+ `@ACCESSORY_EFFECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

+ `@BL`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

+ `@DEF_COLOR`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

+ `@PRINT_ACCESSORY_NAME`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

+ `@PRINT_COLORTEXT`<sup>[说明文件](/Wiki/erasqn_wiki/function/func_template.md)</sup>

### 函数实现

#### 参数

+ ARG

#### 返回值

+ 当要显示的饰品槽为空时返回`0`

#### 功能实现

**L231**：

声明变量`LOCAL`，并将其置为`300 + ARG*10`（要显示的饰品的第一个FLAG标号）。

**L232-233**：

如果`FLAG:LOCAL`为`0`（饰品槽为空），则返回`0`。

**L235**：

以传入的`ARG`作为选项标号，并调用`@PRINT_ACCESSORY_NAME(FLAG:LOCAL)`打印出改饰品的名称，接着打印改饰品的等级`FLAG:(LOCAL + 9) + 1`

（饰品等级FLAG，从程序逻辑上来说是以`0`开始计算；<br/>而从玩家逻辑上来说是以`1`开始计算，所以要加上`1`）

（没错，此处就是`程序猿数数都是从0开始数`的那个冷笑话，<br/>绝大部分程序语言，都是从0开始数数的）

**L236-L240**：

如果`FLAG:399`的值等于传入的参数ARG，这说明玩家正在装备此饰品。

在行末输出一个黄色的`Ｅ`，表示该饰品装备中。

**L242-247**：

当`FLAG:(LOCAL + 8)`的1bit为`1`时，在行末再输出一个黄色的`合成ベース`（与饰品合成有关，需要更多代码佐证）。

**L250**：

将饰品等级`FLAG:3X9`，存到`LOCAL`中。

**L252-L265**：

以`FLAG:(3X0)/10`的值作为选择支，

  + 当值为`0`时，输出`精神力＋{25 + LOCAL * 10}％　魅力＋{5 + LOCAL * 5}％`

  + 当值为`1`时，输出`精神力＋{5 + LOCAL * 5}％　魅力＋{25 + LOCAL * 10}％`

  + 当值为`2`时，输出`技巧＋{15 + LOCAL * 5}％　精神力＋{5 + LOCAL * 5}％　魅力＋{15 + LOCAL * 5}％`

  + 当值为`3`时，输出`精力＋{15 + LOCAL * 5}％　精神力＋{5 + LOCAL * 5}％　魅力＋{15 + LOCAL * 5}％`

  + 当值为`4`时，输出`技巧＆精力＆精神力＆魅力＋{5 + LOCAL * 5}％`

  + 当值为`5`时，输出`技巧＆精力＆精神力＆魅力＋{25 + LOCAL * 10}％`

**L267-L271**：

将输出颜色设为黄色。

以`LCOUNT`记录迭代数，FOR循环`5`次：

 当`FLAG:3X0 + LCOUNT`的值不为`0`时，调用`@ACCESSORY_EFFECT(FLAG:(3X0 + LCOUNT))`，输出该饰品的加成效果

重置输出颜色。