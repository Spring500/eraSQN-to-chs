# @ACCESSORY_COUNT

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 返回已记录饰品的饰品槽个数

### 所在文件

+ [Accessory_System.erb](/ERB/SHOP/Accessory_System.erb#L982-L994)

### 调用关系

**被调用**：

+ `@ACCESSORY_SHOP_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop_buy.md)</sup>

**调用**：

+ 不调用其他函数

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ `0～8`

#### 功能实现

**L984-L985**：

声明变量`LCOUNT`和`ACCESSORY_NUM`

**L987**：

调用引擎命令`VARSET`将变量`ACCESSORY_NUM`置为`0`

**L989-L992**：

以`LCOUNT`作为迭代数，FOR循环`8`次：

  + 当`FLAG:(300 + LCOUNT * 10)`不为`0`

    + 就让`ACCESSORY_NUM`自增`1`

**L994**：

返回`ACCESSORY_NUM`
