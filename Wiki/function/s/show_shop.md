# @SHOW_SHOP

> [\[回Wiki首页\]](/Wiki) [\[回函数列表\]](/Wiki/function/README.md)

### 作用描述

+ 读取存档后，此函数会被自动执行

### 所在文件

+ [Shop.erb](/ERB/SHOP/Shop.erb#L137-L545)

### 调用关系

**被调用**：

+ 读取存档后，此函数会被自动执行

**调用**：

+ `@VERUP_ERASQN`<sup>[说明文件](/Wiki/function/v/verup_erasqn.md)</sup>

+ `@SETFLAG`<sup>[说明文件](/Wiki/function/s/setflag.md)</sup>

### 函数实现

#### 参数

+ 无参数

#### 返回值

返回值描述

#### 功能实现

L149：调用`@VERUP_ERASQN`更新旧版存档

L154-L182：变量初始化列表

  变量名称|初始化值|变量作用
  ----|----|----
  FLAG:8|1|判断值的显示(0=不显示，1=显示)
  TFLAG|0|`VARSET TFLAG`，重置TFLAG
  CFLAG:COUNT:95|0|`CVARSET CFLAG, 95, 0`<br/>重置各个角色的行为(bit)<br/>0=怀孕夜晚流逝, 1=咖啡店打工, 2=开放深夜偷吃, 3=同床事件,<br/>4=日常事件出演, 5=参加乱交, 6=咖啡店对话？<br/>作用不明，需要后续的程序解析
  FLAG:45|0|助手画面恢复为默认
  FLAG:46|0|初始化能力显示画面的三围显示
  FLAG:47|0|重置调教对象切换画面
  FLAG:99|0|`调教中`之类的标志OFF
  FLAG:210|`FLAG:210 &= ~(1 << 21)`|`CLEARBIT FLAG:210, 21`<br/>重置不显示命令的状态
  FLAG:253|0|重置允许变更角色标志
  MASTER|1|将PLAYER设为MASTER（以防万一）
  PLAYER|MASTER|将PLAYER设为MASTER（以防万一）
  TARGET:1\~TARGET:4|0|複数キャラを使うイベント用の対象フラグリセット
  TARGET|MAX(TARGET, 0)|TARGETとASSIが-1となることを禁止
  ASSI|MAX(ASSI, 0)|TARGETとASSIが-1となることを禁止<br/>作用不明，需要后续的程序解析
  -|-|`CALL SETFLAG, "等级限制器"`<br/>检查等级限制器
