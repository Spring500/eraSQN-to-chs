# @NEW_PRINT_STATE

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 作用描述

### 所在文件

+ [New_Print_State.erb](/ERB/SHOP/New_Print_State.erb#L2-L499)

### 调用关系

**被调用**：

+ `@CREATE_CHARA`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/create_chara.md)</sup>

+ `@DAUGHTER_BIRTH`<sup>[说明文件](/Wiki/erasqn_wiki/function/d/daughter_birth.md)</sup>

+ `@PRINT_PROFILE`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_profile.md)</sup>

+ `@SET_DAUGHTER_NAME`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_daughter_name.md)</sup>

+ `@SHOW_CHARADATA`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/show_charadata.md)</sup>

+ `@SHOW_JUEL`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/show_juel.md)</sup>

+ `@USERCOM`<sup>[说明文件](/Wiki/erasqn_wiki/function/u/usercom.md)</sup>

**调用**：

+ `@ACCESSORY_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_select.md)</sup>

+ `@COND`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/cond.md)</sup>

+ `@CONDS`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/conds.md)</sup>

+ `@DEF_COLOR`<sup>[说明文件](/Wiki/erasqn_wiki/function/d/def_color.md)</sup>

+ `@EXP_NEXTLV`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/exp_nextlv.md)</sup>

+ `@GETBITS`<sup>[说明文件](/Wiki/erasqn_wiki/function/g/getbits.md)</sup>

+ `@HEARTMARK`<sup>[说明文件](/Wiki/erasqn_wiki/function/h/heartmark.md)</sup>

+ `@NEW_PRINT_3SIZE`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/new_print_3size.md)</sup>

+ `@NEW_PRINT_ABL`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/new_print_abl.md)</sup>

+ `@NEW_PRINT_EXP`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/new_print_exp.md)</sup>

+ `@NEW_PRINT_EXP50`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/new_print_exp50.md)</sup>

+ `@NEW_PRINT_JUEL`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/new_print_juel.md)</sup>

+ `@NEW_PRINT_MARK`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/new_print_mark.md)</sup>

+ `@NEW_PRINT_PUBICHAIR`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/new_print_pubichair.md)</sup>

+ `@NEW_PRINT_TALENT`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/new_print_talent.md)</sup>

+ `@NEW_PRINT_ZOKUSEI`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/new_print_zokusei.md)</sup>

+ `@NUM`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/num.md)</sup>

+ `@PRINT_COS`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_cos.md)</sup>

+ `@PRINT_COLORTEXT`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_colortext.md)</sup>

+ `@PRINT_EQUIPPING_ACCESSORY`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_equipping_accessory.md)</sup>

+ `@PRINT_INDICATE`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_indicate.md)</sup>

+ `@PRINT_MIDASHINAMI`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_midashinami.md)</sup>

+ `@PRINT_OTHER`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_other.md)</sup>

+ `@PRINT_STR`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_str.md)</sup>

+ `@PRINT_VIDEO`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_video.md)</sup>

+ `@PROFILE_TEXT`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/profile_text.md)</sup>

+ `@SET_MIDASHINAMI`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_midashinami.md)</sup>

+ `@SHOOT_RANKING`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/shoot_ranking.md)</sup>

+ `@SHOW_FAMILY`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/show_family.md)</sup>

+ `@STATE`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/state.md)</sup>

+ `@TEXTS`<sup>[说明文件](/Wiki/erasqn_wiki/function/t/texts.md)</sup>

### 函数实现

#### 参数

+ ARG

+ ARGS

#### 返回值

+ 传入的ARG为非法角色编号时，返回`0`

#### 功能实现

**L3-L5**：

声明变量`MEMO_LINECOUNT`、`MEMO_FLAG3`和`MEMO_REDRAW`

**L7-L9**：

用`MEMO_LINECOUNT`于记录到目前为止引擎显示过的行数

用`MEMO_FLAG3`记录`FLAG:3`（能力表示画面的项目开关标志）

将`CURRENTREDRAW()`的返回值记录到`MEMO_REDRAW`中<br/>（记录当前刷新帧率，如果当前帧率为`0`则只在玩家输入时刷新显示，如果帧率为`1`则按照引擎的设置帧率刷新）

**L13-L136**：

（因此选择支内容较多，所以下面会将说明拆分）

以`ARGS`作为选择支：

  + 当其值为`通常`、`通常：２`、`キャラメイク`或`ＬＶＵＰ`时：

**L16-L25**：

如果`ARG`小于`0`时：

  + 输出`ERROR：角色编号不能为负数`且返回`0`

否则如果`ARG`为`0`时：

  + 输出`ERROR：角色编号不存在`且返回`0`

否则如果`ARG`大于`CHARANUM - 1`时：

  + 输出`ERROR：角色编号超过总角色数`且返回`0`

**L27**：

输出`CALLNAME:ARG`（以参数传入的角色号的`CALLNAME`）

**L29-L36**：

如果`ARG`不等于`MASTER`时：

  + 当`CFLAG:ARG:209`不为`0`，<br/>且`CFLAG:ARG:209`不等于`1`，<br/>且`CFLAG:ARG:209`不等于`857`时：

    + 输出`口癖{CFLAG:ARG:209}`

  + 将`RESULT`置为`0`

  + 尝试调用`@IS_SINGLE_ENDING_K{NO:ARG}_{CFLAG:ARG:209}`

  + 当`RESULT`不为`0`时：

    + 调用`@PRINT_STR`以粉红色输出`有特殊ＥＮＤ`的提示

**L38-L44**：

如果`@STATE("悪酔い", ARG)`返回不为`0`：

  + 调用`@PRINT_COLORTEXT`以`青色`输出`烂醉如泥`

否则如果`@STATE("ドランク", ARG)`返回不为`0`

  + 调用`@PRINT_COLORTEXT`以`粉红色`输出`醉酒`

**L45-L58**：

以`ARG`作为选择支：

  + 当其值为`MASTER`时：

    + 输出`主人`

  + 当其值为`ASSI`时：

    + 以`ABL:ASSI:助手`作为选择支：

      + 当其值为`0`时：

        + 输出`见习%TEXTS("助手の名称")%`

      + 否则

        + 输出`LV{ABL:ASSI:助手}%TEXTS("助手の名称")%`

  + 当其值为`TARGET`时：

    + 当`EXP:ARG:调教次数`不为`0`时：

      + 输出`调教中`

**L62-L78**：

如果`ABL:ARG:ＬＶ`小于`@NUM("最大レベル", 90)`时：

  + 输出`ABL:ARG:ＬＶ`

  + 当`ARG`为`MASTER`，且`ABL:MASTER:ＬＶ`小于`FLAG:255`（等级限制器标志）时：

    + 输出`限制中`

  + 输出`EXP:ARG:经验值`

  + 将`LOCAL`置为`0`

  + 当`ARG`不为`MASTER`，且`ABL:ARG:ＬＶ`等于`14`，且角色为`TALENT:ARG:梦魔`时：

    + 将`LOCAL`置为`200`

  + 如果`@EXP_NEXTLV(ARG, ABL:ARG:ＬＶ)`的返回值加上`LOCAL`，再减去当前已有的经验值`EXP:ARG:经验值`的结果大于`0`时：

    + 输出距离下个等级还需要经验`EXP_NEXTLV(ARG, ABL:ARG:ＬＶ) + LOCAL - EXP:ARG:经验值`

  + 否则：

    + 调用`@PRINT_STR, "黄色_MAX!"`

    + 输出现有的经验值`EXP:ARG:经验值`

否则：

  + 调用`@PRINT_STR, "黄色_LVUPOK!"`

  + 输出现有的经验值`EXP:ARG:经验值`

**L80-L81**：

当`@COND("化蝶之梦", ARG)`的值大于`0`时：

  + 输出`%CALLNAME:COND("化蝶之梦", ARG)%的身体`（正在与谁交换身体）

**L85-L86**：

当角色处于下列的任意一种状态时：

  + `TALENT:ARG:怀孕`

  + `BASE:ARG:育儿中`

  + `@GETBITS(BASE:ARG:生理周期, 10, 20)`

  + `@COND("避妊中", ARG)`

  + `@COND("着床確認", ARG)`

输出特殊状态信息的`(`

**L87-L91**：

如果角色处于`BASE:ARG:育儿中`状态时：

  + 输出`正在养育%CONDS("胎儿的父亲", ARG)%的孩子`

  + 当角色处于`TALENT:ARG:怀孕`状态，或`@GETBITS(BASE:ARG:生理周期, 10, 20)`返回值不为`0`，或`@COND("避妊中", ARG)`返回值不为`0`时：

    + 输出*一个空格*？

**L92-L115**：

如果角色处于`TALENT:ARG:怀孕`状态：

  + 打印`正在怀着%CONDS("精液的优势", ARG)%的孩子`

否则如果角色处于`@COND("発情期", ARG)`状态：

  + 调用`@DEF_COLOR`将输出颜色设为`粉红色`

  + 输出`%CONDS("精液的优势", ARG)%的精子已着床`

  + 调用`@HEARTMARK`输出一个心型字符

否则如果角色处于`@COND("避妊中", ARG)`状态：

  + 如果角色装备了`TALENT:ARG:避孕护符`：

    + 输出`避孕护符`

  + 否则如果角色处于`TALENT:ARG:避孕药服用`状态：

    + 输出`避孕药服用中:药效剩余{TALENT:ARG:避孕药服用}日`

否则如果角色处于`@COND("安全日", ARG)`状态：

  + 输出`安全日`

否则如果角色处于`@COND("排卵中", ARG)`状态：

  + 调用`@DEF_COLOR`将输出颜色设为`粉红色`

  + 输出`危险日`

否则如果角色处于`@COND("危険日", ARG)`状态：

  + 调用`@DEF_COLOR`将输出颜色设为`黄色`

  + 输出`危险日`

**L116-L117**：

调用引擎命令重置输出颜色`RESETCOLOR`

以与*L85-L86*同样的条件，输出特殊状态信息的`)`

**L121-L122**：

当传入的参数`ARG`不为`MASTER`时：

  + 输出好感度`CFLAG:ARG:2`

**L124-L125**：

输出角色的最大`MAXBASE:ARG:体力`与最大`气力:{MAXBASE:ARG:气力}`

**L126-L127**：

当角色最大`MAXBASE:ARG:精力`不为`0`时：

  + 当`STOCK`为`0`时，直接打印最大`MAXBASE:ARG:精力`

  + 当`STOCK`不为`0`时，打印`MAXBASE:ARG:精力`×`MAXBASE:ARG:STOCK`

**L128-L129**：

当角色不为`TALENT:ARG:男性`时：

  + 打印`@COND("胎内の精液量", ARG)`子宫内精液量

**L132-L133**：

当传入的`ARG`不为`MASTER`，且`@COND("前回調教日", ARG)`返回值不为`0`，且`@COND("調教空白期間", ARG)`返回值大于或等于`2`时：

  + 输出上次调教日期`@COND("前回調教日", ARG)`和放置时间`@COND("調教空白期間", ARG)`

**L134-L136**：

（呼应*L13-L136*）

以`ARGS`作为选择支：

  + 当其值为`召喚`时：

    + 调用`PROFILE_TEXT, NO:ARG`，打印角色背景故事简介

**L139-L445**：

（因此选择支内容较多，所以下面会将说明拆分）

以`ARGS`作为选择支：

**L140-L145**：

当其值为`ＬＶＵＰ`时：

  + 调用`@NEW_PRINT_EXP, TARGET`，（作用不明，过后研究）

  + 当角色拥有`EXP:异常经验`时，调用`@NEW_PRINT_EXP50, TARGET`，（作用不明，过后研究）

  + 调用`@NEW_PRINT_JUEL, TARGET`，（作用不明，过后研究）

**L146-L231**：

当其值为`通常`时：<br/>（显示角色信息第一页）

  + 如果`ARG`值为`MASTER`时：<br/>（当显示的是MASTER的信息时）

    + 调用`@NEW_PRINT_3SIZE, ARG, "個別表示"`，显示角色三围

    + 调用`@NEW_PRINT_ZOKUSEI, ARG`，显示角色性癖

    + 调用`@NEW_PRINT_JUEL, ARG`，显示角色拥有的宝珠

    + 调用`@NEW_PRINT_EXP, ARG`，显示角色经验值

    + 调用`@NEW_PRINT_EXP50, ARG`，显示角色异常经验

    + 调用`@NEW_PRINT_ABL, ARG`，显示角色能力

    + 调用`@NEW_PRINT_MARK, ARG`，显示角色刻印

    + 调用`@NEW_PRINT_TALENT, ARG`，显示角色素质

    + 调用`@NEW_PRINT_PUBICHAIR, ARG`，显示角色的阴毛和腋毛的状态

    + 调用`@PRINT_EQUIPPING_ACCESSORY, ARG`，显示角色装备中的装饰品

    + 调用`@PRINT_MIDASHINAMI, ARG`，显示角色的仪容

    + 调用`@PRINT_COS, ARG`，显示角色的服装详情

    + 调用`@SHOW_FAMILY, ARG`，显示角色的家族构成

    + 调用`@PRINT_RELATION, ARG`，显示角色相性

    + 调用`@PRINT_OTHER, ARG`，显示角色榨精排行等信息

    + 输出菜单项目`仪表管理`

    + 如果`@NUM("所持アクセサリ")`角色持有的饰品数大于`0`

      + 输出可用的菜单项目`饰品装备`

    + 否则输出不可用的菜单项目`饰品装备`

    + 输出菜单项目`关闭`

    + 输出菜单项目`page2`

    + 输出不可用的菜单项目`主人`（目前显示的正是MASTER的信息）

    + 如果设定了调教目标`TAREGT`：

      + 输出菜单项目`调教对象`

    + 否则输出不可用的菜单项目`调教对象`

    + 如果设定了助手`ASSI`：

      + 输出菜单项目`%TEXTS("助手の名称")%`

    + 否则输出不可用菜单项目`%TEXTS("助手の名称")%`

    + 当`ARG`为`1`时，输出菜单项目`末位角色`，否则输出菜单项目`上一位角色`

    + 当`ARG`为`CHARANUM - 1`时，输出菜单项目`首位角色`，否则输出菜单项目`下一为角色`

    + 调用引擎命令`ONEINPUTS`读取玩家输入<br/>（此命令仅接受一个字符的输入，且当玩家输入后，会立即进行下一个动作）

    + 以玩家的输入`RESULTS`作为选择支：

      + 当其值位`1`、`3`或`4`时：

        + 调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`7`时：

        + 如果玩家持有的饰品数`@NUM("所持アクセサリ")`不为`0`：

          + 调用`@ACCESSORY_SELECT`进行饰品选择

        + 否则：

          + 调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`0`时：

        + 调用`@SET_MIDASHINAMI, MASTER`，为MASTER设置仪表

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`2`时：

        + 将`ARGS`设为`通常：２`（显示此角色的第二页信息）

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`5`时：

        + 当`ARG`不为`TARGET`，且选定了`TARGET`

          + 将`ARG`置为`TARGET`

          + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`6`时：

        + 当`ARG`不为`ASSI`，且选定了`ASSI`时：

          + 将`ARG`置为`ASSI`

          + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`8`时：

        + 如果`ARG`为`1`时：

          + 将`ARG`置为`CHARANUM - 1`

        + 否则：

          + `ARG`扣减`1`

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`9`时：

        + 如果`ARG`的值与`CHARANUM - 1`相等时：

          + 将`ARG`置为`1`

        + 否则：

          + `ARG`自增`1`

        + 调用引擎命令`RESTART`，重新从头执行本函数

**L232-L297**：

当其值为`通常`时：

  + 否则：<br/>（当显示的*不*为MASTER的信息时）

    + `@NEW_PRINT_3SIZE, ARG, "個別表示"`，显示角色三围

    + `@NEW_PRINT_ZOKUSEI, ARG`，显示角色性癖

    + `@NEW_PRINT_JUEL, ARG`，显示角色拥有的宝珠

    + `@NEW_PRINT_EXP, ARG`，显示角色经验值

    + `@NEW_PRINT_EXP50, ARG`，显示角色异常经验

    + `@NEW_PRINT_ABL, ARG`，显示角色能力

    + `@NEW_PRINT_MARK, ARG`，显示角色刻印

    + `@NEW_PRINT_TALENT, ARG`，显示角色素质

    + `@NEW_PRINT_PUBICHAIR, ARG`，显示角色的阴毛和腋毛的状态

    + `@PRINT_EQUIPPING_ACCESSORY, ARG`，显示角色装备中的装饰品

    + 输出菜单项目`关闭`

    + 输出菜单项目`page2`

    + 如果`ARG`不为`TARGET`，且选定了调教对象`TARGET`：

      + 输出菜单项目`调教对象`

    + 否则：

      + 输出不可用菜单项目`调教对象`

    + 如果`ARG`不为`ASSI`，且选定了助手`ASSI`：

      + 输出菜单项目`助手`

    + 否则：

      + 输出不可用菜单项目`助手`

    + 当`ARG`为`1`时，输出菜单项目`末位角色`，否则输出菜单项目`上一位角色`

    + 当`ARG`为`CHARANUM - 1`时，输出菜单项目`首位角色`，否则输出菜单项目`下一为角色`

    + 调用引擎命令`ONEINPUTS`读取玩家输入

    + 以玩家的输入`RESULTS`作为选择支：

      + 当其值为`0`、`1`、`3`或`7`时：

        + 调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`2`时：

        + 将`ARGS`的值置为`通常：２`

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`4`时：

        + 将`ARG`置为`MASTER`

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`5`时：

        + 当`ARG`的值不为`TARGET`，且选定了`TARGET`时：

          + 将`ARG`置为`TARGET`

          + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`6`时：

        + 当`ARG`的值不为`ASSI`，且选定了助手`ASSI`时：

          + 将`ARG`置为`ASSI`

          + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`8`时：

        + 如果`ARG`的值为`1`：

          + 将`ARG`的值置为`CHARANUM - 1`

        + 否则：

          + `ARG`扣减`1`

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`9`时：

        + 如果`ARG`的值置为`CHARANUM - 1`时：

          + 将`ARG`置为`1`

        + 否则：

          + `ARG`自增`1`

        + 调用引擎命令`RESTART`，重新从头执行本函数

**L298-L367**：

当其值为`通常：２`时：<br/>（显示角色信息第二页）

  + 如果`ARG`值为`MASTER`时：<br/>（当显示的是MASTER的信息时）

    + 调用`@SHOOT_RANKING, ARG`，显示射精排行

    + 输出菜单项目`仪表管理`

    + 如果角色持有的饰品数不为`0`：

      + 输出菜单项目`饰品装备`

    + 否则：

      + 输出不可用菜单项目`饰品装备`

    + 输出菜单项目`关闭`

    + 输出菜单项目`page1`（目前正在显示第二页）

    + 输出不可用菜单项目`主人`

    + 如果选定了`TARGET`：

      + 输出菜单项目`调教对象`

    + 否则：

      + 输出不可用菜单项目`调教对象`

    + 如果选定了助手`ASSI`：

      + 输出菜单项目`%TEXTS("助手の名称")%`

    + 否则：

      + 输出不可用菜单项目`%TEXTS("助手の名称")%`

    + 当`ARG`为`1`时，输出菜单项目`末位角色`，否则输出菜单项目`上一位角色`

    + 当`ARG`为`CHARANUM - 1`时，输出菜单项目`首位角色`，否则输出菜单项目`下一为角色`

    + 调用引擎命令`ONEINPUTS`读取玩家输入

    + 以玩家的输入`RESULTS`作为选择支：

      + 当其值为`2`、`3`或`4`时：

        + 调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`7`时：

        + 如果玩家持有的饰品数`NUM("所持アクセサリ")`不为`0`：

          + 调用`@ACCESSORY_SELECT`进行饰品选择

        + 调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`0`时：

        + 调用`@SET_MIDASHINAMI, MASTER`，为MASTER设置仪表

        + 调用引擎命令`RESTART`，重新从头执行本函数

      + 当其值为`1`时：

        +

========================

调用引擎命令`CLEARLINE`删除`LINECOUNT - MEMO_LINECOUNT`行已显示的内容

调用引擎命令`RESTART`，重新从头执行本函数
