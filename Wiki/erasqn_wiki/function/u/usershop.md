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

+ `@ACCESSORY_SHOP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/accessory_shop.md)</sup>

+ `@ANALYSIS`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/analysis.md)</sup>

+ `@ARCANA_SHOP`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/arcana_shop.md)</sup>

+ `@CHANGE_TARGET`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/change_target.md)</sup>

+ `@CHARA_BUY`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/chara_buy.md)</sup>

+ `@CHARA_NUM`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/chara_num.md)</sup>

+ `@CHARA_SALE`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/chara_sale.md)</sup>

+ `@CHECK_COM_ABLE`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/check_com_able.md)</sup>

+ `@CHECK_FLAG_MUMA`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/check_flag_muma.md)</sup>

+ `@CHECK_SINGLE_ENDING`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/check_single_ending.md)</sup>

+ `@COMPOUND_ITEM`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/compound_item.md)</sup>

+ `@COND`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/cond.md)</sup>

+ `@CONFIG`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/config.md)</sup>

+ `@COSPLAY_LIST`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/cosplay_list.md)</sup>

+ `@DEBUG_MODE`<sup>[说明文件](/Wiki/erasqn_wiki/function/d/debug_mode.md)</sup>

+ `@EAT_LUNCH`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/eat_lunch.md)</sup>

+ `@ENDING_CHECK`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/ending_check.md)</sup>

+ `@EVENT_DESKWORK`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/event_deskwork.md)</sup>

+ `@EVENT_KOTYOUNOYUME`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/event_kotyounoyume.md)</sup>

+ `@EVENT_RANKOU_SET`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/event_rankou_set.md)</sup>

+ `@EVENT_RANKOU`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/event_rankou.md)</sup>

+ `@EVENT_REST_PRE`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/event_rest_pre.md)</sup>

+ `@EVENT_SHOP`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/event_shop.md)</sup>

+ `@EVENT_TRAVEL_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/event_travel_select.md)</sup>

+ `@EXPLORER`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/explorer.md)</sup>

+ `@GIVE_NAME`<sup>[说明文件](/Wiki/erasqn_wiki/function/g/give_name.md)</sup>

+ `@GUEST_KOJO_K{NO:TARGET}_{CFLAG:209}`<sup>[说明文件](/Wiki/erasqn_wiki/function/README.md#其他函数)</sup>

+ `@INPUT_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/i/input_select.md)</sup>

+ `@LOADGAME_EX`<sup>[说明文件](/Wiki/erasqn_wiki/function/l/loadgame_ex.md)</sup>

+ `@LV_LIMITTER`<sup>[说明文件](/Wiki/erasqn_wiki/function/l/lv_limitter.md)</sup>

+ `@NAME_CONVERT`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/name_convert.md)</sup>

+ `@NUM`<sup>[说明文件](/Wiki/erasqn_wiki/function/n/num.md)</sup>

+ `@PLAY_WITH_ASSI`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/play_with_assi.md)</sup>

+ `@PRINT_STR`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_str.md)</sup>

+ `@SAVEGAME_EX`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/savegame_ex.md)</sup>

+ `@SELECT_ASSI`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/select_assi.md)</sup>

+ `@SETFLAG`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/setflag.md)</sup>

+ `@SET_3SIZE`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_3size.md)</sup>

+ `@SET_CHARA_LOVE`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_chara_love.md)</sup>

+ `@SET_CHARA_NIGHTWALKER`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_chara_nightwalker.md)</sup>

+ `@SET_CONFIGURE`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_configure.md)</sup>

+ `@SHOP_EX`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/shop_ex.md)</sup>

+ `@SHOW_CHARADATA`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/show_charadata.md)</sup>

+ `@SHOW_ITEM_HAVE`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/show_item_have.md)</sup>

+ `@TEXTS`<sup>[说明文件](/Wiki/erasqn_wiki/function/t/texts.md)</sup>

+ `@USERSHOP_SEXUHARA`<sup>[说明文件](/Wiki/erasqn_wiki/function/u/usershop_sexuhara.md)</sup>

### 函数实现

#### 参数

+ 无参数传入

#### 返回值

返回：`0`

#### 功能实现

**L571-L573**：

定义三个变量，分别是`CHOICE`，`MEMO_TARGET`和`MEMO_ASSI`，作为暂存用。

**L575-L576**：

将玩家上一步的输入记录在`CHOICE`和`TFLAG:102`中

**L578-L579**：

如果`GETBIT(FLAG:23, 10)`值为`1`，

就调用`@USERSHOP_SEXUHARA CHOICE`（作用不明，过后研究，`FLAG:23`的说明看不懂）。

**L582-L589**：

如果玩家在`@SHOW_SHOP`中输入的是`100`，

且`TARGET`不为`0`（有选中调教对象），则使用引擎内置命令`BEGIN TRAIN`开始调教，TRAIN结束后返回`1`。

如果没有选定调教对象则打印提示`未选对象`。

**L591-L596**：

如果玩家在`@SHOW_SHOP`中输入的是`101`，

且`CONFIG("調教相手変更不可")`查询`FLAG:252`，不为`0`，则将`FLAG:253`（对象和助手是否可变更）置为`1`。然后调用`SHOW_CHARADATA, 0, 0`。

**L598-L610**：

如果玩家在`@SHOW_SHOP`中输入的是`102`，

当选择了调教对象且`CONFIG("調教相手変更不可")`调教对象可变更时，就将`FLAG:0`置为`1`，然后尝试调用`EVENT_REST_PRE`（`TRYCALL`在调用的函数不存在试也不会报错）。

当`EVENT_REST_PRE`执行完成后，接着执行引擎指令`BEGIN TURNEND`（当指令`BEGIN TURNEND`被执行时，引擎会自动调用`@EVENTTURNEND`，这个函数是负责梦魔化相关的功能的），最后返回`1`。

当`CONFIG("調教相手変更不可")`调教对象不可变更时，打印`现在还不可以休息`。

当没有选定调教对象时打印`目前没有选定调教对象`。

> [尝试调用]是指用`TRYCALL`系命令调用函数，用此系列的命令调用函数的话，即使目标函数不存在，也不会抛出异常导致当前正在运行的过程意外中止，下同。

**L614-L625**：

如果玩家在`@SHOW_SHOP`中输入的是`108`，

当选定了助手且`CONFIG("調教相手変更不可")`调教助手也可变更时，就用`LOCAL`暂存助手的角色编号，然后将助手置为`0`。接着判断调教对象是不是可以成为助手，如果可以成为助手，就将`ASSI = TARGET`当前的对象设为助手。

> `COND("助手可能")`会查询`GETBIT(CFLAG:ARG:1, 1)`，如果该FLAG值为1，则代表角色可以被*出售*，值为2则代表可以*成为助手*

然后再将暂存的`LOCAL`复制给`ASSI`。完成助手与对象的更换。

当设置了助手且`CONFIG("調教相手変更不可")`调教对象不可变更时提示`无法交换`。

当没有设置助手时提示`没有指定助手`。

**L627-L643**：

如果玩家在`@SHOW_SHOP`中输入的是`109`，

开始先用`MEMO_ASSI`记录当前的助手编号。

如果`CHARA_NUM("助手可能")`大于`0`且`CONFIG("調教相手変更不可")`调教对象可变更时，就将`FLAG:253`（调教对象和助手可以变更）置为`1`。

然后调用`CALL SELECT_ASSI, 0, 0`函数选择助手。

如果`CONFIG("調教相手変更不可")`，则打印`助手不可变更`。

如果`CHARA_NUM("助手可能")`返回`0`，则说明目前没有可以作为助手的角色，打印对应的提示。

先测算`(ASSI != MEMO_ASSI)`，然后再将其布尔值结果与`ASSI`相与，如果结果大于`0`，就尝试调用`@GUEST_KOJO_K{NO:ASSI}_{CFLAG:ASSI:209}, "助手に抜擢", ASSI`（此函数作用需要后续确认）。然后，如果当前助手的助手经验为`0`，就为其加上`1`点助手经验。

> 这段布尔运算一开始没看懂。（L654也是一样）
> 因为原本程序是`ASSI && ASSI != MEMO_ASSI`。我一开始理解是从左到右运算的，将`&&`和`!=`的优先级当成一样的了。
> 其实这是错误的。后来灵光一闪，感觉应该是运算符优先度问题。
> 于是立即查阅[文档](/Wiki/emuera_wiki/eramaker_base_dev_info/exop.md#暫定的な演算子の優先度表)，随后发现`!=`的优先度其实比`&&`高，所以是语句后面的部分先运算。
> 实际上应该理解为`ASSI && (ASSI != MEMO_ASSI)`，然后再看代码就解释得通了。
> 为不再造成误解，已经在代码中后面的部分加上了圆括号。

**L645-L655**：

如果玩家在`@SHOW_SHOP`中输入的是`110`，

开始先用`MEMO_TARGET`暂存当前调教对象的编号。

如果`CHARA_NUM("控えキャラ")`可替换角色大于`0`且`CONFIG("調教相手変更不可")`可以更换调教对象，就将`FLAG:253`（对象和助手是否可以变更）置为`1`，然后调用`CHANGE_TARGET, 0, 0`选择新的调教对象。

如果选定了新的调教对象，且此对象跟`MEMO_TARGET`所记录的前一个调教对象不同，且当前调教对象的`EXP:调教次数`大于`0`时，就尝试调用`@GUEST_KOJO_K{NO:TARGET}_{CFLAG:209}, "調教相手に選ばれた", TARGET`（此函数作用需要后续确认）。

**L657-L664**：

如果玩家在`@SHOW_SHOP`中输入的是`111`，

当`CHARANUM`小于`100`且`CONFIG("調教相手変更不可")`调教助手可变更，就调用`CHARA_BUY`。

当`CONFIG("調教相手変更不可")`助手不可变更，就提示`现在不是召唤的时候`。

当`CHARANUM>=100`，则提示`角色已满`。

**L666-L684**：

如果玩家在`@SHOW_SHOP`中输入的是`112`，

当`CHARA_NUM("売却可能")`大于`0`且`CONFIG("調教相手変更不可")`调教对象可变更时，则将`MONEY:1`（目前调教过角色的最高价）和`MONEY:3`（目前调教角色的最高评价）都重设为`0`。

然后遍历所有除玩家以外的角色，在角色上找出上述两个值的最大值，并覆盖到`MONEY:1`以及`MONEY:3`中。

最后，将`MNOEY:1`和`MONEY:2`两值的最大值存到`MONEY:2`（调教过的角色的最高价格），

将`MNOEY:3`和`MONEY:4`两值的最大值储存到`MONEY:4`（调教过的角色的最高评价）。

如果处于`CONFIG("調教相手変更不可")`调教对象不可变更的状态，则提示`现在不是卖出的时候`。

如果`CHARA_NUM("売却可能")`可以出售的角色为`0`，则提示`没有可以出售的梦魔`。

**L686-L690**：

如果玩家在`@SHOW_SHOP`中输入的是`113`。

当`CHARANUM`角色总数大于`2`时，就调用`@COSPLAY_LIST, 0, 0`。

**L692-L693**：

如果玩家在`@SHOW_SHOP`中输入的是`114`。

就调用`@EVENT_SHOP`。

**L695-L700**：

如果玩家在`@SHOW_SHOP`中输入的是`115`。

当`NUM("総衣装数")`游戏内所有衣装的总数大于`NUM("所持衣装")`玩家持有的衣装数时，就调用`@COSPLAY_SHOP`，否则打印`已卖完`的消息。

**L702-L703**：

如果玩家在`@SHOW_SHOP`中输入的是`116`。

就调用`@ARCANA_SHOP`。

**L704-L705**：

如果玩家在`@SHOW_SHOP`中输入的是`117`。

就调用`@ACCESSORY_SHOP`。

**L705-L713**：

如果玩家在`@SHOW_SHOP`中输入的是`118`。

当`FLAG:40`(食品代码，推测吃东西后会被更新)为`0`时，就调用`@EAT_LUNCH`，否则打印`已吃不下`。

**L715-L728**：

如果玩家在`@SHOW_SHOP`中输入的是`120`。

当`CHARA_NUM("一晩開放可能")`可以开放深夜偷吃的角色数大于`0`时，就调用`@SET_CHARA_NIGHTWALKER, 0, 0`。

否则，显示出满足何种条件的角色才能外出。

**L730-L732**：

如果玩家在`@SHOW_SHOP`中输入的是`121`。

就调用`@EXPLORER, 0, 0`

**L734-L739**：

如果玩家在`@SHOW_SHOP`中输入的是`122`。

就检查MASTER或ASSI是否具有`TALENT:调合知识`，如果有就调用`@COMPOUND_ITEM`.

否则，打印出调合道具所需要的条件提示。

**L741-L751**：

如果玩家在`@SHOW_SHOP`中输入的是`123`。

当`CHARA_NUM("書類仕事")`，不为`0`时：

  + 当`FLAG:12`（MASTER有文书工作）为`0`时，调用`@EVENT_DESKWORK`。

  + 否则，就打印`工作已完成`。

当`CHARA_NUM("書類仕事")`为`0`时，就提示没有可进行文书工作的角色。

**L753-L760**：

如果玩家在`@SHOW_SHOP`中输入的是`124`。

当指定了助手`ASSI`且`CONFIG("調教相手変更不可")`调教对象**可变更**时，尝试调用`@PLAY_WITH_ASSI`。

当指定了助手`ASSI`且`CONFIG("調教相手変更不可")`调教对象**不可变更**时，就打印`不想搭理助手`。

当没有指定助手`ASSI`时，就打印`还没指定助手`。

**L762-L769**：

如果玩家在`@SHOW_SHOP`中输入的是`125`。

当指定了调教对象`TARGET`其`COND("温泉旅行可能")`可以预约温泉旅行时，尝试调用`@EVENT_TRAVEL_SELECT`。

否则，输出温泉旅行的相关条件提示。

**L771-L782**：

如果玩家在`@SHOW_SHOP`中输入的是`131`。

先检查`FLAG:208`偏爱再设定剩余天数是否为`0`，若不为`0`则打印提示再过n天才可以重新设定偏爱。

若为`0`，就先用`TFALG:0`记录MASTER当前的弱点，用`TFLAG:1`记录当前MASTER的性癖。

然后遍历所有非MASTER角色，用`TFLAG:角色编号`来记录该角色是否被设置了偏爱。最后调用`@SET_CHARA_LOVE, 0, 0`

**L784-L787**：

如果玩家在`@SHOW_SHOP`中输入的是`140`。

当`NUM("所持アイテム")`所持物品数和`NUM("所持衣装")`所持衣装数的和大于`0`时，调用`@SHOW_ITEM_HAVE`。

**L789-L792**：

如果玩家在`@SHOW_SHOP`中输入的是`141`。

当`NUM("売却可能アイテム")`可以出售的物品数大于`0`时，调用`@SELL_ITEM`。

**L794-L799**：

（这个功能被原开发者关闭了，感觉重新打开问题也不大）

如果玩家在`@SHOW_SHOP`中输入的是`142`。

当选定了调教对象`TARGET`时，就调用`@ANALYSIS`。

否则提示`请将要分析的角色设为调教对象`。

**L801-L809**：

如果玩家在`@SHOW_SHOP`中输入的是`160`。

当`NUM("運営可能店舗")`可以运营店铺或`NUM("所持店舗")`持有店铺数其中之一不为`0`时，就调用`@SHOP_EX`。

否则就打印咖啡店的开张条件文本提示。

**L810-L811**：

如果玩家在`@SHOW_SHOP`中输入的是`200`。

就调用`@SAVEGAME_EX`。

**L812-L813**：

如果玩家在`@SHOW_SHOP`中输入的是`300`。

就调用`@LOADGAME_EX`。

**L815-L822**：

如果玩家在`@SHOW_SHOP`中输入的是`330`，

且`ITEM:化蝶之梦`的值为`100`时，就打印`化蝶之梦已达尾声`，让玩家选择是否醒来。

如果选择醒来，就调用`@EVENT_KOTYOUNOYUME, "夢の終わり"`。

**L823-L824**：

如果玩家在`@SHOW_SHOP`中输入的是`333`，

且拥有`ITEM:等级限制器`，就调用`@LV_LIMITTER`。

**L825-L826**：

如果玩家在`@SHOW_SHOP`中输入的是`555`，

则调用`@SET_CONFIGURE`，进行系统设定。

**L827-L849**：

如果玩家在`@SHOW_SHOP`中输入的是`600`。

检查`COND("エンディング選択可能")`是否可以进入ENDING。

如果可以进入ENDING：

+ 当所持金钱`MONEY`不达`NUM("目標金額")`目标金额时，输出提示`仍未达标`。

+ 当存在`CALCF("最愛の相手")`恋慕或相思相爱角色时，就输出提示`MASTER最爱的对象是XXX`，然后调用`@CHECK_SINGLE_ENDING`检查是否有特殊END，如果有就输出提示`有特殊END`。

最后询问玩家是否真的要迎接ENDING，如果玩家选择不迎接，则返回`0`，否则调用`@ENDING_CHECK`。

**L850-L853**：

如果玩家在`@SHOW_SHOP`中输入的是`650`，

且`NUM("ＥＮＤ閲覧済")`不为`0`，就用`MEMO_TARGET`记录当前的调教对象，然后调用`@SHOW_CHARA_END`，等该函数执行完毕后，再将`TARGET`重置为`MEMO_TARGET`。

**L854-L855**：

如果玩家在`@SHOW_SHOP`中输入的是`700`，

且选定了调教对象`TARGET`，且`COND("子孫")`该角色的CHARA\*\*.CSV`番号,**`为`95`或`97`且，对象姓名为`娘`或`息子`，就调用`@GIVE_NAME`。

**L858-L869**：

如果玩家在`@SHOW_SHOP`中输入的是`666`，

且角色总数`CHARANUM`小于`100`。

如果处于调教对手可变更状态，就将`FLAG:666`设为`1`：

  + 如果`CONFIG("召喚事故") 即 FLAG:221`为`0`时，就将`FLAG:221`设为`1`然后调用`@CHARA_BUY`，等`@CHARA_BUY`执行结束后，再将`FLAG:221`重置为`0`

  + 否则，直接调用`@CHARA_BUY`。

最后将`FLAG:666`重置为`0`。

**L870-L871**：如果玩家在`@SHOW_SHOP`中输入的是`777`，

则调用`@NAME_CONVERT`（角色改名功能，与系统设置里面的项目重复，且无直接对应的菜单项目）。

**L872-L881**：

如果玩家在`@SHOW_SHOP`中输入的是`888`。

当没有选择调教目标时，就返回`0`。

（余下的几行作用不明，过后研究，但似乎可以触发乱交事件）

```
CALL CHECK_COM_ABLE, TARGET
CALL EVENT_RANKOU_SET, "夜這い乱交"
IF CSTR:夜袭 != ""
	CSTR:乱交 = %CSTR:夜袭%
	CALL EVENT_RANKOU, "夜這い乱交"
ENDIF
```

**L822-L892**：

如果玩家在`@SHOW_SHOP`中输入的是`88224646`。

则先用`MEMO_TARGET`记录下目前的调教对象。

然后如果`TARGET`小于或等于`0`，就将`TARGET`设为`1`。

接着调用`@DEBUG_MODE`。

`@DEBUG_MODE`执行结束后，将`TARGET`重置为`MEMO_TARGET`记录的值。

最后后遍历所有角色，为每一个角色都调用一次`@SET_3SIZE, LOCAL`（此函数作用不明，过后研究）。
