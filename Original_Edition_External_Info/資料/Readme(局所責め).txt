「挿入局所責めパッチ」1.00　byぱ

eratohoRR向けのコマンド追加パッチです。
追加コマンドは以下の２つ（マイナーチェンジ込み４つ）です。

「挿入（騎乗）Ｇスポ責め」「挿入（騎乗）子宮口責め」

正常位、後背位、騎乗位、対面座位、背面座位、乱れ牡丹のいずれかを二回続けて選ぶことで発生します。
その際調教者の技巧が3以上必要で、体位やＶ感覚、欲情の値に応じてどちらかにランダムで派生します。
対面座位のような奥へ入れやすい体位は子宮口責めが発生しやすく、背面座位のような入り口を責めやすい体位はＧスポ責めになりやすいです。
また、Ｖ感覚・欲情がそれぞれ高い方が子宮口責めになりやすいです。

Ｇスポ責めは露出を伴い、Ｖ開発前でもそれなりの効果があります。
大きいストロークをしないため、挿入している側への快感は小さく、射精ゲージはあまり増えません。

子宮口責めはＶ開発がかなり進んでいないと効果が小さいですが、開発しきった奴隷には効果抜群です。
Ｇスポ責めほどではないですが、やはり射精ゲージはあまり増えません。
正常位・対面座位・後背位から派生した場合、擦れるので快Ｃも発生します。


それだけのパッチです。


私はあれですよ。
奥コツコツされて子宮ダダ下がりの雌モードになったぱる子がアヘ顔であーあーバカみたいに喘いでるところが見たいんだ。
それだけなんだ。


ERBファイルを全てERBフォルダに突っ込んでご利用ください。
各種パッチを妨げるものはほぼ入ってないので、可能な限り最後に導入してください。
というかそうじゃなきゃ正常に動きません。

口上をつけたいという奇特な方は、「口上テンプレ用.txt」か最新のぱるぷれーとを参照してください。


http://mixi.jp/show_friend.pl?id=20112285
mixi取りました。罵声や要望、バグ取り依頼などどしどしこちらへ。


口上テンプレ用やっつけです。CFLAGはぱるぷれーと依存。
体位別に分けたい場合はPREVCOMで分岐可能。


;-------------------------------------------------
;コマンド実行時のセリフ CFLAG 301～400を使用
;愛撫・クンニのみ301・302。それ以降は300+コマンド番号のCFLAGに統一
;-------------------------------------------------

;-------------------------------------------------
;以下、挿入局所責めパッチのコマンド群
;-------------------------------------------------
;挿入Ｇスポ責め（正常位・後背位・対面座位・背面座位繰り返し） CFLAG555
;騎乗Ｇスポ責め（騎乗位繰り返し）
;-------------------------------------------------
;騎乗Ｇスポ責め
IF SELECTCOM == 255 && PREVCOM == 34
	;初回
	IF CFLAG:555 == 0 || CFLAG:555 == 2
		;恋慕
		IF TALENT:85
			PRINTFORMW 
		;それ以外
		ELSE
			PRINTFORMW 
		ENDIF
		SIF CFLAG:555 == 0
			CFLAG:555 = 1
		SIF CFLAG:555 == 2
			CFLAG:555 = 3
	;二回目以降
	ELSE
		;恋慕
		IF TALENT:85
			PRINTFORMW 
		;それ以外
		ELSE
			PRINTFORMW 
		ENDIF
	ENDIF
	RETURN 0
;挿入Ｇスポ責め
ELSEIF SELECTCOM == 255
	;初回
	IF CFLAG:555 == 0 || CFLAG:555 == 1
		;恋慕
		IF TALENT:85
			PRINTFORMW 
		;それ以外
		ELSE
			PRINTFORMW 
		ENDIF
		SIF CFLAG:555 == 0
			CFLAG:555 = 2
		SIF CFLAG:555 == 1
			CFLAG:555 = 3
	;二回目以降
	ELSE
		;恋慕
		IF TALENT:85
			PRINTFORMW 
		;それ以外
		ELSE
			PRINTFORMW 
		ENDIF
	ENDIF
	RETURN 0
ENDIF

;-------------------------------------------------
;挿入子宮口責め（正常位・後背位・対面座位・背面座位繰り返し） CFLAG556
;騎乗子宮口責め（騎乗位繰り返し）
;-------------------------------------------------
;騎乗子宮口責め
IF SELECTCOM == 256 && PREVCOM == 34
	;初回
	IF CFLAG:556 == 0 || CFLAG:556 == 2
		;恋慕
		IF TALENT:85
			PRINTFORMW 
		;Ｖ感覚4以上
		ELSEIF ABL:4 > 3
			PRINTFORMW 
		;それ以外
		ELSE
			PRINTFORMW 
		ENDIF
		SIF CFLAG:556 == 0
			CFLAG:556 = 1
		SIF CFLAG:556 == 2
			CFLAG:556 = 3
	;二回目以降
	ELSE
		;恋慕
		IF TALENT:85
			PRINTFORMW 
		;Ｖ感覚4以上
		ELSEIF ABL:4 > 3
			PRINTFORMW 
		;それ以外
		ELSE
			PRINTFORMW 
		ENDIF
	ENDIF
	RETURN 0
;挿入子宮口責め
ELSEIF SELECTCOM == 256
	;初回
	IF CFLAG:556 == 0 || CFLAG:556 == 1
		;恋慕
		IF TALENT:85
			PRINTFORMW 
		;Ｖ感覚4以上
		ELSEIF ABL:4 > 3
			PRINTFORMW 
		;それ以外
		ELSE
			PRINTFORMW 
		ENDIF
		SIF CFLAG:556 == 0
			CFLAG:556 = 2
		SIF CFLAG:556 == 1
			CFLAG:556 = 3
	;二回目以降
	ELSE
		;恋慕
		IF TALENT:85
			PRINTFORMW 
		;Ｖ感覚4以上
		ELSEIF ABL:4 > 3
			PRINTFORMW 
		;それ以外
		ELSE
			PRINTFORMW 
		ENDIF
	ENDIF
	RETURN 0
ENDIF
