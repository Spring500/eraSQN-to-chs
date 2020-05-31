# @PROFILE

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/erasqn_wiki/function/README.md)

### 作用描述

+ 设置角色详情

### 所在文件

+ [Shop3.erb](/ERB/SHOP/Shop3.erb#L418-L890)

### 调用关系

**被调用**：

+ `@CHARA_MANUAL`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/chara_manual.md)</sup>

+ `@START_CHARA_SELECT`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/start_chara_select.md)</sup>

**调用**：

+ `@CALC`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/calc.md)</sup>

+ `@CEVENT`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/cevent.md)</sup>

+ `@COND`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/cond.md)</sup>

+ `@COORDINATE_MUMA`<sup>[说明文件](/Wiki/erasqn_wiki/function/c/coordinate_muma.md)</sup>

+ `@GET_EXABL`<sup>[说明文件](/Wiki/erasqn_wiki/function/g/get_exalb.md)</sup>

+ `@GET_EXTALENT`<sup>[说明文件](/Wiki/erasqn_wiki/function/g/get_extalent.md)</sup>

+ `@GET_MAGIC`<sup>[说明文件](/Wiki/erasqn_wiki/function/g/get_magic.md)</sup>

+ `@HIGH_RANKER`<sup>[说明文件](/Wiki/erasqn_wiki/function/h/high_ranker.md)</sup>

+ `@MEMO_FAVORITE_DRESS`<sup>[说明文件](/Wiki/erasqn_wiki/function/m/memo_favorite_dress.md)</sup>

+ `@PENIS`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/penis.md)</sup>

+ `@PRINT_PROFILE`<sup>[说明文件](/Wiki/erasqn_wiki/function/p/print_profile.md)</sup>

+ `@RESET_EXP_GAIN`<sup>[说明文件](/Wiki/erasqn_wiki/function/r/reset_exp_gain.md)</sup>

+ `@SET_3SIZE`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_3size.md)</sup>

+ `@SET_COUNTER_BASE`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_counter_base.md)</sup>

+ `@SET_NEWNAME`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/set_newname.md)</sup>

+ `@SETFLAG`<sup>[说明文件](/Wiki/erasqn_wiki/function/s/setflag.md)</sup>

+ `@TEXTS`<sup>[说明文件](/Wiki/erasqn_wiki/function/t/texts.md)</sup>

### 函数实现

#### 参数

+ ARG

+ ARGS

#### 返回值

+ 无返回值

#### 功能实现

**L419-L427**：

声明下列（数组）变量：

`LCOUNT`、`LCOUNT2`、`MEMO_TARGET`、`MEMO_MASTER`、`MEMO, 4`、`TALENT_FIX`和`TALENT_RMV`

**L429**：

调用引擎命令`ADDCHARA`新增角色`ARG`

（这就是为什么当玩家没有召唤且观看过角色详情时要删除最后一个角色的原因）

**L433-L437**：

使用`MEMO_TARGET`记录当前的调教目标`TARGET`

分别将`A`、`C`、`D`和`E`复制给`MEMO:0`、`MEMO:1`、`MEMO:2`和`MEMO:3`

然后将调教目`TARGET`标设为`CHARANUM - 1`
（这里是为了后面的代码编写方便而进行的更改，并非真的更改调教目标）

**L445-L494**：

以参数`ARG`作为选择支：

  + 当其值为`7`时：<br/>（要显示`ワーウルフ/狼人`的角色详情）

    + 当随机数`RAND:2`结果大于或等于`1`时：

      + **不**为角色设置`TALENT:四足步行`素质

  + 当其值为`9`时：<br/>（要显示`V.ヴィレッジャ/V.村女`的角色详情）

    + 当随机数`RAND:2`结果大于或等于`1`时：

      + 为角色设置`TALENT:贫乳`素质

  + 当其值为`16`时：<br/>（要显示`クズノハ/葛之叶`的角色详情）

    + 当随机数`RAND:3`结果为`0`时：

      + 为角色设置`TALENT:娇小体型`素质

      + 当随机数`RAND:4`结果大于或等于`1`时：

        + 为角色设置`TALENT:贫乳`素质

        + **不**为角色设置`TALENT:巨乳`素质

  + 当其值为`20`时：<br/>（要显示`エンジェル/天使`的角色详情）

    + 当随机数`RAND:5`结果为`0`时：

      + **不**为角色设置`TALENT:女性`素质

      + 为角色设置`TALENT:扶她`素质

      + 为角色设置`TALENT:童贞`素质

      + 将角色的`ABL:Ｃ感觉`等级设为`2`级

    + 当角色不为`TALENT:男性`，且随机数`RAND:5`结果为`0`时：

      + 为角色设置`TALENT:处女`素质

  + 当其值为`21`时：<br/>（要显示`ルシフェル/路西法`的角色详情）

    + 当随机数`RAND:5`结果为`0`时：

      + 为角色设置`TALENT:女性`素质

      + 为角色设置`TALENT:扶她`素质

      + 将角色的`ABL:Ｃ感觉`等级设为`2`级

      + 将角色的`EXP:Ｖ插入经验`置为与`EXP:Ｖ性交经验`一样的等级

      + 将角色的`EXP:腰技经验`置为现在已有数值的`2`倍

  + 当其值为`42`时：<br/>（要显示`バンダースナッチ/无法翻译`的角色详情）

    + 当随机数`RAND:3`结果为`0`时：

      + 为角色设置`TALENT:巨乳`素质

    + 当随机数`RAND:2`结果大于或等于`1`时：

      + 为角色设置`TALENT:贫乳`素质

  + 当其值为`48`时：<br/>（要显示`エスト/爱丝忒`的角色详情）

    + 当随机数`RAND:5`结果为`0`时：

      + **不**为角色设置`TALENT:高挑体型`素质

      + 为角色设置`TALENT:娇小体型`素质

      + **不**为角色设置`TALENT:巨乳`素质

      + 为角色设置`TALENT:贫乳`素质

  + 当其值为`61`时：<br/>（要显示`ヴァルキリー/女武神`的角色详情）

    + 角色不为`TALENT:男性`，且随机数`RAND:5`结果为`0`时：

      + 为角色设置`TALENT:处女`素质

**L496-L544**：

如果`@COND("ユニーク")`的调用结果为`0`时：<br/>（查询调教对象`TARGET`是否特殊角色，返回`0`则不是）

  + 如果随机数`RAND:5`结果为`0`，且角色不为`TALENT:男性`时：

    + 如果角色天赋`TALENT:巨乳`大于或等于`2`级时：

      + 当随机数`RAND:2`结果大于或等于`1`时：

        + 将角色的`TALENT:巨乳`天赋等级扣减`1`

    + 否则当角色`TALENT:巨乳`素质不为`0`时：

      + 如果随机数`RAND:2`结果大于或等于`1`时：

        + 将角色天赋`TALENT:巨乳`设为`2`级

      + 否则：

        + 将角色天赋`TALENT:巨乳`设为`0`级

    + 否则当角色`TALENT:贫乳`素质不为`0`时：

      + 如果随机数`RAND:2`结果大于或等于`1`时：

        + 将角色天赋`TALENT:贫乳`设为`0`级

    + 否则：

      + 如果随机数`RAND:2`结果大于或等于`1`时：

        + 将角色天赋`TALENT:巨乳`设为`1`级

      + 否则：

        + 将角色天赋`TALENT:贫乳`设为`1`级

  + 如果随机数`RAND:5`结果为`0`时：

    + 以角色的`TALENT:肤色`作为选择支：

      + 当其值为`0`时：<br/>（将`普通`肤色转成`褐色`或`白色`）

        + 如果随机数`RAND:2`结果大于或等于`1`时：

          + 将角色的`TALENT:肤色`置为`1`

        + 否则：

          + 将角色的`TALENT:肤色`置为`2`

      + 当其值为`1`时：<br/>（将`褐色`肤色转成`普通`）

        + 将角色的`TALENT:肤色`置为`0`

      + 当其值为`2`时：<br/>（将`白色`肤色转成`普通`）

        + 将角色的`TALENT:肤色`置为`0`

      + 当其值为`3`时：<br/>（将`青色`肤色转成`褐色`或`白色`）

        + 如果随机数`RAND:2`结果大于或等于`1`时：

          + 将角色的`TALENT:肤色`置为`1`

        + 否则：

          + 将角色的`TALENT:肤色`置为`2`

**L547-L554**：

如果调用`@CEVENT("固定：ふたなり", MASTER)`返回不为`0`时：<br/>（`@CEVENT`作用不明，过后研究，下同）

  + 将角色的`TALENT:扶她`素质设为`1`

  + 将角色的`TALENT:男性`素质设为`0`

  + 将角色的`TALENT:女性`素质设为`0`

否则如果调用`@CEVENT("除外：ふたなり", MASTER)`返回不为`0`时：

  + 将角色的`TALENT:扶她`素质设为`0`

  + 将角色的`TALENT:女性`素质设为`1`

**L555-L559**：

如果调用`@CEVENT("固定：処女", MASTER)`返回不为`0`，且角色不为`TALENT:男性`时：

  + 将角色的`TALENT:処女`素质设为`1`

否则调用`@CEVENT("除外：処女", MASTER)`返回不为`0`，且角色不为`TALENT:男性`时：

  + 将角色的`TALENT:処女`素质设为`0`

**L569-L564**：

如果调用`@CEVENT("固定：童貞", MASTER)`返回不为`0`，且调用`@PENIS(TARGET)`返回不为`0`时：<br/>（`@PENIS(TARGET)`会在TARGET为`男性`或`扶她`时返回`1`，否则返回`0`）

  + 将角色的`TALENT:童贞`素质设为`1`

否则调用`@CEVENT("除外：童貞", MASTER)`返回不为`0`，且调用`@PENIS(TARGET)`返回不为`0`时：

  + 将角色的`TALENT:童贞`素质设为`0`

**L566-L574**：

调用`@HIGH_RANKER, ARG, E`，在角色身上快速应用素质配置集

调用`@SETFLAG, "识别号码", TARGET`，为角色设置`识别号码`

调用`@SET_NEWNAME`，为角色设置名字

调用`@RESET_EXP_GAIN, TARGET`，重置角色的经验值

调用`@GET_EXABL, TARGET`，计算角色各种特殊经验的等级

调用`@GET_EXTALENT, TARGET`，计算角色的特殊天赋等级

调用`@SET_3SIZE, TARGET`，计算角色的三围

调用`@CALL SETFLAG, "陰毛と腋毛", TARGET`，设置角色的阴毛腋毛相关

调用`@SETFLAG, "乳首の詳細設定", TARGET`，设置角色乳头相关设定

**L578-L579**：

调用引擎命令`VARSET`，重置数组`LOCALS`

调用引擎命令`SPLIT`，将`@TEXTS("固定可能な素質")`返回的字符串以`/`作为分隔符，存到`LOCALS`数组中

**L581-L862**：

以`LCOUNT`作为迭代数，循环`100`次：

  + 当`LOCALS:LCOUNT`为空时：

    + 立即跳出当前循环

  + 将`固定：%LOCALS:LCOUNT%`赋值给`TALENT_FIX`

  + 将`除外：%LOCALS:LCOUNT%`赋值给`TALENT_RMV`

  + 如果`@CEVENT(TALENT_FIX, MASTER)`的返回值不为`0`：<br/>（处理手动指定的素质）

    + 以`LOCALS:LCOUNT`的值作为选择支：

      + 当其值为`乳首肥大`时：

        + 如果`GETBIT(TALENT:乳头, 0)`的返回值为`0`

          + 则立即进入下次循环

        + 调用引擎命令`CLEARBIT`将`TALENT:乳头`的第0bit置为`0`

        + 调用引擎命令`SETBIT`将`TALENT:乳头`的第1bit置为`1`

      + 当其值为`陥没乳首`时：

        + 如果`GETBIT(TALENT:乳头, 10)`的返回值为`0`

          + 则立即进入下次循环

        + 调用引擎命令`CLEARBIT`将`TALENT:乳头`的第10bit置为`0`

        + 调用引擎命令`SETBIT`将`TALENT:乳头`的第11bit置为`1`

      + 当其值为`巨乳輪`时：

        + 如果`GETBIT(TALENT:乳头, 20)`的返回值为`0`

          + 则立即进入下次循环

        + 调用引擎命令`CLEARBIT`将`TALENT:乳头`的第20bit置为`0`

        + 调用引擎命令`SETBIT`将`TALENT:乳头`的第21bit置为`1`

      + 当其值为`長身`时：

        + 如果角色拥有`TALENT:妖精`素质：

          + 则立即进入下次循环

        + 调用`@CALC, "長身化", TARGET`

      + 当其值为`小柄体型`时：

        + 如果角色拥有`TALENT:妖精`素质：

          + 则立即进入下次循环

        + 调用`@CALC, "小柄化", TARGET`

      + 当其值为`貧乳`时：

        + 如果角色拥有`TALENT:男性`素质：

          + 则立即进入下次循环

        + 调用`@CALC, "貧乳化", TARGET`

      + 当其值为`巨乳`时：

        + 如果角色拥有`TALENT:男性`素质：

          + 则立即进入下次循环

        + 调用`@CALC, "巨乳化", TARGET`

      + 当其值为`爆乳`时：

        + 如果角色拥有`TALENT:男性`素质：

          + 则立即进入下次循环

        + 调用`@CALC, "爆乳化", TARGET`

      + 当其值为`超乳`时：

        + 如果角色拥有`TALENT:男性`素质：

          + 则立即进入下次循环

        + 调用`@CALC, "超乳化", TARGET`

      + 当其值为`小尻`时：

        + 如果`@COND("小尻")`的返回值大于或等于`0`：

          + 则立即进入下次循环

        + 将角色的`TALENT:大臀`素质设为`0`

        + 以`LCOUNT2`作为迭代数，FOR循环`100`次：

          + 如果`@COND("小尻")`的返回值大于或等于`0`

            + 立即跳出当前循环

          + 将角色的`BASE:臀围`扣减`BASE:身高 * 2 / 100`

        + 将角色的素质`TALENT:小臀`设为`1`

      + 当其值为`巨尻`时：

        + 如果`@COND("巨尻")`的返回值为`1`时：

          + 则立即进入下次循环

        + 如果`@COND("巨尻")`的返回值为`0`时：

          + 将角色的素质`TALENT:小臀`设为`0`

          + 以`LCOUNT2`作为迭代数，FOR循环`100`次：

            + 如果`@COND("小尻")`的返回值大于或等于`0`

              + 立即跳出当前循环

            + 将角色的`BASE:臀围`加上`BASE:身高 * 2 / 100`

        + 否则：

          + 以`LCOUNT2`作为迭代数，FOR循环`100`次：

            + 如果`@COND("小尻")`的返回值小于或等于`1`

              + 立即跳出当前循环

            + 将角色的`BASE:臀围`扣减`BASE:身高 * 2 / 100`

          + 将角色的素质`TALENT:大臀`设为`1`

      + 当其值为`爆尻`时：

        + 如果`@COND("巨尻")`的返回值为`2`时：

          + 则立即进入下次循环

        + 如果`@COND("巨尻")`的返回值小于等于`1`时：

          + 将角色的素质`TALENT:小臀`设为`0`

          + 以`LCOUNT2`作为迭代数，FOR循环`100`次：

            + 如果`@COND("小尻")`的返回值大于或等于`2`

              + 立即跳出当前循环

            + 将角色的`BASE:臀围`加上`BASE:身高 * 2 / 100`

        + 否则：

          + 以`LCOUNT2`作为迭代数，FOR循环`100`次：

            + 如果`@COND("小尻")`的返回值小于`2`

              + 立即跳出当前循环

            + 将角色的`BASE:臀围`扣减`BASE:身高 * 2 / 100`

        + 将角色的素质`TALENT:大臀`设为`2`

      + 当其值为`超尻`时：

        + 如果`@COND("巨尻")`的返回值为`3`时：

          + 则立即进入下次循环

          + 将角色的素质`TALENT:小臀`设为`0`

          + 以`LCOUNT2`作为迭代数，FOR循环`100`次：

            + 如果`@COND("巨尻")`的返回值为`3`

              + 立即跳出当前循环

            + 将角色的`BASE:臀围`加上`BASE:身高 * 2 / 100`

        + 将角色的素质`TALENT:大臀`设为`3`

      + 当其值为`褐色肌`时：

        + 将角色的素质`TALENT:肤色`设为`1`

      + 当其值为`色白`时：

        + 将角色的素质`TALENT:肤色`设为`2`

      + 当其值为`青肌`时：

        + 将角色的素质`TALENT:肤色`设为`3`

      + 当其值为`母乳体質`或`子宮性感`时：

        + 如果角色不为`TALENT:男性`

          + 将角色的素质`TALENT:(LOCALS:LCOUNT)`设为`1`

      + 当其值为`腸液分泌体質`、`嘔吐反射耐性`、`拡張適正`、`喉性感`、`尿道性感`或`においに弱い`时：

          + 将角色的素质`TALENT:(LOCALS:LCOUNT)`设为`1`

      + 当其值为`処女`、`童貞`或`ふたなり`时：

          + 未定义特殊行为

  + 否则如果`@CEVENT(TALENT_RMV, MASTER)`的返回值不为`0`：<br/>（处理手动排除的素质）

    + 参考上面的说明，差不多做同样的事，只不过设置的值是相反的

    + 实在太长了……

**L864-L869**：

调用`@SETFLAG, "属性", TARGET`，设置角色的`BASE:属性`（此数值不同二进制位代表不同的意义，请参阅该函数的详情）

调用`@CALC, "好きな体位", TARGET`，设置角色`TALENT:喜欢的体位`

调用`@SETFLAG, "ペニス詳細設定"`，设置角色`TALENT:阴茎`

调用`@COORDINATE_MUMA, TARGET`，设置角色衣装

调用`@MEMO_FAVORITE_DRESS, TARGET`，设置角色喜爱的衣装？（作用不明，过后研究）

**L871-L878**：

如果`ARGS`的值为`主人`：

  + 以变量`MEMO_MASTER`记录当前`MASTER`的值

  + 将`TARGET`赋值给`MASTER`

  + 调用`@SET_COUNTER_BASE`，设置角色的精力和STOCK

  + 将`MASTER`恢复为`MEMO_MASTER`

否则：

  + 调用`@SET_COUNTER_BASE`

**L880-L881**：

如果角色为`TALENT:魔法使`：

  + 调用`@GET_MAGIC, TARGET`设置角色拥有的秘法

**L884**：

调用`@PRINT_PROFILE`，打印角色的素质

**L886-L890**：

将`TARGET`恢复为`MEMO_TARGET`

将`A`恢复为`MEMO:0`

将`B`恢复为`MEMO:1`

将`C`恢复为`MEMO:2`

将`D`恢复为`MEMO:3`
