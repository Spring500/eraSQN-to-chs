# @USERSHOP

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 在主菜单做出选择后，跳转到对应功能的函数

### 所在文件

+ [Shop.erb](/ERB/SHOP/Shop.erb#L570-L896)

### 调用关系

**被调用**：

+ 在主菜单`@SHOW_SHOP`执行后，被游戏引擎调用

**调用**：

+ `@ACCESSORY_SHOP`<sup>[说明文件](.)</sup>

+ `@ANALYSIS`<sup>[说明文件](.)</sup>

+ `@ARCANA_SHOP`<sup>[说明文件](.)</sup>

+ `@CHANGE_TARGET`<sup>[说明文件](.)</sup>

+ `@CHARA_BUY`<sup>[说明文件](.)</sup>

+ `@CHARA_NUM`<sup>[说明文件](.)</sup>

+ `@CHARA_SALE`<sup>[说明文件](.)</sup>

+ `@CHECK_COM_ABLE`<sup>[说明文件](.)</sup>

+ `@CHECK_SINGLE_ENDING`<sup>[说明文件](.)</sup>

+ `@COMPOUND_ITEM`<sup>[说明文件](.)</sup>

+ `@COND`<sup>[说明文件](.)</sup>

+ `@CONFIG`<sup>[说明文件](.)</sup>

+ `@COSPLAY_LIST`<sup>[说明文件](.)</sup>

+ `@DEBUG_MODE`<sup>[说明文件](.)</sup>

+ `@EAT_LUNCH`<sup>[说明文件](.)</sup>

+ `@ENDING_CHECK`<sup>[说明文件](.)</sup>

+ `@EVENT_DESKWORK`<sup>[说明文件](.)</sup>

+ `@EVENT_KOTYOUNOYUME`<sup>[说明文件](.)</sup>

+ `@EVENT_RANKOU_SET`<sup>[说明文件](.)</sup>

+ `@EVENT_RANKOU`<sup>[说明文件](.)</sup>

+ `@EVENT_REST_PRE`<sup>[说明文件](.)</sup>

+ `@EVENT_SHOP`<sup>[说明文件](.)</sup>

+ `@EVENT_TRAVEL_SELECT`<sup>[说明文件](.)</sup>

+ `@EXPLORER`<sup>[说明文件](.)</sup>

+ `@GIVE_NAME`<sup>[说明文件](.)</sup>

+ `@GUEST_KOJO_K{NO:TARGET}_{CFLAG:209}`<sup>[说明文件](.)</sup>

+ `@INPUT_SELECT`<sup>[说明文件](.)</sup>

+ `@LOADGAME_EX`<sup>[说明文件](.)</sup>

+ `@LV_LIMITTER`<sup>[说明文件](.)</sup>

+ `@NAME_CONVERT`<sup>[说明文件](.)</sup>

+ `@NUM`<sup>[说明文件](.)</sup>

+ `@PLAY_WITH_ASSI`<sup>[说明文件](.)</sup>

+ `@PRINT_STR`<sup>[说明文件](.)</sup>

+ `@SAVEGAME_EX`<sup>[说明文件](.)</sup>

+ `@SELECT_ASSI`<sup>[说明文件](.)</sup>

+ `@SETFLAG`<sup>[说明文件](.)</sup>

+ `@SET_3SIZE`<sup>[说明文件](.)</sup>

+ `@SET_CHARA_LOVE`<sup>[说明文件](.)</sup>

+ `@SET_CHARA_NIGHTWALKER`<sup>[说明文件](.)</sup>

+ `@SET_CONFIGURE`<sup>[说明文件](.)</sup>

+ `@SHOP_EX`<sup>[说明文件](.)</sup>

+ `@SHOW_CHARADATA`<sup>[说明文件](.)</sup>

+ `@SHOW_ITEM_HAVE`<sup>[说明文件](.)</sup>

+ `@TEXTS`<sup>[说明文件](.)</sup>

+ `@USERSHOP_SEXUHARA`<sup>[说明文件](.)</sup>
﻿
+ `funcname3`<sup>[文档](https://osdn.net/projects/emuera/wiki/FrontPage)</sup>

### 函数实现

#### 参数

+ 无参数传入

#### 返回值

返回：`0`

#### 功能实现

L571-L573：定义三个变量，分别是`CHOICE`，`MEMO_TARGET`和`MEMO_ASSI`

L575-L576：将用户上一步的输入记录在`CHOICE`和`TFLAG:102`中

L578-L579：调用`@USERSHOP_SEXUHARA`，传入参数`CHOICE`（作用不明，过后研究）

L582-L589：如果用户输入的是`100`，且`TARGET`不为0（有选中调教对象），则使用引擎内置命令`BEGIN TRAIN`开始调教，并返回`1`。如果没有选定调教对象则打印相应的提示

L591-L596：如果用户输入的是`101`，且用`CONFIG("調教相手変更不可")`查询`FLAG:252`，如果`FLAG:252`不为`0`则`FLAG:253 = 1`。然后调用`SHOW_CHARADATA, 0, 0`

L598-L610：如果用户输入的是`102`，当没有选择调教对象且`CONFIG("調教相手変更不可") == 0`，就将`FLAG:0`置为`1`，然后尝试调用`EVENT_REST_PRE`（`TRYCALL`在调用的函数不存在试也不会报错），当`EVENT_REST_PRE`执行完成后，接着执行引擎指令`BEGIN TURNEND`（简单看了一下，当指令`BEGIN TURNEND`被执行时，引擎会自动调用`@EVENTTURNEND`，这个函数是负责梦魔化相关的功能的），最后返回`1`。当只是`CONFIG("調教相手変更不可")`为`1`时，打印`现在还不可以休息`。当没有选择对手时打印`目前没有指定对手`。

L614-L625：如果用户输入的是`108`，当设置了助手且`CONFIG("調教相手変更不可")`调教助手也可变更（为`0`），就用`LOCAL`暂存助手的角色编号，然后将助手置为`0`。接着判断调教对象是不是可以成为助手（`COND("助手可能")`会查询`GETBIT(CFLAG:ARG:1, 1)`，如果该FLAG=1则代表角色可以被出售，=2则代表可以成为助手），如果可以成为助手，就将`ASSI = TARGET`当前的对象设为助手。然后再将暂存的`LOCAL`复制给`ASSI`。完成助手与对象的更换。当设置了助手且调教对象不可变更时提示`无法交换`。当没有设置助手时提示`没有指定助手`。

L627-L643：如果用户输入的是`109`，开始先用`MEMO_ASSI`记录当前的助手编号。如果`CHARA_NUM("助手可能") && CONFIG("調教相手変更不可") == 0`（这句出现好几次了，说明参考上面），就将`FLAG:253`置为`1`。然后调用`CALL SELECT_ASSI, 0, 0`函数选择助手。如果`CONFIG("調教相手変更不可")`，则打印`助手不可变更`。如果`CHARA_NUM("助手可能")`返回`0`，则说明目前没有可以作为助手的角色，打印对应的提示。
如果`ASSI && ASSI != MEMO_ASSI`，就`TRYCALLFORM GUEST_KOJO_K{NO:ASSI}_{CFLAG:ASSI:209}, "助手に抜擢", ASSI`（此函数作用需要后续确认），当助手角色为`0`时，助手角色`+=1`。

L645-L655：如果用户输入的是`110`，开始先用`MEMO_TARGET`记录当前调教对象的编号。如果可替换角色&&助手变更不可==0，就将`FLAG:253`（对象和助手是否可以变更）置为`1`，然后调用`CHANGE_TARGET, 0, 0`。

> L654-L655看不太懂逻辑，回头解释。根据注释的说明：如果曾经的调教对像与现在的对象不同，就`TRYCALLFORM GUEST_KOJO_K{NO:TARGET}_{CFLAG:209}, "調教相手に選ばれた", TARGET`

> `SIF TARGET && TARGET != MEMO_TARGET && EXP:调教次数`

> 其中`TARGET && TARGET`必定为`1`，因为同一时刻调教对象号码只能有一个，然后`MEMO_TARGET && EXP:调教次数`代表的是上次调教的角色编号和该角色的被调教次数。

> 综合理解就是当上次调教角色的编号不等于上次调教角色的调教次数时，就`TRYCALLFORM GUEST_KOJO_K{NO:TARGET}_{CFLAG:209}, "調教相手に選ばれた", TARGET`

L657-L664：如果用户输入的是`111`，当`CHARANUM`小于100且调教助手可变更，就调用`CHARA_BUY`。如果助手不可变更，这提示`现在不是召唤的时候`。如果`CHARANUM>=100`，则提示`角色已满`。
