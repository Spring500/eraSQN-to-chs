# @SYSTEM_TITLE

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ Emuera引擎的入口

+ 游戏开始首屏显示：游戏名、版本和作者等信息

+ 提供开始新游戏和读取进度的选项

### 所在文件

+ [Title.erb](/ERB/Title.erb#L14-L75)

### 调用关系

**被调用**：

+ 直接被Emuera引擎调用，是整个游戏的入口

**调用**：

+ `@EVENTFIRST`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/eventfirst.md)</sup>

+ `@LOADGAME_EX`<sup>[说明文件](/Wiki/erasqn_wiki/function/l/loadgame_ex.md)</sup>

+ `ADDDEFCHARA`<sup>[文档](https://osdn.net/projects/emuera/wiki/excom%23h5-ADDDEFCHARA)</sup>

+ `BEGIN FIRST`<sup>[文档](https://osdn.net/projects/emuera/wiki/excom#h5-BEGIN.20.3C.E3.82.AD.E3.83.BC.E3.83.AF.E3.83.BC.E3.83.89.3E)</sup>

### 函数实现

#### 参数

无参数

#### 返回值

无返回值

#### 功能实现

**L25-L30**：

通过引擎内置变量读取[/CSV/GameBase.csv](/CSV/GameBase.csv)里的游戏版本信息，将整型的游戏版本转化成`.`分隔的版本号。

**L33**：

声明跳转标记`$TITLE_SELECT`。

**L36-L42**：

通过引擎内置变量读取[/CSV/GameBase.csv](/CSV/GameBase.csv)里的游戏标题、版本信息、作者、制作年、附加信息，然后显示到游戏标题屏幕。

**L43-L49**：

通过读取[/CSV/Strname.csv](/CSV/Strname.csv)里的汉化版描述信息，然后显示到游戏首屏。

**L54-L55**：

显示新游戏和读取菜单。

**L56**：

声明跳转标记`$TITLE_INPUT`。

**L57**：

读取玩家输入的选择项。

**L58-L74**：

如果玩家在上一步中输入的是`0`，

  1. 调用引擎命令`RESETDATA`初始化所有变量。

  2. 调用引擎命令`ADDDEFCHARA`读取[/CSV/CHARA/Chara0.csv](/CSV/CHARA/Chara0.csv)作为玩家角色初始值，并开始初始化游戏。

  3. 调用引擎命令`BEGIN FIRST`，执行`@EVENTFIRST`。

如果玩家在上一步中输入的是`1`，

  1. 调用`@LOADGAME_EX`，进入存档加载画面。

  2. 当`@LOADGAME_EX`执行结束后，跳转到标记`$TITLE_SELECT`，重新显示游戏标题屏幕。

如果玩家在上一步中的输入既不是`0`也不是`1`，则输出提示`数值无效`，接着跳转到标记`$TITLE_INPUT`，重新读取玩家输入。
