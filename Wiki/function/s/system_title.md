# @SYSTEM_TITLE

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/function/README.md)

### 作用描述

+ Emuera引擎的入口
+ 游戏开始首屏显示：游戏名、版本和作者等信息
+ 提供开始新游戏和读取进度的选项

### 所在文件

+ [Title.erb](/ERB/Title.erb#L14)

### 调用关系

**被调用**：

+ 直接被Emuera引擎调用，是整个游戏的入口

**调用**：

+ `@EVENTFIRST`<sup>[说明文件](/Wiki/function/e/eventfirst.md)</sup>

+ `@LOADGAME_EX`<sup>[说明文件](/Wiki/function/l/loadgame_ex.md)</sup>

+ `ADDDEFCHARA`<sup>[文档](https://osdn.net/projects/emuera/wiki/excom%23h5-ADDDEFCHARA)</sup>

+ `BEGIN FIRST`<sup>[文档](https://osdn.net/projects/emuera/wiki/excom#h5-BEGIN.20.3C.E3.82.AD.E3.83.BC.E3.83.AF.E3.83.BC.E3.83.89.3E)</sup>

### 函数实现

#### 参数

无参数

#### 返回值

无返回值

#### 功能实现

L25-L30：通过引擎内置变量读取[/CSV/GameBase.csv](/CSV/GameBase.csv)里的游戏版本信息，将整型的游戏版本转化成`.`分隔的版本号

L36-L42：通过引擎内置变量读取[/CSV/GameBase.csv](/CSV/GameBase.csv)里的游戏版本信息，然后显示到游戏首屏

L43-L49：通过读取[/CSV/Strname.csv](/CSV/Strname.csv)里的汉化版描述信息，然后显示到游戏首屏

L54-L55：显示新游戏和读取菜单

L64：调用引擎内置函数`ADDDEFCHARA`读取[/CSV/CHARA/Chara0.csv](/CSV/CHARA/Chara0.csv)作为玩家角色初始值，并开始初始化游戏

L65：调用引擎内置函数`BEGIN FIRST`，这个函数会自动调用`@EVENTFIRST`函数，正式开始新游戏

L68：调用函数`@LOADGAME_EX`，读取存档

L69：当用户在`@LOADGAME_EX`中没有读取到存档时，跳转到L57的标记`$TITLE_INPUT`，重新读取新的输入

L59.L67.L71：判断用户输入，0=新游戏/1=读取存档/其他=错误值，清除输入，并要求重新选择
