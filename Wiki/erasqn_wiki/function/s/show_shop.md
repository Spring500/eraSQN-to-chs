﻿# @SHOW_SHOP

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 游戏主菜单显示

+ 读取存档后，此函数会被引擎自动调用

### 所在文件

+ [Shop.erb](/ERB/SHOP/Shop.erb#L137-L545)

### 调用关系

**被调用**：

+ 读取存档后，此函数会被自动执行

**调用**：

+ `@ASSI_LIST_ABL`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/assi_list_abl.md)</sup>

+ `@ASSI_LIST_INDICATE`<sup>[说明文件](/Wiki/erasqn_wiki/function/a/assi_list_indicate.md)</sup>

+ `@CDAYEV`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/cdayev.md)</sup>

+ `@CHARA_NUM`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/chara_num.md)</sup>

+ `@CHECK_FLAG_MUMA`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/check_flag_muma.md)</sup>

+ `@CONFIG`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/config.md)</sup>

+ `@DAYEV`<sup>[说明文件](/Wiki/erasqn_wiki/function/d/dayev.md)</sup>

+ `@DEL_CEVENT_GROUP`<sup>[说明文件](/Wiki/erasqn_wiki/function/d/del_cevent_group.md)</sup>

+ `@EVENTTURNEND_FLAG`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/eventturnend_flag.md)</sup>

+ `@EVENT_TRAVEL`<sup>[说明文件](/Wiki/erasqn_wiki/function/e/event_travel.md)</sup>

+ `@PRINT_BAR`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_bar.md)</sup>

+ `@PRINT_DRESS`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_dress.md)</sup>

+ `@SAVE_PALAM_BEFORECOM`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/save_palam_beforecom.md)</sup>

+ `@SETFLAG`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/setflag.md)</sup>

+ `@SET_COUNTER_BASE`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_counter_base.md)</sup>

+ `@TEXT`<sup>[说明文件](/Wiki/erasqn_wiki/function/t/text.md)</sup>

+ `@TEXT_LJ`<sup>[说明文件](/Wiki/erasqn_wiki/function/t/text_lj.md)</sup>

+ `@VERUP_ERASQ`<sup>[说明文件](/Wiki/erasqn_wiki/function/v/verup_erasqn.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

+ 无返回值

#### 功能实现

**L138-L144**：

声明数值变量：
+ LCOUNT
+ MEMO_LINECOUNT
+ NEXT_LINE
+ MEMO_TARGET
+ MEMO_ASSI
+ ACTOR

声明字符串变量：
+ MENU_SHOP

**L149**：

调用`@VERUP_ERASQN, TARGET`更新旧版存档

**L155**：

将`FLAG:8`判定值设为显示`1`。

**L157**：

重置变量TFLAG。

**L160**：

重置角色变量·行动标志`CFLAG:95`为`0`。

**L162**：

重置有显示助手能力的画面的相关设定`FLAG:45`为`0`。

**L164**：

重置能力显示画面的三围显示`FLAG:46`为`0`。

**L166**：

重置变更调教对象画面的相关设定`FLAG:47`为`0`。

**L168**：

重置调教过程中发生事件的标志`FLAG:47`为`0`。

**L170**：

重置调教命令菜单的显示过滤器`FLAG:210`的后21bit为`0`。

**L172**：

重置调教对象是否可变更标志`FLAG:253`为`0`

**L174-L175**：

将`MASTER`和`PLAYER`都重置为`1`。

**L177**：

将`TARGET:1 ～ TARGET:4`都重置为`0`。

**L179**：
用`MAX(TARGET, 0)`对比是`TARGET`的值大还是`0`大，然后将较大的值赋给`TARGET`，防止`TARGET`变成非法值。

**L180**：
用`MAX(ASSI, 0)`对比是`ASSI`的值大还是`0`大，然后将较大的值赋给`ASSI`，防止`ASSI`变成非法值。

**L182**：

调用`@SETFLAG, "等级限制器"`，将MASTER的等级设为等级限制器设定的等级。

**L187**：

调用`@CHECK_FLAG_MUMA`。遍历每个角色，将不适合该角色的参数去除（如男性角色的子宫内精子量应为`0`等），并重新计算需要计算的参数值（如出售价格等）。

**L190**：

调用`@SET_COUNTER_BASE`重置每一个角色的精力和STOCK。

**L192**：

调用`@SAVE_PALAM_BEFORECOM`，重置所有角色有关调教时的状态计量表。

**L197-L217**：

当存在`FLAG:60`温泉旅行目的地且事件为周六`@DAYEV("土曜", "ゲーム内")`且时间为`@TEXTS("時間") == "昼"`时，先用`MEMO_TARGET`和`MEMO_ASSI`记录当前的调教对象和助手编号。

接着调用`@EVENT_TRAVEL`。

（作用不明，过后研究）然后用2层循环（共15次），最内层调用5次`EVENTTURNEND_FLAG, LCOUNT`（LCOUNT为内层循环的遍历数，区间`[1～5]`），在外层循环执行`TIME = (TIME + 1)%2`（共3次）。

（`TIME`是一个非`0`既`1`的值，代表什么仍未能确定）

接着将`FLAG:60～70`重置为`0`，将每个角色的`CFLAG:70`重置为`0`。

游戏内日期`DAY`增加一天。

调用`SETFLAG, "安全危険日判定"`检查并设置每个角色的生理周期。

最后再将调教目标`TARGET`和助手`ASSI`重置为`MEMO_TARGET`和`MEMO_ASSI`记录的值，并重新执行L197的条件判定。

**L222**：

用`FLAG:2`记录到目前为止引擎显示过的行数`LINECOUNT`

**L228-L230**：

计算目前游戏内的日期、年份、季节，并将其存到`FLAG:871～FLAG:873`中。

**L232**：

显示游戏内部的季节和时间。

**L233-L234**：

如果在酒馆吃过东西，就显示吃过的东西。

**L236-L238**：

如果持有魔法瓶，就显示魔法瓶内的精液储量。

**L240-L253**：

用`TEXTS("日付対応イベント")`检查目前的日期是否落在节庆日。

如果落在节庆日，就将字体颜色设成`黄色`然后显示节日的名称。

（L246-L248作用不明，过后研究）

**L255-L265**：

如果选定了`TARGET`调教对象，就显示调教对象的名字、生理周期、体力、好感度、侍奉快乐经验、穿着。

**L266-L280**：

如果设置了`ASSI`助手，就显示助手的名字、生理周期、助手的能力以及给助手的指示。

**L282**：

显示MASTER的名字。

**L283-L299**：

如果开启了等级限制器，就显示等级限制器的设定。

**L300**：

显示MASTER的精力，

如果`MAXBASE:MASTER:STOCK`不为`0`就显示STOCK，

以及生理周期、能力。

**L312**：

将`ITEMSALES`的第0～100bit设为`1`。

**L316**：

将`MENU_SHOP`置为空值。

**L318-L324**：

向变量`MENU_SHOP`追加菜单项目[进行调教]。

如果没有选定`TARGET`调教对象，就将[进行调教]设成灰色。

如果选定了`TARGET`调教对象且对象的`GETBIT(CFLAG:201, 4)==1`就追加为[前去会面]，其余情况追加为[进行调教] 。

`CFLAG:201`推测是相思相爱或恋慕或淫乱的标志（但日版的资料中却说该FLAG是`調教開始時のセリフ`，需要更多代码佐证其作用）。

**L326**：

向变量`MENU_SHOP`追加菜单项目[查看能力]。

**L328-L330**：

向变量`MENU_SHOP`追加菜单项目[休息]，

如果没有选定`TARGET`调教对象，或处于`CONFIG("調教相手変更不可")`调教对象不可变更时显示为灰色。

**L332-L334**：

向变量`MENU_SHOP`追加菜单项目[交换助手和对象]，

如果没有选定`ASSI`助手，或处于`CONFIG("調教相手変更不可")`调教对象不可变更时显示为灰色。

**L336-L338**：

向变量`MENU_SHOP`追加菜单项目[变更助手]，

如果`CHARA_NUM("助手可能")`可以作为助手的人数为`0`，或`CONFIG("調教相手変更不可")`调教对象不可变更时显示为灰色。

**L340-L342**：

向变量`MENU_SHOP`追加菜单项目[变更调教对象]，

如果`CHARA_NUM("控えキャラ")`除MASTER外的角色数为`0`，或处于`CONFIG("調教相手変更不可")`调教对象不可变更时显示为灰色。

**L344-L349**：

向变量`MENU_SHOP`追加菜单项目[梦魔召唤]，

如果`CHARANUM`角色总数`>=100`或`CONFIG("調教相手変更不可")`调教对象不可变更时显示为灰色。

如果`CHARANUM`角色总数`<2`时显示和为粉红色。

**L351-L353**：

向变量`MENU_SHOP`追加菜单项目[梦魔出售]，

如果`CHARA_NUM("売却可能")`可出售的角色数为`0`或`CONFIG("調教相手変更不可")`调教对手不可变更时就显示为灰色。

**L355-L357**：

向变量`MENU_SHOP`追加菜单项目[确认着装]，

如果`CHARANUM`角色总数小于`2`，则显示为灰色。

**L359**：

向变量`MENU_SHOP`追加水蓝色的菜单项目[召见御用商人]。

**L361-L363**：

向变量`MENU_SHOP`追加菜单项目[去高级服饰店]，

如果`NUM("所持衣装")`所持衣装数量=`NUM("総衣装数")`总衣装数，则显示为灰色否则显示为水蓝色。

**L365**：

向变量`MENU_SHOP`追加水蓝色的菜单项目[去秘法店]。

**L367**：

向变量`MENU_SHOP`追加水蓝色的菜单项目[去饰品屋]。

**L369-L371**：

向变量`MENU_SHOP`追加水蓝色的菜单项目[去酒馆]，

如果`FLAG:40`不为`0`（之前吃过东西），则显示为灰色。

**L373-L375**：

向变量`MENU_SHOP`追加菜单项目[外出许可管理]，

如果`CHARA_NUM("一晩開放可能")`可以外出的人数为`0`则显示为灰色。

**L377**：

向变量`MENU_SHOP`追加菜单项目[外出探索]。

**L379-L383**：

向变量`MENU_SHOP`追加菜单项目[素材调合]，

如果MASTER或者助手都没有持有技能调合知识的话就显示为灰色。

**L385-L387**：

向变量`MENU_SHOP`追加菜单项目[文书工作]，

如果`FLAG:12`为`1`当前无文书工作或`CHARA_NUM("書類仕事")`拥有文书工作相关技能的角色数为`0`时，显示为灰色。

**L389-L391**：

向变量`MENU_SHOP`追加菜单项目[助手性欲处理]，

如果没有选定`TARGET`助手或`CEVENT("助手で性処理：おあずけ", ASSI)`助手没有性欲可处理或`CONFIG("調教相手変更不可")`调教对手不可变更时，显示为灰色。

**L393-L395**：

向变量`MENU_SHOP`追加菜单项目[预约旅行]，

如果没有选定`TARGET`调教对象或`COND("温泉旅行可能")`目前不可以去温泉旅行，则显示为灰色。

**L397-L399**：

向变量`MENU_SHOP`追加菜单项目[偏爱&弱点设定]，

如果`FLAG:208`剩余变更限制天数不为`0`，则显示为灰色。

**L401-L403**：

向变量`MENU_SHOP`追加菜单项目[道具&衣装一览]，

如果`NUM("所持アイテム")`所持道具数+`NUM("所持衣装")`所持衣装数为`0`，则显示为灰色。

**L404-L406**：

向变量`MENU_SHOP`追加菜单项目[出售道具]，

如果`NUM("売却可能アイテム")`可出售道具数为`0`，则显示为灰色。

**L408-L410**：

向变量`MENU_SHOP`追加菜单项目[数据分析]（被关闭，可以重新打开，建议编号为[310]），

如果没有选定`TARGET`调教对象时显示为灰色。

**L412-L418**：

向变量`MENU_SHOP`追加菜单项目[咖啡店的准备]或[咖啡店开张]，

如果`NUM("所持店舗")`持有的店铺数量大于`0`则显示为[咖啡店的准备]，

否则如果`NUM("運営可能店舗")`可以运营店铺数为`0`则显示为[咖啡店开张]。

**L420**：

向变量`MENU_SHOP`追加菜单项目[保存]。

**L422**：

向变量`MENU_SHOP`追加菜单项目[读取]。

**L424-L425**：

当`ITEM:化蝶之梦`的值等于`100`时，则向变量`MENU_SHOP`追加菜单项目[从梦中醒来]。

**L427-L428**：

如果持有等级限制器，则向变量`MENU_SHOP`追加菜单项目[等级限制器]。

**L430**：

向变量`MENU_SHOP`追加菜单项目[系统设定]。

**L433-L434**：

如果`COND("エンディング選択可能")`可以进入ENDING时，则向变量`MENU_SHOP`追加菜单项目[迎接END]。

**L435-L436**：

如果`NUM("ＥＮＤ閲覧済")`大于`0`，则向变量`MENU_SHOP`追加菜单项目[回想特殊END]。

**L438-L439**：

当选定了调教目标`TARGET`，且`COND("子孫")`调教目标为子孙，

且调教目标的名字`(NAME:TARGET == "娘" || NAME:TARGET == "息子")`为`娘`或`息子`时，

向变量`MENU_SHOP`追加菜单项目[给XXX取名字]。

> 可能存在翻译bug导致显示不出来，后期需要注意检查。

**L442**：

将`LOCALS`置为空值。

**L443**：

将`MENU_SHOP`以`/`作为分隔符进行分割，将分割结果存到LOCALS中。

**L449-L475**：

使用FOR循环遍历`LOCALS`，并使用`@TEXT_LJ`打印菜单项目，

每输出三个就换行一次。

> 此处有中文字符长度bug，已修正。

**L476-L477**：

最后再确认一下，如果当前`NEXT_LINE`换行标记为3的倍数，再输出一个换行符。

**L481**：

将`LOCALS`置为空值。

**L482-L503**：

（作用不明，过后研究）

**L505**：

用`MEMO_LINECOUNT`记录到目前为止引擎显示过的行数`LINECOUNT`。

**L508-L542**：

当`CHARANUM`角色总数大于`3`，且`COND("一言イベント中")`为0的情况下，

另`ACTOR`等于随机一个非玩家角色的编号。

当`CONFIG("台詞の名前非表示")`设置了显示台词角色名时，打印出角色名。

用`MEMO_LINECOUNT`记录到目前为止引擎显示过的行数`LINECOUNT`。

然后，尝试调用`GUEST_KOJO_K{NO:ACTOR}_{CFLAG:ACTOR:209}, "一言イベント", ACTOR`。

（推测此函数会输出一句话小剧场，过后研究）

当`MEMO_LINECOUNT`等于引擎显示过的行数`LINECOUNT`时，说明上述函数不存在，或没有输出任何内容：

  + 用引擎内置命令`CLEARLINE`消除上一行显示。

  + 如果`CONFIG("台詞の名前非表示")`设置了显示台词角色名时，再调用一次擎内置命令`CLEARLINE`消除上一行显示（之前显示的说话人角色名）。

  + 重新用`MEMO_LINECOUNT`记录到目前为止引擎显示过的行数`LINECOUNT`。

否则，当引擎显示过的行数`LINECOUNT`大于`MEMO_LINECOUNT`记录的行数时：
	
  + 用`FLAG:23`记录小剧场的演出者。

  + 将`FLAG:23`第10bit置为`1`。（作用不明，过后研究）

  + 然后调用`@INPUT_SEXUHARA, ACTOR`。（作用不明，过后研究）

另外，当`COND("一言イベント中") 即 GETBIT(FLAG:23, 10)`为`0`，且`LINECOUNT`与之前记录的行数`MEMO_LINECOUNT`相等，且`RAND:3`为`0`时：

  + 调用`COND("温泉旅行可能", ACTOR)`检查当前ACTOR是否可以被带去温泉旅行，如果可以，就输出对应的提示。

  + 如果ACTOR不是当前的调教对象`TARGET`，ACTOR处于`COND("欲求不满", ACTOR)`欲求不满状态的话，就输出响应的提示。

**L544-L545**：

如果此时`LINECOUNT`与之前记录的行数`MEMO_LINECOUNT`相等，就再输出一个换行符。
