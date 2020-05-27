---
name: Bug汇报
about: 反馈游戏强制退出的情况
title: Bug汇报
labels: bug
assignees: ''

---

<sup>（注意：请不要随意更改模板格式，熟悉Markdown者除外）</sup>

**小提示**：编辑时可以点击上方的`Preview`标签预览最终效果，点击`Write`返回编辑框

----------------------------------------

### 请简单描述一下Bug发生的时间点：

如：调教结算，升级能力时

----------------------------------------

### emuera.log 日志内容：

**请将日志内容粘贴到下方两行反引号中间**

```
日志粘贴区域

例子：

TRAIN\Function_Sq.erbの3396行目でエラーが発生しました:Emuera_1.821.0.0
		RETURNF TALENT:ARG:ARGS
エラー内容：talent.csvの中に"ドラグーン"の定義がありません
現在の関数：@COND（TRAIN\Function_Sq.erbの869行目）
関数呼び出しスタック：
↑TRAIN\Function_Sq.erbの3417行目（関数@FIND_COND内）
↑EVENT\Daily_Life.erbの910行目（関数@DAILY_LIFE_MAIN内）
↑EVENT\Daily_Life.erbの19行目（関数@DAILY_LIFE内）
↑System.erbの512行目（関数@EVENTTURNEND内）
```
