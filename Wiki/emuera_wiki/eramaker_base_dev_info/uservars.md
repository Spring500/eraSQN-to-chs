﻿# 用户定义变量

----------------------------------------

+ 書式（プライベート変数の場合）
+ 初期値の設定
+ 動的変数
+ 定数
+ 参照型変数
+ 書式（広域変数の場合）
+ 制限
	+ 命令と同じ名前は使用不可
	+ 関数の外部からの干渉

----------------------------------------

\#DIM および #DIMS を利用することで好きな変数を定義することが可能です。

関数内で定義した変数はその関数内でのみ使用可能なプライベート変数に、

[ヘッダーファイル（ERH）](/Wiki/emuera_wiki/eramaker_base_dev_info/erh.md)内で定義した変数はERB中の全ての箇所から参照できる広域変数になります。

## 書式（プライベート変数の場合）

その変数を定義したい関数の宣言の下に「#DIM(S) <変数名>, <要素数>{, <要素数>{, <要素数>}}」を記述します。

<変数名>は関数名と同様に、先頭が数字でなく、記号は"\_"のみで構成された任意の文字列です。

<要素数>はすべて1～1000000の範囲内の任意の整数または定数式です。省略した場合、1となります。

<要素数>をいくつ与えたかによって、定義される変数の次元が変化します。最大は三次元で、四次元以上の変数を定義することはできません。

\#DIM(S)によるプライベート変数は単一関数中に複数定義できます。

これにより、<変数名>で指定した名前の変数がその関数内で使用可能になります。

変数は<要素数>で指定した要素数で代入可能、セーブはされません。初期値は0または空文字列です。

\#DIMで定義すると整数型変数に、#DIMSで定義すると文字列型変数になります。

\#DIM(S)で定義した変数はその関数の引数に指定することも可能です。初期値も設定できます。

```
@FIND_CSTR(KEY, VALUE)
#FUNCTION
#DIM LCOUNT
#DIM KEY
#DIMS VALUE
SIF KEY < 0 || KEY >= VARSIZE("CSTR")
	RETURNF -1
FOR LCOUNT, 0, CHARANUM
	SIF LCOUNT == MASTER
		CONTINUE
	SIF CSTR:LCOUNT:KEY == VALUE
		RETURNF LCOUNT
NEXT
```

上のスプリクトのように、用途に合わせた変数名をつけ、適切な要素数を設定することで

連続的でないLOCALの多用による可読性の低下を改善することができるかもしれません。

----------------------------------------

## 初期値の設定

1次元配列変数を宣言する際、初期値を定義することができます。

初期値を定義した配列の要素数は省略することができ、その場合初期値の数が自動的に配列の要素数になります。

配列の要素数を省略しない場合はその数字が配列の要素数になります。

要素数が省略されておらず、かつ初期値の数が要素数より多い場合にはエラーになります。

```
;要素数を省略したためHOGEの要素数は3
#DIM HOGE = 1,2,3

;要素数を省略しないためPUGEの要素数は100
#DIM PUGE,100 = 4,5,6

;エラー（初期値の数が指定した要素数より多い）
#DIM HIGE,1 = 7,8,9

;文字列変数でも可能（文字列式で指定）
#DIMS SHOGE = "A", "B", "C"
```

なお、多次元配列には初期値を定義できません。

----------------------------------------

## 動的変数

「#DIM(S) DYNAMIC <変数名>, <要素数>」のように変数名の前にDYNAMICを入れると、定義された変数は動的に確保されます。

具体的には関数が呼ばれたときに確保され、関数が終了したときに変数とその中の値は消滅します。

（RESTART命令は「関数の最初に戻る命令」であるため、動的に確保した変数であってもリセットされることはありません）

関数中に自分自身を呼出（再帰）した場合も再帰した回数だけ変数が確保されるため再帰処理の挙動が安定します。

ただしDYNAMICを入れない場合（静的変数）に比べ動作が遅くなります。

----------------------------------------

## 定数

1次元配列変数を定義する際に変数名の前にCONSTを入れると、1次元配列の定数が定義されます。

初期値同様に、1次元配列変数のみ定義することができます。

定数の宣言には必ず初期値が必要で、また途中で代入して変更することはできません。

またCONSTはその性質上、GLOBAL、SAVEDATA、REF、DYNAMICキーワードと同時には使用できません。

なお、配列の要素数を省略せずに指定することもできますが、要素数と初期値の数が一致しない場合エラーになります。

```
;1次元定数配列の定義
#DIM CONST HOGE = 1,2,3

;エラー（初期値の数と要素数が一致しない）
#DIM CONST PUGE,100 = 4,5,6

;文字列変数でも可能（文字列式で指定）
#DIMS CONST SHOGE = "A", "B", "C"
```

----------------------------------------

## 参照型変数

変数名の前にREFキーワードを用いることで、参照型変数を定義できます。

整数型1～3次元配列、文字列型1～3次元配列はそれぞれ以下のように宣言します。

```
#DIM REF HOGE1DIM,0
#DIM REF HOGE2DIM,0,0
#DIM REF HOGE3DIM,0,0,0
#DIMS REF PUGE1DIM,0
#DIMS REF PUGE2DIM,0,0
#DIMS REF PUGE3DIM,0,0,0
```

カンマの数があっていれば0は省略してもかまいません。1次元配列の場合はカンマも省略できます。
参照型変数は実体を持たず、参照型変数を操作するとREF命令（ver1.815現在は利用不能）又は参照渡しにより渡された変数が代わりに操作されることになります。
参照渡しの詳細は[関数-引数の参照渡し](/Wiki/emuera_wiki/eramaker_base_dev_info/exfunc.md#引数の参照渡し)を確認してください。

----------------------------------------

## 書式（広域変数の場合）

[ヘッダーファイル（ERH）](/Wiki/emuera_wiki/eramaker_base_dev_info/erh.md)内に#DIM(S)を記述した場合、ERB中で定義するプライベート変数とは異なり、
ERB中の全ての箇所から参照できる広域変数になります。

プライベート変数とは異なりDYNAMIC、STATICの区別はなく、REFを用いた参照型変数を定義することもできませんが、CONSTを用いた定数は同様に定義できます。

関数中におけるDIMにはない機能としてセーブされる変数やグローバル変数、キャラ変数を定義することが可能です。

詳しくは[ヘッダーファイル（ERH）](/Wiki/emuera_wiki/eramaker_base_dev_info/erh.md)の項目をご確認ください。

----------------------------------------

## 制限

### 命令と同じ名前は使用不可

以下のように、命令と同じ名前の変数を定義することはできません。

```
;エラー
#DIM PRINTFORM
#DIM SELECTCASE
#DIM CALL
#DIM RETURN
#DIM GOTO
#DIM SQRT
#DIM DATAFORM
#DIM NOSKIP
#DIM FUNC
#DIM ENDFUNC
```

関数名・プリプロセッサと同じ名前の変数は定義できますが、推奨できません。

```
;推奨しない
#DIM EVENTFIRST
#DIM COMF32
#DIM COMABLE15
#DIM SHOW_ABLUP_SELECT
#DIM DIM
#DIM PRI
#DIM ONLY
#DIM SKIPSTART
```

### 関数の外部からの干渉

LOCAL@HOGEのあるLOCALと異なり、他の関数のプライベート変数を参照したり、代入したりする方法はありません。