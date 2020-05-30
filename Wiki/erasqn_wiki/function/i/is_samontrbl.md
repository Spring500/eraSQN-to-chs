# @IS_SAMONTRBL

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 根据设定和MASTER的能力，返回`0`或`1`

### 所在文件

+ [Shop2.erb](/ERB/SHOP/Shop2.erb#L81-L94)

### 调用关系

**被调用**：

+ `@CHARA_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/chara_buy.md)</sup>

**调用**：

+ `@CHAR_SAMON_T`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/char_samon_t.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 返回`1`代表发生召唤事故

+ 返回`0`代表不发生召唤事故

#### 功能实现

**L84-L85**：

当`FLAG:666`值为`1`或MASTER拥有`TALENT:MASTER:天灾召唤师`天赋时：

  + 返回`1`

**L87-L88**：

当MASTER拥有`TALENT:MASTER:天才召唤师`天赋以及`CONFIG("召喚事故")`返回`1`时：

  + 返回`1`

**L90-L91**：

当`@COND("ユニーク")`返回`1`，且`CONFIG("召喚事故：ユニーク")`返回`0`时：

  + 返回`0`

**L92-L93**：

当`CONFIG("召喚事故")`返回`1`，且计算一次随机数`RAND:3`结果为`0`时：

  + 返回`1`

**L94**：

默认情况下返回`0`
