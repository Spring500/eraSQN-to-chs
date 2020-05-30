# @CHARA_MANUAL

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 打印角色素质详情，并提供召唤确认菜单项

### 所在文件

+ [Shop3.erb](/ERB/SHOP/Shop3.erb#L1011-L1031)

### 调用关系

**被调用**：

+ `@CHARA_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/chara_buy.md)</sup>

**调用**：

+ `@FIX_TALENT`[说明文件](/Wiki/erasqn_wiki/function/f/fix_talent.md)</sup>

+ `@HIGH_RANKER_SHOW`[说明文件](/Wiki/erasqn_wiki/function/h/high_ranker_show.md)</sup>

+ `@PROFILE`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/profile.md)</sup>

### 函数实现

#### 参数

+ ARG

+ ARGS

#### 返回值

+ 根据玩家选择是否召唤上位种而返回不同的值

#### 功能实现

**L1002-L1004**：

声明变量`MEMO_LINECOUNT`

用`MEMO_LINECOUNT`记录引擎到目前为止所显示过的行数`LINECOUNT`

**L1006**：

调用`@PROFILE, ARG, ARGS`显示角色的档案

**L1009-L1015**：

如果`ARGS`为`MASTER`时：

  + 打印出确认提示

  + 打印出`确认`、`取消`、`重新生成`以及`自行指定素质`

否则：

  + 打印出确认提示

  + 打印出`确认`、`取消`、`重新召唤`以及`自行指定素质`

**L1017**：

调用`@HIGH_RANKER_SHOW, ARG`，显示`ARG`种族的高位种

**L1019-L1026**：

以上一步的调用结果作为选择支：

  + 当结果为`0`时，返回`1`

  + 当结果为`1`时，返回`0`

  + 当结果为`3`时，调用`@FIX_TALENT`

**L1029-L1031**：

调用引擎命令`DELCHARA`，删除角色编号为`CHARANUM - 1`的角色

调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容。

调用引擎命令`RESTART`，重新从头执行本函数。
