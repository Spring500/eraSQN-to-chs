# @LOADGAME_EX

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/function/README.md)

### 作用描述

+ 读取存档

### 所在文件

+ [Saveload.erb](/ERB/Saveload.erb#L77)

### 调用关系

**被调用**：

+ `@SYSTEM_TITLE`<sup>[说明文件](/Wiki/function/s/system_title.md)</sup>

**调用**：

+ `@PRINT_SAVEDATA`<sup>[说明文件](/Wiki/function/p/print_savedata.md)</sup>

+ `CHKDATA`<sup>[文档](https://osdn.net/projects/emuera/wiki/excom#h5-CHKDATA.20.3C.E6.95.B0.E5.BC.8F.3E)</sup>

+ `LOADDATA`<sup>[文档](https://osdn.net/projects/emuera/wiki/excom#h5-LOADDATA.20.3C.E6.95.B0.E5.BC.8F.3E)</sup>

### 函数实现

#### 参数

无参数

#### 返回值

+ 如果没有读取存档，选择了返回上层菜单，就会返回`%LOCALS:2%`

#### 功能实现

L84-L85：如果`SAVESTR:11`变量的值长度不为`0`，就打印出目前游玩存档的故事名称（需找到定义语句）

L88：调用`@PRINT_SAVEDATA`，显示存档列表

L89：调用引擎内置函数`CHKDATA`，检查第99号存档，如果存档存在，存档信息就会被写到变量`%RESULTS:0%`中，读取时间储存在`%LOCALS:2%`

L90：将`RESULTS:0`显示到第99号选项

L94：读取用户输入

L95-L97：如果输入100，输入合法，则`RETURN`，结束函数，继续执行调用函数后面的部分

L98：如果输入的数小于0，或大于引擎设定的最大存档数`SAVENOS()`，或不等于99，输入不合法，则什么都不做

L100：如果输入的数，>=`FLAG:1 * 20`且小于`FLAG:1 * 20 + 20`（落在`@PRINT_SAVEDATA`显示列表的序号区间），则输入合法，执行L101-L109

L101-L109：调用引擎内置函数`CHKDATA`，检查输入的存档号数，如果存档存在，就调用引擎内置函数`LOADDATA`加载该存档；如果存档不存在，就打印错误提示并跳转到L82的`$REDRAW_SAVEDATA`标记，重新显执行本函数

L113：如果输入的数不在存档列表区间，也没有选择返回，也没有出错，而是落在翻页编号选项时，就改变`FLAG:1`的值，让其`= RESULT/20`

L115：跳转到L87的`$REDRAW_SAVEDATA2`标记，立即调用`@PRINT_SAVEDATA`并以`FLAG:1`为参数，进行存档槽列表翻页显示

L119：如果输入的值还是出错，就跳转到L93的`$INPUT_DATANUM`标记，要求用户重新输入
