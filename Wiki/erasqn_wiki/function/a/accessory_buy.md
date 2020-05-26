# @ACCESSORY_BUY

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 判断饰品盒是否装满

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L976-L980)

### 调用关系

**被调用**：

+ `@ACCESSORY_SHOP_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop_buy.md)</sup>

**调用**：

+ 不调用其他函数

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ `0`或`1`

#### 功能实现

**L978-L979**：

当`FLAG:380`为`0`（没有记录有饰品时），返回`1`。

**L780**：

否则返回`0`。
