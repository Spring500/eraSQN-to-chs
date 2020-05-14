# @EVENTFIRST

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 开始新游戏

+ 执行引擎内置命令`BEGIN FIRST`后会被自动调用

### 所在文件

+ [System_Newgame.erb](/ERB/System_Newgame.erb#L1-L201)

### 调用关系

**被调用**：

+ `@SYSTEM_TITLE`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/system_title.md)</sup>

**调用**：

+ `@CONFIG`<sup>[说明文件](/Wiki/function/c/config.md)</sup>

+ `@INPUT_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/i/input_select.md)</sup>

+ `@LOAD_CONFIGURE`<sup>[说明文件](/Wiki/erasqn_wiki/function/l/load_configure.md)</sup>

+ `@LVUPCHECK_MASTER`<sup>[说明文件](/Wiki/erasqn_wiki/function/l/lvupcheck_master.md)</sup>

+ `@MONEY_C`<sup>[说明文件]()</sup>

+ `@NUM`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/num.md)</sup>

+ `@SETFLAG`<sup>[说明文件](Wiki/erasqn_wiki/function/s/setflag.md)</sup>

+ `@SET_CONFIGURE`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_configure.md)</sup>

+ `@SET_NEWNAME`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_newname.md)</sup>

+ `@START_CHARA_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/start_chara_select.md)</sup>

+ `@TEXT_RJ`<sup>[说明文件](/Wiki/erasqn_wiki/function/t/text_rj.md)</sup>

+ `@VER_ERASQ`<sup>[说明文件](/Wiki/erasqn_wiki/function/v/verup_erasqn.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 无返回值

#### 功能实现

**L3**：

用`FLAG:29`记录当前eraSQN的版本。

**L5**：

将`ASSI`助手设为`0`。

**L6**：

将游戏内的日期`DAY`设为`1`。

**L8**:

调用`@SETFLAG, "アイテムフラグ調整"`，批量处理所有物品的售价以及清空魔法瓶内的精液量。

**L10**：

将`FLAG:6`置为`1`。

**L12**:

将`FLAG:7`置为`1`，打开口癖显示。

**L13**：

将`FLAG:8`置为`1`，打开判定值显示。

**L16-L17**：

将`FLAG:11`的第1和2bit置为`1`，重置主人的外表年龄以及乳头的详细设定。

**L19**：

将`FLAG:98`的第1bit置为`1`。

（作用不明，过后研究）

**L21-L25**：

删除角色号为`0`的角色（推测是系统初始化时自动创建的角色）。

加载`Chara93.csv`为`0`号角色（这个角色似乎是隐藏角色，作用需要更多代码佐证），

加载`Chara0.csv`为`1`号角色，

将`MASTER`置为`1`。

**L28**：

加载GLOBAL变量。

**L30-31**：

将变量`LOCAL`置为空值。

声明跳转标记`$SELECT_MOOD`。

**L34-L37**：

打印三个选项，分别为难度：NORMAL、难度：EASY和游戏设定供玩家选择。

**L38-L40**：

当`GLOBAL:99`（上次全局设定存档时间）大于`0`且`LOCAL`为`0`时，打印[读取上次设定]的选项及上次全局设定保存的时间。

**L40-L67**：

打印[返回]选项。

**L42**：

声明跳转标记`$INPUT_LOOP`。

**L43**：

读取用户输入。

如果玩家在上面菜单中输入的是`100`，

  + 就使用系统内置命令`BEGIN TITLE`，重新显示游戏标题画面。

如果玩家在上面菜单中输入的是`11`，且`GLOBAL:99`大于`0`，且`LOCAL`为`0`时

  + 调用`@LOAD_CONFIGURE`

  + 如果`@CONFIG("自動購入") 即 FLAG:9`不为`0`

    + 如果`FLAG:9`的第6bit为`1`，就将`FLAG:9`置为`1p6`<br/>（将第1bit置为`1`，然后左移6bit，空余位置补`0`，此处十进制数值为`64`）。

    + 否则将`FLAG:9`置为`0`。

  + 将`LOCAL`置为`1`。

  + 跳转到标记`$INPUT_LOOP`。

如果玩家在上面菜单中输入的是`10`，

  + 调用`@SET_CONFIGURE`。

  + 跳转到标记`$SELECT_MOOD`。

如果玩家在上面菜单中输入的是`1`，

  + 将`FLAG:220`置为`1`（设定游戏难度为NORMAL）。

  + 打印难度描述。

如果玩家在上面菜单中输入的是`0`，

  + 什么都不需要做。

如果玩家在上面菜单中输入的东西不再可选选项内，

  + 跳转到标记`$INPUT_LOOP`，让玩家重新输入选择。

**L69**:

调用`@START_CHARA_SELECT`，让玩家选择角色。

**L71**：

调用`@SET_NEWNAME, MASTER`，让玩家设置玩家角色姓名。

**L73-L74**：

将`PLAYER`置为`MASTER`。

将调教对象`TARGET`置为`0`。

**L76-L150**：

当玩家角色的角色编号`NO:MASTER`（角色对应`Chara**.csv`里面的`番号`）为`0`、`34`和`35`时，分别打印不同的开场白。

**L151-L158**：

当玩家的角色编号`NO:MASTER`为`34`或`35`时，

  + 调用引擎命令`ADDCHARA 94`，以`Chara94.csv`为模板，新增角色。

  + 将`FLAG:1093`（角色购买标志之一）置为`1`。

  + MASTER获得天赋`TALENT:MASTER:无视污臭`。

  + MASTER获得天赋`TALENT:MASTER:高潮管理`。

  + 将新增的角色设为`TARGET`。

  + 调用`@SET_NEWNAME`为角色设定名字。

**L160**：

将起始金钱设为`10,000`。

**L162-L166**：

当`FLAG:4`（攻略周回数）为`0`时，输出相应的提示。

**L169-L193**：

寻味玩家是否使用作者推荐的设定集，如果玩家选择使用作者推荐的配置集就作以下配置：

+ `FLAG:211 = 1p0 + 1p1`<br/>(FLAG:211, 1bit=1 2bit=1)<br/>打开怀孕补丁 and 可以通过MASETR的精子怀孕

+ `FLAG:209 |= 1p4 + 1p6`<br/>(FLAG:209, 5bit=1, 7bit=1)<br/>打开判定值显示，打开脱処女フィルタ（作用不明，过后研究）

+ `FLAG:223 = 1`<br/>恍惚状态时任凭梦魔摆布

+ `FLAG:250 = 1`<br/>显示未获得的经验值

+ `FLAG:239 = 1p0 + 1p1`<br/>(FLAG:239, 1bit=1, 2bit=1)<br/>打开三围和身高显示

+ `FLAG:205 = 1`<br/>打开日常事件描写显示

+ `FLAG:98 = 1p0 + 1p2 + 1p5`<br/>(FLAG:98, 1bit=1, 3bit=1, 6bit=1)<br/>画面表示：カラーバー、パラメータ４列、バーのグラフ表示

并输出响应的提示。

**L197**：

调用`@LVUPCHECK_MASTER`，设定MASTER的经验值以及等级上限。

**L199**：

将MASTER的基础STOCK设为MASTER的STOCK上限值。

**L201**：

调用引擎命令`BEGIN SHOP`。
