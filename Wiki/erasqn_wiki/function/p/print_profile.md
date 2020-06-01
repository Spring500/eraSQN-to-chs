# @PRINT_PROFILE

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 作用描述

### 所在文件

+ [Shop3.erb](/ERB/SHOP/Shop3.erb#L892-L996)

### 调用关系

**被调用**：

+ `@PROFILE`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/profile.md)</sup>

**调用**：

+ `@ANALYSIS_CALC`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/analysis_calc/.md)</sup>

+ `@COND`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/cond.md)</sup>

+ `@NEW_PRINT_STATE`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/new_print_state.md)</sup>

+ `@SETFLAG`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/setflag.md)</sup>

+ `@SHOW_DIFFICULTY`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/show_difficulty.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 无返回值

#### 功能实现

**L893**：

调用`@NEW_PRINT_STATE, TARGET, "召喚"`，打印部分角色素质

**L896-L921**：

如果角色拥有下列全部素质时：<br/>（`TALENT:Ｍ敏感`、`TALENT:Ｃ敏感 `、`TALENT:Ｖ敏感`、`TALENT:Ａ敏感`和`TALENT:Ｂ敏感`）

  + 输出`全部位弱点`

否则当角色**未**拥有下列任一素质时：<br/>（`TALENT:Ｍ敏感`、`TALENT:Ｃ敏感 `、`TALENT:Ｖ敏感`、`TALENT:Ａ敏感`和`TALENT:Ｂ敏感`）

  + 输出`无弱点部位`

 否则：

  + 将`LOCALS`置为空值

  + 当角色拥有素质`TALENT:Ｍ敏感`时：

    + `LOCALS`追加赋值`亲吻、`

  + 当角色拥有素质`TALENT:Ｃ敏感`或`TALENT:Ｖ敏感`时：

    + `LOCALS`追加赋值`阴部、`

  + 当角色拥有素质`TALENT:Ｂ敏感`时：

    + `LOCALS`追加赋值`胸部、`

  + 当角色拥有素质`TALENT:Ａ敏感`时：

    + `LOCALS`追加赋值`臀部、`

  + 当`COND("精飲に弱い")`返回不为`0`时：

    + `LOCALS`追加赋值`饮精、`

  + 当`COND("膣内射精に弱い")`返回不为`0`时：

    + `LOCALS`追加赋值`膣内射精、`

  + 当`COND("肛内射精に弱い")`返回不为`0`时：

    + `LOCALS`追加赋值`肛内射精、`

  + 当`COND("乳内射精に弱い")`返回不为`0`时：

    + `LOCALS`追加赋值`乳内射精、`

  + 调用引擎命令`STRLENS`计算`LOCALS`的字符长度（结果会自动存到`RESULT`）

  + 调用引擎命令`SUBSTRING`，生成`LOCALS`第0～(RESULT - 2)个字符的子字符串（结果会自动存到`RESULTS`）

  + 打印出`RESULTS`（前两步是为了去除整个字符串结尾的`、`）

**L923-L968**：

调用引擎命令`VARSET`将`LOCALS`置为空值

当角色拥有下列素质时：<br/>（好色、强硬、清纯、开朗、坦率、阴郁、腼腆、胆怯、坏心眼、抖Ｓ、高傲、自备、沉着、狂气、献身、斯文、粗野、聪慧、糊涂）<br/>（每项素质一个`SIF`）

  + 将`%LOCALS%%TALENTNAME:[素质编号]%、`赋值给`LOCALS`

如果`LOCALS`大于`0`时：<br/>（角色拥有上述任意一种素质）

  + 打印`LOCALS`的第0～(RESULT - 2)个字符的子字符串

否则：

  + 打印`？`

**L971-L972**：

调用`@ANALYSIS_CALC`，（作用不明，过后研究）

调用`@SHOW_DIFFICULTY`，显示该角色的调教难易度

**L974-L975**：

调用引擎命令，将变量`SOURCE`和`CUP`重置为`0`

**L977-L996**：

调用`@SETFLAG, "売却価格", TARGET`，计算角色的售价（素质）

以`CFLAG:42`（价格：基础素质）为选择支：

  + 当其值大于等于`10,000`时，输出`SSS`

  + 当其值大于等于`8,000`时，输出`SS`

  + 当其值大于等于`6,000`时，输出`S`

  + 当其值大于等于`4,000`时，输出`A`

  + 当其值大于等于`2,000`时，输出`B`

  + 当其值大于等于`1,000`时，输出`C`

  + 当其值大于等于`500`时，输出`D`

  + 否则，输出`E`
