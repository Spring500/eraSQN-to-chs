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


L666-L684：如果用户输入的是`112`，就先检查`CHARA_NUM("売却可能")`和`CONFIG("調教相手変更不可")`。如果两者相与为`0`。则将`MONEY:1`（目前调教过角色的最高价）和`MONEY:3`（目前调教角色的最高评价）都重设为`0`。然后遍历所有除玩家外的角色，在角色上找出上述两个值的最大值，并覆盖到`MONEY:1`以及`MONEY:3`中。最后再用`MONEY:2`（调教过的角色的最高价格）储存`MNOEY:1`和`MONEY:2`两值的最大值；用`MONEY:4`（调教过的角色的最高评价）储存`MNOEY:3`和`MONEY:4`两值的最大值。然后调用`@CHARA_SALE`。如果处于调教对象不可变更的状态，则提示`现在不是卖出的时候`。如果可以出售的角色为`0`，则提示`没有可以出售的梦魔`。

L686-L690：如果用户输入的是`113`。当角色总数大于`2`时，就调用`@COSPLAY_LIST`。

L692-L693：如果用户输入的是`114`。就调用`@EVENT_SHOP`。

L695-L700：如果用户输入的是`115`。就判断`NUM("総衣装数")`是否大于`NUM("所持衣装")`。如果衣装总数比较大，就调用`@COSPLAY_SHOP`，否则打印`已卖完`的消息。

L702-L703：如果用户输入的是`116`。就调用`@ARCANA_SHOP`

L704-L705：如果用户输入的是`117`。就调用`@ACCESSORY_SHOP`

L705-L713：如果用户输入的是`118`。就先检查`FLAG:40`(食品代码，推测吃东西后会被更新)是否为`0`，如果为`0`则调用`@EAT_LUNCH`，否则打印`已吃不下`。

L715-L728：如果用户输入的是`120`。就先检查`CHARA_NUM("一晩開放可能")`，当可以允许外出的角色数不为`0`时，就调用`@SET_CHARA_NIGHTWALKER`。否则，显示出何种条件的角色才能外出。

L730-L732：如果用户输入的是`121`。就调用`@EXPLORER`

L734-L739：如果用户输入的是`122`。就检查MASTER或ASSI是否具有`TALENT:调合知识`，如果有就调用`@COMPOUND_ITEM`，否则打印出条件提示。

L741-L751：如果用户输入的是`123`。就检查`CHARA_NUM("書類仕事")`，当大于`0`时，再查看`FLAG:12`是否为`0`，如果为`0`则代表可以进行文书工作，就调用`@EVENT_DESKWORK`，否则就打印`工作以完成`。如果`CHARA_NUM("書類仕事")`为`0`，就提示没有可进行文书工作的角色。

L753-L760：如果用户输入的是`124`。就检查是否有指定助手和调教是否可以变更，如果设定了助手且调教对像可变更，就`TRYCALL PLAY_WITH_ASSI`。如果设置了对象且调教对象不可变更，就输出提示`不想搭理助手`。如果没有设置助手，就输出提示`还没指定助手`

L762-L769：如果用户输入的是`125`。就检查是否设置了调教对象以及用`COND("温泉旅行可能")`确认是否可以预约温泉旅行，如果可以则调用`@EVENT_TRAVEL_SELECT`，否则输出温泉旅行的相关条件提示。

L771-L782：如果用户输入的是`131`。则先检查`FLAG:208`（偏爱再设定剩余天数）是否为`0`，若不为`0`则打印提示再过n天才可以重新设定偏爱。若为`0`，就先用`TFALG:0`记录MASTER当前的弱点，用`TFLAG:1`记录当前MASTER的性癖。然后遍历所有非MASTER角色，用`TFLAG:角色编号`来记录该角色是否被设置了偏爱。最后调用`@SET_CHARA_LOVE`

L784-L787：如果用户输入的是`140`。当`NUM("所持アイテム")`和`NUM("所持衣装")`的和大于`0`时，调用`@SHOW_ITEM_HAVE`

L789-L792：如果用户输入的是`141`。当`NUM("売却可能アイテム")`大于`0`时，调用`@SELL_ITEM`

L794-L799：（这个功能被原开发者关闭了，感觉重新打开问题也不大）如果用户输入的是`142`。当选定了调教对象时，调用`@ANALYSIS`，否则提示`请将要分析的角色设为调教对象。`

L801-L809：如果用户输入的是`160`。如果`NUM("運営可能店舗")`或`NUM("所持店舗")`其中之一不为`0`，就调用`@SHOP_EX`。否则就打印咖啡店的开张条件文本提示。

L810-L811：如果用户输入的是`200`。就调用`@SAVEGAME_EX`。

L812-L813：如果用户输入的是`300`。就调用`@LOADGAME_EX`。

L815-L822：如果用户输入的是`330`，且`ITEM:化蝶之梦`的值为`100`，就打印化蝶之梦已达尾声，让用户选择是否醒来。如果选择醒来，就调用`@EVENT_KOTYOUNOYUME, "夢の終わり"`。

L823-L824：如果用户输入的是`333`，且拥有`ITEM:等级限制器`，就调用`@LV_LIMITTER`。

L825-L826：如果用户输入的是`555`，则调用`@SET_CONFIGURE`，进行系统设定。

L827-L849：如果用户输入的是`600`。先检查`COND("エンディング選択可能")`是否可以进入ENDING。当金钱不达`NUM("目標金額")`金额时，输出提示`仍未达标`。或用`CALCF("最愛の相手")`查找并返回带有恋慕或相思相爱的角色，如果存在满足条件的角色，就输出提示`MASTER最爱的对象是XXX`，然后调用`@CHECK_SINGLE_ENDING`检查是否有特殊END，如果有就输出提示`有特殊END`。最后询问用户是否真的要迎接ENDING，如果用户不迎接，则返回`0`，否则调用`@ENDING_CHECK`。

L850-L853：如果用户输入的是`650`，且`NUM("ＥＮＤ閲覧済")`不为`0`，就用`MEMO_TARGET`记录当前的调教对象，然后调用`@SHOW_CHARA_END`，等该函数执行完毕后，再将`TARGET`重置为`MEMO_TARGET`。

L854-L855：如果用户输入的是`700`，且设置了对象，且`COND("子孫")`角色的CHARA\*\*.CSV`番号,**`为`95`或`97`且，对象姓名为`娘`或`息子`，就调用`@GIVE_NAME`。

L858-L869：如果用户输入的是`666`，且角色总数小于100。如果处于调教对手可变更状态，就将`FLAG:666`设为`1`，然后如果`CONFIG("召喚事故") 即 FLAG:221`为`0`时，就将`FLAG:221`设为`1`然后调用`@CHARA_BUY`，等`@CHARA_BUY`执行结束后，再将`FLAG:221`重置为`0`；否则，直接调用`@CHARA_BUY`。最后将`FLAG:666`置为`0`。

L870-L871：如果用户输入的是`777`。则调用`@NAME_CONVERT`（角色改名功能，与系统设置里面的项目重复）

L872-L881：如果用户输入的是`888`。当没有选择调教目标时，就返回`0`（余下的行数意义不明，需要日后解读）

L822-L892：如果用户输入的是`88224646`。则先用`MEMO_TARGET`记录下目前的调教对象。然后如果`TARGET`小于或等于`0`，就将`TARGET`设为`1`。接着调用`@DEBUG_MODE`。`@DEBUG_MODE`执行结束后，将`TARGET`重置为`MEMO_TARGET`记录的值，然后遍历所有角色，为每一个角色都调用一次`@SET_3SIZE`（意义不明，留着后面分析）
