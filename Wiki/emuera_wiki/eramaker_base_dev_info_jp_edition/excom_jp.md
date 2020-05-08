# 命令

----------------------------------------

+ PRINT系
	+ PRINT(|V|S|FORM|FORMS)(|K|D)(|L|W)
	+ PRINTSINGLE(|V|S|FORM|FORMS)(|K|D)
	+ PRINT(|FORM)(C|LC)(|K|D)
	+ PRINTDATA(|K|D)(|L|W)
	+ PRINTBUTTON(|C|LC) <文字列式>, <数式 or 文字列式>
	+ PRINTPLAIN(|FORM)
	+ CUSTOMDRAWLINE <文字列>
	+ DRAWLINEFORM <FORM文字列>
	+ REUSELASTLINE <書式付文字列>
	+ CLEARLINE <消す行数>
	+ PRINT\_IMG <文字列式>
	+ PRINT\_RECT <数式>
	+ PRINT\_RECT <数式>, <数式>, <数式>, <数式>
	+ PRINT\_SPACE <数式>
+ 表示操作・フォント操作・表示仕様参照
	+ SETCOLOR <R>, <G>, <B>
	+ SETCOLOR <RGB>
	+ RESETCOLOR
	+ SETBGCOLOR <R>, <G>, <B>
	+ SETBGCOLOR <RGB>
	+ RESETBGCOLOR
	+ SETCOLORBYNAME <文字列>
	+ SETBGCOLORBYNAME <文字列>
	+ GETCOLOR
	+ GETDEFCOLOR
	+ GETBGCOLOR
	+ GETDEFBGCOLOR
	+ GETFOCUSCOLOR
	+ FONTBOLD
	+ FONTITALIC
	+ FONTREGULAR
	+ FONTSTYLE <数式>
	+ GETSTYLE
	+ CHKFONT <文字列式>
	+ SETFONT <文字列式>
	+ GETFONT
	+ FORCEKANA <数式>
	+ ALIGNMENT <キーワード>
	+ CURRENTALIGN
	+ REDRAW <数式>
	+ CURRENTREDRAW
	+ PRINTCPERLINE
	+ LINEISEMPTY
	+ BARSTR <変数>, <最大値>, <長さ>
	+ MONEYSTR <数値>{, <書式指定子>}
	+ SKIPDISP <数値>
	+ NOSKIP
	+ ENDNOSKIP
	+ ISSKIP
	+ MOUSESKIP
+ 文字列操作・参照
	+ TOUPPER <文字列式>
	+ TOLOWER <文字列式>
	+ TOHALF <文字列式>
	+ TOFULL <文字列式>
	+ TOSTR <数式>, <書式指定子>
	+ ISNUMERIC <文字列式>
	+ TOINT <文字列式>
	+ STRLEN <文字列>
	+ STRLENS <文字列式>
	+ STRLENFORM <書式付文字列>
	+ STRLENU <文字列>
	+ STRLENSU <文字列式>
	+ STRLENFORMU <書式付文字列>
	+ SUBSTRING <文字列式>, <数式>, <数式>
	+ SUBSTRINGU <文字列式>, <数式>, <数式>
	+ CHARATU <文字列式>, <文字位置>
	+ STRFIND <文字列式>, <文字列式>(, <数式>)
	+ STRFINDU <検索対象>, <検索する文字列>{, <開始インデックス>}
	+ STRCOUNT <検索対象文字列>, <検索文字列>
	+ SPLIT <文字列式>, <文字列式>, <文字列変数>
	+ REPLACE <置換対象文字列>, <置換対象パターン>, <置換後の文字列>
	+ ESCAPE <文字列>
	+ UNICODE <数式>
	+ ENCODETOUNI <対象文字列(FORM型文字列)>
+ 算術
	+ POWER <変数>, <数式>, <数式>
	+ ABS <数式>
	+ SIGN <数式>
	+ SQRT <数式>
	+ GETBIT <数式>, <数式>
	+ MAX <数式>(, <数式>...)
	+ MIN <数式>(, <数式>...)
	+ LIMIT <数式>, <数式>, <数式>
	+ INRANGE <数式>, <数式>, <数式>
	+ SETBIT <数値型変数>, <数式>{, <数式>,...}
	+ CLEARBIT <数値型変数>, <数式>{, <数式>,...}
	+ INVERTBIT <数値型変数>, <数式>{, <数式>,...}
+ キャラ操作・参照
	+ ADDCHARA <数式>(, <数式>, <数式>, ...)
	+ DELCHARA <数式>(, <数式>, <数式>, ...)
	+ SWAPCHARA <数式>, <数式>
	+ SORTCHARA <キャラクタ変数> {, <FORWARDorBACK>}
	+ GETCHARA <キャラ番号(NO:XXXの方)>
	+ ADDDEFCHARA
	+ ADDVOIDCHARA
	+ DELALLCHARA
	+ PICKUPCHARA <対象キャラ>(, <対象キャラ>, ....)
	+ EXISTCSV <数式>
	+ FINDCHARA <キャラクタ変数>, <式>(, <数式>, <数式>)
	+ FINDLASTCHARA <キャラクタ変数>, <式>(, <数式>, <数式>)
	+ COPYCHARA <数式>, <数式>
	+ ADDCOPYCHARA <数式>
+ 変数操作・変数参照・CSV参照
	+ VARSIZE <変数名>
	+ RESETDATA
	+ RESETGLOBAL
	+ RESET\_STAIN <数式>
	+ SWAP <変数1>, <変数2>
	+ CSVNAME <数式>
	+ CSVCALLNAME <数式>
	+ CSVNICKNAME <数式>
	+ CSVMASTERNAME <数式>
	+ CSVBASE <数式>, <数式>
	+ CSVCSTR <数式>, <数式>
	+ CSVABL <数式>, <数式>
	+ CSVTALENT <数式>, <数式>
	+ CSVMARK <数式>, <数式>
	+ CSVEXP <数式>, <数式>
	+ CSVRELATION <数式>, <数式>, <数式>
	+ CSVJULE <数式>, <数式>
	+ CSVEQUIP <数式>, <数式>
	+ CSVCFLAG <数式>, <数式>,
	+ GETNUM <変数名>, <文字列式>
	+ GETPALAMLV <数式>, <判定するLVの上限>
	+ GETEXPLV <数式>, <判定するLVの上限>
	+ FINDELEMENT <一次元配列変数>, <検索対象(変数と同型)>, <検索初位置>, <検索終位置>, <厳密一致かのフラグ>
	+ FINDLASTELEMENT <一次元配列変数>, <検索対象(変数と同型)>, <検索初位置>, <検索終位置>, <厳密一致かのフラグ>
	+ VARSET <変数名>{, <数式 or 文字列式>, <配列範囲初値>, <配列範囲終値+1>}
	+ CVARSET <キャラクタ変数>{, <数式>, <式>, <キャラクタ範囲初値>, <キャラクタ範囲終値+1>}
	+ ARRAYSHIFT <対象変数>, <ずらす数>, <ずらしてできた空白領域の初期値>{, <ずらす配列範囲の初値>, <ずらす配列要素の範囲の数>}
	+ ARRAYREMOVE <対象変数>, <消す範囲初値>, <消す要素数>
	+ ARRAYSORT <対象変数>{, <ソート方式(FORWARD or BACK)>, <開始インデックス>, <対象要素数>}
	+ ARRAYCOPY <コピー元変数名>, <コピー先変数名>
	+ ARRAYMSORT array1{, array2...}
	+ CUPCHECK <登録キャラクター番号>
+ セーブデータ操作
	+ SAVEDATA <数式>, <文字列式>
	+ LOADDATA <数式>
	+ DELDATA <数式>
	+ CHKDATA <数式>
	+ SAVENOS <数値変数>
	+ SAVEGLOBAL
	+ LOADGLOBAL
	+ OUTPUTLOG
	+ SAVECHARA str filename, str memo, int charano{, int charano2, ...}
	+ LOADCHARA str filename
	+ CHKCHARADATA str filename
	+ FIND\_CHARADATA str filename
	+ SAVETEXT str text, int fileNo{, int force\_savdir, int force\_UTF8}
	+ LOADTEXT int fileNo{, int force\_savdir, int force\_UTF8}
+ 日付・時刻取得
	+ GETTIME
	+ GETMILLISECOND
	+ GETSECOND
+ 入力・ウェイト
	+ FORCEWAIT
	+ INPUT {<数値>}
	+ INPUTS {<文字列>}
	+ TINPUT <数値>, <数値>{, <数値>, <文字列>}
	+ TINPUTS <数値>, <文字列式>{, <数値>, <文字列>}
	+ TWAIT <数値>, <数値>
	+ ONEINPUT {<数値>}
	+ ONEINPUTS {<文字列>}
	+ TONEINPUT <数値>, <数値>{, <数値>, <文字列>}
	+ TONEINPUTS <数値>, <文字列式>{, <数値>, <文字列>}
	+ WAITANYKEY
	+ INPUTMOUSEKEY {int time}
+ ループ・分岐構文
	+ FOR <数値型変数>, <数式>, <数式>{, <数式>}
	+ NEXT
	+ WHILE <数式>
	+ WEND
	+ DO
	+ LOOP <数式>
	+ SELECTCASE <式>
	+ CASE <CASE条件式>(, <CASE条件式>, <CASE条件式> ……)
	+ CASEELSE
	+ ENDSELECT
+ 乱数制御
	+ RANDOMIZE <数式>
	+ DUMPRAND
	+ INITRAND
+ デバッグ補助・システムフロー制御
	+ BEGIN <キーワード>
	+ CALLTRAIN <コマンド数>
	+ DOTRAIN <数式>
	+ THROW <FORM構文>
+ CALL・JUMP・GOTO系
	+ TRYJUMP <文字列> (, 引数1, 引数2……)
	+ TRYCALL <文字列> (, 引数1, 引数2……)
	+ TRYGOTO <文字列>
	+ JUMPFORM <書式付文字列> (, 引数1, 引数2……)
	+ CALLFORM <書式付文字列> (, 引数1, 引数2……)
	+ GOTOFORM <書式付文字列>
	+ TRYJUMPFORM <書式付文字列> (, 引数1, 引数2……)
	+ TRYCALLFORM <書式付文字列> (, 引数1, 引数2……)
	+ TRYGOTOFORM <書式付文字列>
	+ CALLF <文字列> (, 引数1, 引数2……)
	+ CALLFORMF <書式付文字列> (, 引数1, 引数2……)
	+ CALLEVENT <文字列>
+ CALL・JUMP・GOTO系2 (TRYC-CATCH-ENDCATCH)
	+ TRYCJUMP <文字列> (, 引数1, 引数2……)
	+ TRYCCALL <文字列> (, 引数1, 引数2……)
	+ TRYCGOTO <文字列>
	+ TRYCJUMPFORM <書式付文字列> (, 引数1, 引数2……)
	+ TRYCCALLFORM <書式付文字列> (, 引数1, 引数2……)
	+ TRYCGOTOFORM <書式付文字列>
	+ CATCH
	+ ENDCATCH
	+ TRYCALLLIST
	+ TRYJUMPLIST
	+ TRYGOTOLIST
	+ FUNC <文字列> (, 引数1, 引数2……)
	+ ENDFUNC
+ RETURN系
	+ RETURN <数式>(, <数式>, <数式>, ...)
	+ RETURNFORM <書式付文字列>(, <書式付文字列>, <書式付文字列>, ...)
	+ RETURNF <式>
+ DEBUG系
	+ DEBUGPRINT <文字列>
	+ DEBUGPRINTL <文字列>
	+ DEBUGPRINTFORM <書式付文字列>
	+ DEBUGPRINTFORML <書式付文字列>
	+ DEBUGCLEAR
	+ ASSERT <数式>
+ ツールチップ系
	+ TOOLTIP\_SETCOLOR <数式>, <数式>
	+ TOOLTIP\_SETDELAY <数式>
	+ TOOLTIP\_SETDURATION int msDuration
+ HTML系
	+ HTML\_PRINT <文字列式>
	+ HTML\_TAGSPLIT <文字列式>(, <数値変数>, <文字列変数>)
+ AWAIT関連
	+ AWAIT {int time}
	+ GETKEY int vkey
	+ GETKEYTRIGGERED int vkey
	+ MOUSEX
	+ MOUSEY
	+ ISACTIVE
+ 画像処理関連
	+ GCREATE int ID, int width, int height
	+ GCREATEFROMFILE int ID, str filepath
	+ GDISPOSE int ID
	+ GCLEAR int ID, int cARGB
	+ GFILLRECTANGLE int ID, int x, int y, int width, int height
	+ GDRAWG int destID, int srcID, int destX, int destY, int destWidth, int destHeight, int srcX, int srcY, int srcWidth, int srcHeight
	+ GDRAWG int destID, int srcID, int destX, int destY, int destWidth, int destHeight, int srcX, int srcY, int srcWidth, int srcHeight, var cm
	+ GDRAWGWITHMASK int destID, int srcID, int maskID, int destX, int destY
	+ GDRAWSPRITE int ID, str sprName
	+ GDRAWSPRITE int ID, str sprName, int destX, int destY
	+ GDRAWSPRITE int ID, str sprName, int destX, int destY, int destWidth, int destHeight
	+ GDRAWSPRITE int ID, str sprName, int destX, int destY, int destWidth, int destHeight, var cm
	+ GSETCOLOR int ID, int cARGB, int x, int y
	+ GSETBRUSH int ID, int cARGB
	+ GSETFONT int ID, str fontName, int fontSize
	+ GSETPEN int ID, int cARGB, int penWidth
	+ GCREATED int ID
	+ GWIDTH int ID
	+ GHEIGHT int ID
	+ GGETCOLOR int ID, int x, int y
	+ GSAVE int ID, int fileNo
	+ GLOAD int ID, int fileNo
	+ SPRITECREATE str spriteName, int gID
	+ SPRITECREATE str spriteName, int gID, int x, int y, int width, int height
	+ SPRITEANIMECREATE str spriteName, int width, int height
	+ SPRITEANIMEADDFRAME string spriteName, int gID, int x, int y, int width, int height, int offsetx, int offsety, int delay
	+ SPRITEDISPOSE string spriteName
	+ SPRITEGETCOLOR string spriteName, int x, int y
	+ SPRITECREATED str spriteName
	+ SPRITEWIDTH str spriteName
	+ SPRITEHEIGHT str spriteName
	+ SPRITEPOSX str spriteName
	+ SPRITEPOSY str spriteName
	+ SPRITESETPOS str spriteName, int posx, int posy
	+ SPRITEMOVE str spriteName, int movex, int movey
	+ CBGSETG int ID, int x, int y, int zdepth
	+ CBGSETSPRITE str spriteName, int x, int y, int zdepth
	+ CBGCLEAR
	+ CBGCLEARBUTTON
	+ CBGREMOVERANGE int zmin, int zmax
	+ CBGREMOVEBMAP
	+ CBGSETBMAPG int ID
	+ CBGSETBUTTONSPRITE int button, str spriteName, str spriteNameB, int x, int y,int zdepth
	+ CBGSETBUTTONSPRITE int button, str spriteName, str spriteNameB, int x, int y,int zdepth, str tooltipmes
	+ SETANIMETIMER int time
+ 未整理項目
	+ CLEARTEXTBOX
	+ STRDATA
	+ STOPCALLTRAIN

----------------------------------------

## PRINT系

### PRINT(|V|S|FORM|FORMS)(|K|D)(|L|W)

PRINT系の基本となる命令です。

1つ目の括弧内のキーワードは引数タイプを指定します。

+ なし - (<文字列>)
+ V - (<数式> <数式> ,<数式> ……)
+ S - <文字列式>
+ FORM - (<書式付文字列>)
+ FORMS - <書式付文字列式>

2つ目の括弧内のキーワードの"K"はFORCEKANA命令の適用を指定します。またキーワード"D"はSETCOLOR命令を無視することを指定します。ver1.736現在、キーワードKとDを同時に指定することはできません。

+ なし - FORCEKANAを無視し、SETCOLORで指定された色で描画します。
+ K - FORCEKANAを適用して描画します。
+ D - SETCOLORを無視してコンフィグで指定されたディフォルト色で描画します。

3つ目の括弧内のキーワードは描画後の改行、WAITの有無を指定します。

+ なし - PRINTのみで改行やWAITは行いません。
+ L - PRINT後、改行します。
+ W - PRINT後、改行しWAIT命令を行います。

これらの組み合わせにより、例えばPRINTSDWであれば、引数として<文字列式>を指定し、ディフォルト色で描画し、PRINT後にWAIT命令を行うことを意味します。

### PRINTSINGLE(|V|S|FORM|FORMS)(|K|D)

PRINTSINGLE系はPRINTLとほぼ同じですが、PRINTSINGLE系は文字列を折り返さず、必ず1行で表示します。

画面端を超えた文字は描画されません。

また、自動的に改行が付与されるため、(|L|W)キーワードはありません。

他のキーワードの意味はPRINT系と同じです。

### PRINT(|FORM)(C|LC)(|K|D)

PRINTC系命令です。

コンフィグ"PRINTCの文字数"（初期値25）で指定した文字数になるように半角スペースを補ってPRINTする命令です。

なお、EmueraではPRINTされた文字列のボタン化処理の中でPRINTC系命令を多少特別扱いしています。

1つ目の括弧内のキーワードは引数タイプを指定します。

+ なし - <文字列>
+ FORM - <書式付文字列>

2つ目の括弧内のキーワードは揃える位置を指定します。

+ C - 右に揃えます（左側に半角スペースを追加します）
+ LC - 左に揃えます。

3つ目の括弧内のK,DはPRINT系と同じです。

### PRINTDATA(|K|D)(|L|W)

PRINTDATA系命令です。 私家改造版readmeによれば、

```
書式：PRINTDATA (数値変数：省略可)
　　　　DATA (文字)
　　　　DATAFORM (FORM文字列)
　　　　DATALIST
　　　　　(DATA or DATAFORMの羅列)
　　　　ENDLIST
　　　ENDDATA
内容：DATA、DATAFORMおよびDATALIST～ENDLISTで指定した文字列を確率均一でランダムで表示
　　　IFとRANDを使わずにランダム表示を実装可能
　　　引数に数値変数を指定した場合は表示された変数DATAの番号が入ります
　　　表示された文字列によって後の処理をいじりたい場合にどうぞ
　　　DATALIST～ENDLIST内ではDATAorDATAFORM1個が1行に相当します
```

とのことです。

K、D、L、Wキーワードの効果はPRINT系と同じです。

PRINTDATA系～ENDDATAの内部にDATA系による表示データが与えられてない場合、何もせずに次に進みます。

PRINTDATA系～ENDDATA、およびDATALIST～ENDLIST内に上記の文法以外の記述をすることはできません。

### PRINTBUTTON(|C|LC) <文字列式>, <数式 or 文字列式>

PRINTBUTTON命令はマウスでクリックできるボタンを生成するための命令です。

書式としてはPRINTS命令に近いですが、第二引数としてクリックされたときに入力する数字または文字を指定します。 第一引数に改行コードが入っている場合オミットされ改行されません。

Emueraは"[300] セーブ"のように[]でくくられた数字とその前後の文字列を自動的にボタンに変換します。

このようなボタンを自動ではなく強制的に生成するための命令がPRINTBUTTONです。

この命令は例えば以下のような場合に有用です。

`
PRINT これでいい？ [0] はい    [1] いいえ
INPUT
`

このような行についてはEmueraはボタンを正しく認識できず、"これでいい？ [0] はい"というボタンと"[1] いいえ"というボタンになってしまいます。

PRINTBUTTONを用いて書き直すと以下のようになります。

```
PRINTS "これでいい？ "
PRINTBUTTON "[0] はい", 0
PRINTS "     "
PRINTBUTTON "[1] いいえ", 1
INPUT
```

（PRINT命令の代わりにPRINTSを使っていますがこれは半角スペースの数を明らかにするためです）

このようにすると"これでいい？ "はボタンではなくなり、"[0] はい"と"[1] いいえ"だけがボタンになります。

なお、PRITNBUTTON命令では表示する文字列に[0]や[1]などが含まれていることは必須ではありませんが、対応する数字を全く表示しないとテンキーなどで操作している方を戸惑わせることになるでしょう。 従来通り[0]などを表記することを勧めます。

また、PRINTBUTTON命令では数字だけでなく文字列を入力するボタンを作成することができます。 そうして作成したボタンはINPUTS命令の実行時にクリックすることができます。

```
PRINTL 名前を入力してください。
PRINTBUTTON "[ほげほげ] ", "ほげほげ"
PRINTBUTTON "[ぷげぷげ] ", "ぷげぷげ"
PRINTBUTTON "[ふうばあ] ", "ふうばあ"
INPUTS
```

括弧内のキーワードは文字を揃える位置を指定します。

+ なし - 揃えません
+ C - PRINTCと同様に右側に揃えます
+ LC - PRINTLCと左に揃えます

### PRINTPLAIN(|FORM)

引数の文字列を平文として出力します。この時ボタン文字列（0など）があってもボタン化しません。

括弧内のキーワードは引数タイプを指定します。

+ なし - <文字列>
+ FORM - <書式付文字列>

### CUSTOMDRAWLINE <文字列>

### DRAWLINEFORM <FORM文字列>

指定した文字列を使って1行の区切りを表示します。 DRAWLINEFORMではFORM構文に対応しています。

### REUSELASTLINE <書式付文字列>

最終行を指定した書式付き文字列で書き換えるが、

これを使って書き換えた行は、次の行が追加されるとそれに置き換わる

基本的にはINPUT、INPUTSのループ処理の中でのみ使用するもの

引数はPRINTFORMと同様の書式を使用可

なお、REUSELASTLINE （この半角スペース必須）とすれば、警告文なしで空行にできます

```
　　$INPUT\_LOOP
　　INPUT
　　IF RESULT != 0
　　　　;!;CLEARLINE 1
　　　　;!;REUSELASTLINE 無効ですよ
　　　　GOTO INPUT\_LOOP
　　ENDIF
```

のように、GOTO INPUT\_LOOPの前にREUSELASTLINEを呼び出すと、

前の入力が画面から消去され、次の入力は前の入力と同じ行に表示される

これによって、無効な入力が繰り返されても、行数が増えず、

気づいたら選択肢が画面外に…なんて事態は防げる…はず

ちなみに@USERXXX系関数の条件分岐の最後に

（対象は@USERCOM、@USERSHOP、@USERABLUPの3つ）

```
;!;ELSE
　　;!;REUSELASTLINE
ENDIF
```

とやっておくと…？

(Emuera専用なら;!;は必要なし)

### CLEARLINE <消す行数>

指定した行数の文字列を削除します（行の数え方はLINECOUNTと同様です）

行数はPRINTL等で改行が行われるまでのものを1つの行とします。

なお、長い文字列が複数行に分割されたものもまとめて1行として扱うので気をつけてください。

### PRINT\_IMG <文字列式>

行中に指定した画像を表示します。

HTML\_PRINT命令の`<img>`タグに相当します。

### PRINT\_RECT <数式>

行中に横幅がフォントサイズの引数％である長方形を表示します。

SETCOLOR命令によりフォント色と同様に色を変えられます。

HTML\_PRINT命令の`<shape type='rect'>`タグに相当します。

### PRINT\_RECT <数式>, <数式>, <数式>, <数式>

行中にx,y,横幅,縦幅がそれぞれ引数％である長方形を表示します。

SETCOLOR命令によりフォント色と同様に色を変えられます。

HTML\_PRINT命令の`<shape type='rect'>`タグに相当します。

### PRINT\_SPACE <数式>

フォントサイズの引数％分だけ何も表示しないスペースを作ります。

HTML\_PRINT命令の`<shape type='space'>`タグに相当します。

----------------------------------------

## 表示操作・フォント操作・表示仕様参照

### SETCOLOR <R>, <G>, <B>

### SETCOLOR <RGB>

### RESETCOLOR

文字色を指定した色に変更、適用はRESETCOLORが呼ばれるまで。

指定方法はRGB形式になります

SETCOLORで指定した色はRESETCOLORでリセットすることができます

現在の背景色はGETCOLORで、デフォルトの背景色はGETDEFCOLORで取得することができます。

1.731以降ではSETCOLORに0xRRGGBB形式で指定できるようになりました。

```
SETCOLOR 255, 128, 0
SETCOLOR 0xFF8000
```

これはどちらの行も同じ意味になります。 GETCOLOR命令で取得できる値は後者です。

### SETBGCOLOR <R>, <G>, <B>

### SETBGCOLOR <RGB>

### RESETBGCOLOR

背景色を指定した色に変更する命令です。

基本的な仕様はSETCOLOR・RESETCOLORと同様ですが、

安全のため変更後0.2秒以内に再変更する場合は0.2秒経過まで強制WAITになります。

現在の背景色はGETBGCOLORで、デフォルトの背景色はGETDEFBGCOLORで取得することができます。

### SETCOLORBYNAME <文字列>

### SETBGCOLORBYNAME <文字列>

定義済み色名からフォント表示色や背景色を指定する命令です。

他の仕様はすべてSETCOLOR・SETBGCOLORと同様です。 引数は色名です。定義済み色名についてはKnownColor列挙体 に準拠しておりますので、そちらを参照してください。

### GETCOLOR

現在使用している文字色コードをRESULT:0に代入します。

戻り値は16進数で0xRRGGBBとなります。

例えばオレンジ色(R,G,B) = (255, 128, 0)であれば0xFF8000(10進数で16744448)を返します。

色と数字の対応はweb colorについて解説しているWebサイトを参考にするとよいでしょう。

1.731での変更により、SETCOLOR命令もSETCOLOR 0xFF8000のような形式で指定できるようになりました。

### GETDEFCOLOR

コンフィグで指定している文字色コードをRESULT:0に代入します。

基本的な仕様はGETCOLORと同様です。

### GETBGCOLOR

現在使用している背景色コードをRESULT:0に代入します。

基本的な仕様はGETCOLORと同様です。

### GETDEFBGCOLOR

コンフィグで指定している背景色コードをRESULT:0に代入します。

基本的な仕様はGETCOLORと同様です。

### GETFOCUSCOLOR

コンフィグで指定している選択中文字色コードをRESULT:0に代入します。

基本的な仕様はGETCOLORと同様です。

### FONTBOLD

### FONTITALIC

### FONTREGULAR

以降の文字を指定したスタイルに変更する

BOLDとITALICは重複可（太字斜体）

REGULARを呼ぶと、太字・斜体指定が解除されます

### FONTSTYLE <数式>

FONTSTYLE以降の文字を指定したスタイルに変更します。

0であれば通常、1なら太字、2なら斜体、4なら打ち消し線、8なら下線が引かれます。

これらはビットごとに組み合わせることができます。

例えばFONTSTYLE 3なら太字かつ斜体になります。

FONTBOLD、FONTITALICは現在のスタイルに太字、斜体スタイルを加えます。

FONTREGULARはFONTSTYLE 0と等価です。つまり通常のスタイルに戻します。

```
	FONTSTYLE 1 + 2
	PRINTL 太字＋斜体
	FONTSTYLE 5
	PRINTL 太字＋打ち消し
	FONTITALIC
	PRINTL 太字＋斜体＋打ち消し
	FONTSTYLE 0
	PRINTL 通常
<表示結果は実際に試してみてください>
```

### GETSTYLE

現在のフォントのスタイル（太字、斜線など）をRESULT:0に代入します。

これはSETSTYLE命令で指定した値と同じです。

SETSTYLE命令が行われていない時は0を返します。

### CHKFONT <文字列式>

指定された名前のフォントがインストールされているかどうかを調べます。

インストールされていれば1、されていなければ0がRESULT:0に代入されます。

使用例はSETFONT命令を参照してください。

### SETFONT <文字列式>

SETFONT命令以降の文字列表示に指定された名前のフォントを用います。

引数を省略、または空文字列を指定した場合、emuera.configに指定された標準のフォントに戻します。

指定されたフォントがインストールされていない場合、代わりに"Microsoft Sans Serif"が使用されます。

インストールされていない可能性があるフォントを指定する場合はSETFONTの前にCHKFONT命令を行ってください。

```
PRINTL abc123あいう(標準フォント)
CHKFONT "ＭＳ Ｐゴシック"
IF RESULT
	SETFONT "ＭＳ Ｐゴシック"
	PRINTL abc123あいう(ＭＳ Ｐゴシック)
ENDIF
CHKFONT "ＭＳ 明朝"
IF RESULT
	SETFONT "ＭＳ 明朝"
	PRINTL abc123あいう(ＭＳ 明朝)
ENDIF
STR:0 = ＭＳ Ｐ明朝
CHKFONT STR:0
IF RESULT
	SETFONT STR:0
	PRINTL abc123あいう(ＭＳ Ｐ明朝)
ENDIF
SETFONT
```

### GETFONT

現在使用しているフォントの名前をRESULTS:0に代入します。

これはSETFONT命令で指定した名前と同じです。

SETFONT命令が行われていない時はemuera.configで指定されている標準のフォントの名前を代入します。

### FORCEKANA <数式>

表示命令のひらがな・カタカナを指定します。

キーワード"K"を含む各種PRINT系命令で有効になります。

引数で指定した値により、以下の影響があります。

+ 0:変換を行わない
+ 1:ひらがな→カタカナ
+ 2:カタカナ→ひらがな（全角のみ）
+ 3:カタカナ→ひらがな（全角・半角両方とも）

### ALIGNMENT <キーワード>

ALIGNMENT以降の行を指定した位置に揃えます。

キーワードには"LEFT"、"CENTER"、"RIGHT"のいずれかを指定します。

通常の表示はALIGNMENT LEFTであり、左端に揃えられます。

ALIGNMENT CENTERによりタイトル画面のように中央に揃えることができます。

ALIGNMENTが適用されるのは改行された時点です。

```
ALIGNMENT RIGHT
PRINT あああ
ALIGNMENT CENTER
PRINTL いいい
ALIGNMENT LEFT
```

このようにすると、"あああいいい"という文字列が中央揃えで表示されます。

現在のALIGNMENTはCURRENTALIGNで取得することができます。

### CURRENTALIGN

現在のALIGNMENTをRESULTS:0に代入します。

返値はALIGNMENT命令で指定した文字列と同じです（大文字）。

ALIGNMENT命令が行われていない時は初期値のLEFTを返します。

### REDRAW <数式>

描画制御命令です。

引数に0を指定するとユーザーが入力を必要とするタイミングでのみ描画を行うようにします。

引数に1を指定すると通常通り、コンフィグの"フレーム毎秒"で指定されたタイミングで描画を行います。

引数に2を加えると(REDRAW 2やREDRAW 3など)、上記の効果に加え、REDRAW命令を行った瞬間に強制的に描画を行います。

現在のREDRAW状態（0または1）はCURRENTREDRAWで取得することができます。

### CURRENTREDRAW

現在のREDRAW状態をRESULT:0に代入します。

返値は通常時は1、REDRAW命令を用いて描画を抑制した時は0になります。

### PRINTCPERLINE

コンフィグ"PRINTCを並べる数"で指定された数をRESULT:0に代入します。標準は3です。

### LINEISEMPTY

現在PRINTしている行が空行かどうかを判断する命令です。

この命令を実行した時点で「PRINTL 」を行おうとした場合、

その結果がただの空行になる場合には1を、そうでない場合は0をRESULT:0に代入します。

PRINTC系で条件に応じたボタンを順次書き連ねる場合に、最後にこの命令を使用することで、

表示されるボタンがあるかないかを判別し、なければ専用の表示をするといったことが可能です

### BARSTR <変数>, <最大値>, <長さ>

与えられた引数と同一の引数のBAR命令で表示される文字列と同じ物をRESULTS:0に代入します。

### MONEYSTR <数値>{, <書式指定子>}

引数で与えられた数値に対して、設定されたお金の単位を付けた文字列をRESULTS:0に代入します。

単位の前置・後置も自動的に処理します。

第2引数はTOSTR命令と同様の数値の文字列化における変換書式指定子となります。

### SKIPDISP <数値>

以下、私家改造版更新履歴より、

```
PRINT等の画面出力命令およびWAIT、TWAITなどの命令を無視するフラグを設定する命令SKIPDISP追加
　書式：SKIPDISP <数値>
　引数：0 　　無視しないようにする
　　　　0以外 無視するようにする
　内容：このフラグを立てると、PRINT等の出力が一切行われなくなる
　　　　また、このフラグが立ってる間にINPUTおよびINPUTSに達した場合は
　　　　ユーザーが何をすればいい知る術がないこと、また飛ばせば無限ループに入る可能性が高いため
　　　　警告文と対処法を明示した上でエラーになるようにしてあります
　　今一般に使われる口上の実装では口上の非表示が可能な場合、
　　表示と非表示でコマンドの結果が変わったり、動作が変わってしまう場合がある
　　そこで、これを立てた上で口上を呼び出せば、表示はされることなくそれ以外の処理が行われるため
　　表示/非表示で同じ動作を期待できる
　　INPUT/INPUTSがかぶる場合は上のNOSKIP～ENDNOSKIPで囲んだり、
　　SKIPDISP 0しておいて、INPUT処理後に再度SKIPDISP 1するなりの対策があります（一応前者推奨）
　　ちなみに今無視するフラグが立ってるかはISSKIP()式中関数で取得できます
```

ver1.808から、SIF文の直後に置いても動作するようになりました。 なお、SKIPDISPを使用すると引数に関係なくRESULT:0が0にリセットされますが仕様となります。

### NOSKIP

### ENDNOSKIP

以下、私家改造版更新履歴より、

```
表示関係無視フラグを無視する区間を指定できるNOSKIP～ENDNOSKIP実装
　　この2つで囲った区間はSKIPDISP 1の状態でも表示等される
　　主にINPUTが必要な場合に使用するとよい
　　また、この命令はSKIPDISPの状態に影響しないので、
　　SKIPDISPフラグが立ちうる環境下のコード（例えば表示/非表示のある口上関係）では
　　これを使うと、絶対に表示する必要がある場所をきちんと表示できるようになります
```

### ISSKIP

SKIPDISPのフラグが0以外（PRINT等の出力を無視）なら1を、そうでなければ0をRESULT:0に代入します

### MOUSESKIP

右クリックが押されてWAITスキップの状態になっているなら1を、そうでなければ0をRESULT:0に代入します

マクロ処理時のスキップ中は0を返します

マクロ処理のスキップと右クリックが競合した場合はマクロを優先し0を返します

## 文字列操作・参照

### TOUPPER <文字列式>

### TOLOWER <文字列式>

### TOHALF <文字列式>

### TOFULL <文字列式>

引数の文字列に特定の変換をかけた結果をRESULTS:0に代入します。

TOUPPERはアルファベットを大文字にした結果を、TOLOWERは小文字化した結果を代入します

TOHALFは全角文字を半角にしますが、対応する半角文字がない全角文字はそのままです。

TOFULLは半角文字を全角にします。

### TOSTR <数式>, <書式指定子>

数値を文字列に変換する命令です。

変換したい数字を第一引数に、変換の書式を文字列で第二引数に指定します。

第二引数は省略できますが、省略した場合はPRINTFORMの{}内などと同じように単に文字列になります。

この関数は内部でC#のInt64.ToString()関数を呼んでおり、C#と同じ書式指定ができます。第二引数が適切でない場合、エラーになります。

簡単な書式指定の例は同名の[式中で使える関数](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/exmeth_jp.md)を確認してください。 書式指定の詳細はC#の数値書式指定文字列について解説しているWebサイトを参考にして下さい。

### ISNUMERIC <文字列式>

文字列を数値としてパース可能か（TOINTで値を取れるか）を判断します。

引数を数値として解釈できる場合1を、それ以外の場合0をRESULT:0に代入します。

### TOINT <文字列式>

引数文字列を数値化してRESULT:0に代入します。ただし、半角数字で構成された文字列のみ数値化できます。

引数を数値として解釈できない場合、0が代入されます。全角数字の場合も同様です。

### STRLEN <文字列>

### STRLENS <文字列式>

### STRLENFORM <書式付文字列>

文字列の長さを測定し、RESULT:0に代入します。

長さはSHIFT-JISでのバイト数です。つまり全角文字を2文字と数えます。

```
	STRLEN ABCあいう
	PRINTFORML <TEST1> = {RESULT}
	STR:0 = ABCあいう
	STRLENS STR:0
	PRINTFORML <TEST2> = {RESULT}
	STRLENFORM abc%STR:0%
	PRINTFORML <TEST3> = {RESULT}

	;STRLENSは文字列式にも対応
	STRLENS "abc" + STR:0
	PRINTFORML <TEST4> = {RESULT}
	WAIT
　結果
　<TEST1> = 9
　<TEST2> = 9
　<TEST3> = 12
　<TEST4> = 12
```

### STRLENU <文字列>

### STRLENSU <文字列式>

### STRLENFORMU <書式付文字列>

STRLEN、STRLENS、STRLENFORMのUnicode版です。違いは全角文字も1文字と数えることです。

### SUBSTRING <文字列式>, <数式>, <数式>

指定した文字列式の部分文字列をRESULTS:0に代入します。

開始位置は文字列の最初が0です。元文字列の長さより後を指定した場合、空文字列""が返されます。

文字数はSHIFT-JISでのバイト数で指定します。つまり全角文字を2文字と数えます。

文字数に負の値を指定するか、元文字列の終端より後の位置を指定した場合、開始位置から最後までの文字列を返します。

開始位置または終了位置で文字を切ることができない場合（全角文字の途中を指している場合）、1つ後ろを指定されたと判断されます。

このことで指定した文字数よりも1文字分だけ長い文字列が返される場合があるので注意してください。

```
STR:0 = 01234あいうえお
SUBSTRING STR:0, 0, -1
PRINTFORML <TEST1> = %RESULTS:0%
SUBSTRING STR:0, 1, 3
PRINTFORML <TEST2> = %RESULTS:0%
SUBSTRING STR:0, 6, 3
PRINTFORML <TEST3> = %RESULTS:0%
WAIT
; 結果
<TEST1> = 01234あいうえお
<TEST2> = 123
<TEST3> = いう
```

### SUBSTRINGU <文字列式>, <数式>, <数式>

SUBSTRINGのUnicode版です。違いは全角文字も1文字と数えることです。

### CHARATU <文字列式>, <文字位置>

以下、私家改造版更新履歴より、

```
文字列中の任意の文字数目の文字を取得する式中関数CHARATU追加
　書式：CHARATU(<参照文字列>, [取得文字位置])
　内容：文字列の指定した位置の文字を取得する
　　　　処理系はユニコードとなります
```

### STRFIND <文字列式>, <文字列式>(, <数式>)

文字列検索命令です。

第一引数には検索される対象の文字列を文字列式で、

第二引数には検索する文字列を文字列式で指定します。

RESULT:0に全角文字を2文字と数え、0から始まるインデックスが代入されます。見つからなかった場合は-1です。

```
STR:0 = abcdefghi
STR:1 = あいうえお
STR:2 = うえ
STRFIND STR:0, "cde"
PRINTFORML <TEST1> = {RESULT:0}
STRFIND STR:1, "いうえ"
PRINTFORML <TEST2> = {RESULT:0}
STRFIND STR:1, STR:2
PRINTFORML <TEST3> = {RESULT:0}
STRFIND STR:1, "か"
PRINTFORML <TEST4> = {RESULT:0}
;結果
<TEST1> = 2
<TEST2> = 2
<TEST3> = 4
<TEST4> = -1
```

1.712以降、STRFIND命令に第3引数が指定できるようにしました。

第3引数には検索の開始位置を0から始まるインデックスで指定します。

```
STRFIND "abcdeabced","a",3
```

上の行の結果、RESULTには5が代入されます。

"a"は0の位置にもありますが、第3引数により検索は3の位置("d")から開始されるので最初に見つかる"a"は5の位置になります。

### STRFINDU <検索対象>, <検索する文字列>{, <開始インデックス>}

以下、私家改造版更新履歴より、

```
STRFINDのユニコード版STRFINDU実装
　書式：STRFINDU(<検索対象>, <検索する文字列>{, <開始インデックス>})
　内容：STRFINDのユニコード版、返り値の文字の位置と開始インデックスがユニコードでのカウントになっている
```

### STRCOUNT <検索対象文字列>, <検索文字列>

文字列中の指定部分文字列の数を取得する命令です。ヒットした数をRESULT:0に代入します。

検索文字列の書式はC#の正規表現の仕様に準じます。

### SPLIT <文字列式>, <文字列式>, <文字列変数>

第1引数で指定した文字列を、第2引数で指定した文字列を区切りとして分割し、第3引数で指定した文字列配列変数に代入します。

また、分割した数をRESULTに代入します。

第3引数で指定する変数は配列変数でなければなりません。

```
SPLIT "あい,うえ,,お", ",", LOCALS
```

上記のスクリプトの結果、LOCALS:0に"あい"、LOCALS:1に"うえ"、LOCALS:2に""（空文字列）、LOCALS:3に"お"、RESULTに4が代入されます。

分割後の要素数が第3引数に代入可能な要素数を超えた分については代入が行われません

RESULTには実際の分割数が入れられるのでそちらで判別してください

### REPLACE <置換対象文字列>, <置換対象パターン>, <置換後の文字列>

以下、私家改造版更新履歴より、

```
文字列置換命令REPLACE実装
　書式：REPLACE(<置換対象文字列>, <置換対象パターン>, <置換後の文字列>)
　内容：置換対象文字列を置換対象パターンで検索し、ヒットしたら置換後の文字列で置き換えます。結果はRESULTSに代入されます。
　　内部処理は思いっきり正規表現です。第２引数はC#の正規表現の仕様に準じて動作します。
　　そのため、()や[]、$、/.\*+等の正規表現で用いられる記号はエスケープ必須となります
```

### ESCAPE <文字列>

以下、私家改造版更新履歴より、

```
文字列を正規表現用にエスケープする式中関数ESCAPEを追加
　書式：ESCAPE([文字列])
　内容：文字列が正規表現中で平文となるように、引数中の文字列の正規表現メタ文字をエスケープして返す
```

### UNICODE <数式>

RESULTS:0に引数の値に対応したunicodeの文字を代入する命令です。

例えば、以下のスクリプトは白抜きのハートマークを表示します。

ただし、この関数ではサロゲートペアを扱うことはできません。

また、フォントが対応していなければ表示できません。

```
UNICODE 0x2661
PRINTFORMW %RESULTS%
```

なお、EmueraのUnicode対応は完全ではないことに注意してください。

例えばEmueraはサロゲートペアを使用した場合、正確な動作は保証できません。

### ENCODETOUNI <対象文字列(FORM型文字列)>

以下、私家改造版更新履歴より、

```
文字列に対してUNICODEのバイトコードを返すENCODETOUNI実装
　書式：ENCODETOUNI <対象文字列(FORM型文字列)>
　内容：与えられた文字列をユニコードにエンコードしてそのバイトを数値として返す
　　　　RESULT:0 　文字数
　　　　RESULT:1～ バイト数値
```

----------------------------------------

## 算術

### POWER <変数>, <数式>, <数式>

指定した変数に累乗を代入します。

例えばPOWER A, X, Y ならば、AにXのY乗が代入されます。

演算結果がオーバーフローを起こすとエラーになります。

```
X = 11
Y = 2
POWER A, X, 2
PRINTFORML <TEST1> = {A}
POWER CFLAG:2, X + 1, Y + 1
PRINTFORML <TEST2> = {CFLAG:2}
; 結果(TARGETは適切に設定されているとする)
<TEST1> = 121
<TEST2> = 1728
```

### ABS <数式>

引数の絶対値をRESULT:0に代入します。

### SIGN <数式>

引数の符号をRESULT:0に代入します。

負の値なら-1、0なら0、正の値なら1を代入します。

### SQRT <数式>

引数の平方根をRESULT:0に代入します。

### GETBIT <数式>, <数式>

引数の特定のビットを取得し、RESULT:0に代入します。

第1引数に対象となる数字を、第2引数には取得したいビットの位置を指定します。 第2引数に指定できる値は0～63までで、範囲外の数値を指定するとエラーになります。

第2引数が定数の場合、例えば5であれば、

```
GETBIT X, 5
RESULT = (X & 1p5) != 0
```

2つの行は同じ結果になります。

### MAX <数式>(, <数式>...)

引数の中で最大の数値をRESULT:0に代入します。

### MIN <数式>(, <数式>...)

引数の中で最小の数値をRESULT:0に代入します。

### LIMIT <数式>, <数式>, <数式>

第一引数の値をRESULT:0に代入します。

ただし、第一引数が第二引数より小さいなら第二引数の値を、第三引数より大きいなら第三引数を返します。

例えばAに X - Y を代入したいが、代入後の値が0以上100以下であってほしい場合、通常は以下のように書きます。

```
A = X - Y
SIF A < 0
	A = 0
SIF A > 100
	A = 100
```

LIMIT命令を使うとこれを二行にまとめることができます。

```
LIMIT X - Y, 0, 100
A = RESULT
```

### INRANGE <数式>, <数式>, <数式>

第一引数の値が第二引数以上かつ第三引数以下であれば1を、第一引数が第二引数より小さい、または第三引数より大きいなら0をRESULT:0に代入します。

### SETBIT <数値型変数>, <数式>{, <数式>,...}

### CLEARBIT <数値型変数>, <数式>{, <数式>,...}

### INVERTBIT <数値型変数>, <数式>{, <数式>,...}

ビット操作関数です。

第1引数で指定した変数の、第2引数以降で指定した位置のビットを操作します。

SETBITはビットを1にし、CLEARBITは0にし、INVERTBITは反転させます。

```
	SETBIT X, A
	CLEARBIT Y, B
	INVERTBIT Z, C
```

の結果は以下と同じです。

```
	X |= 1 << A
	Y &= ~(1 << B)
	Z ^= 1 << C
```

また、これらのビット操作関数の書式はGETBIT関数と対応しています。

"SETBIT X, A" で変更したビットをGETBIT(X, A)で参照することができます。

----------------------------------------

## キャラ操作・参照

### ADDCHARA <数式>(, <数式>, <数式>, ...)

### DELCHARA <数式>(, <数式>, <数式>, ...)

eramakerからある命令ですが、一度にたくさんのキャラを足したり消せるようになりました

### SWAPCHARA <数式>, <数式>

指定した二人のキャラクタの登録番号を入れ替えます。

```
;MASTERしかいない状態とする
ADDCHARA 10
ADDCHARA 11
PRINTFORML NO:1 = {NO:1}, NO:2 = {NO:2}
SWAPCHARA 1,2
PRINTFORML NO:1 = {NO:1}, NO:2 = {NO:2}
;結果
NO:1 = 10, NO:2 = 11
NO:1 = 11, NO:2 = 10
```

### SORTCHARA <キャラクタ変数> {, <FORWARDorBACK>}

任意のキーによる、キャラリストのソート。

ソートキーはNAMEのような文字列変数、NOのような数値型変数、CFLAGのような数値配列変数のいずれでも可能です。

<キャラクタ変数>は省略することができ、その場合はキャラ番号(NO:XX)でソートされます。

FORWARDなら昇順、BACKなら降順になります。省略した場合は昇順でソートされます。

MASTERはソートの対象になりません。

また、TARGET:0、ASSI:0は自動で追尾されますので使用後に手動で操作する必要はありません。

しかしTARGET:1などを使用しているバリアントはこれらを手動で追随させる必要があります。

```
	;NOで昇順にソート
	SORTCHARA
	;NOで降順にソート
	SORTCHARA BACK
	;CFLAG:2で昇順にソート
	SORTCHARA CFLAG:2
	;NAMEで降順にソート
	SORTCHARA NAME, BACK
```

なお、TARGET == -1の場合でも、CFLAG:2などの値を実際に参照するわけではないのでエラーにはなりません。

### GETCHARA <キャラ番号(NO:XXXの方)>

現在所有しているキャラの中にそのキャラがいるかを判定し、いればリスト上での位置を、いなければ-1を返します

リスト全体から特定のキャラの有無を確認したい場合に使えます

### ADDDEFCHARA

ゲーム開始時のシステム的なキャラ追加処理を行う命令です。

chara0\*.csvで定義されたキャラと、gamebase.csvで指定された初期キャラを追加します。

"ADDCHARA 0"はキャラNOが0であるキャラを探して追加しますが、ADDDEFCHARAはcsvの番号でキャラを追加します。

該当するcsvが存在しない場合、ADDVOIDCHARA同様に空のキャラクタを作成します。

これはeramakerの初期化処理を再現するための命令であり、@SYSTEM\_TITLE以外では使用できません。

### ADDVOIDCHARA

csvに依らずにキャラを追加する命令です。

ADDVOIDCHARAで追加されたキャラは全ての変数に0又は""(空文字列)が代入されています。

### DELALLCHARA

登録されている全てのキャラクタを削除します。 以下のスクリプトと同じことです。

```
REPEAT CHARANUM
	DELCHARA 0
REND
```

### PICKUPCHARA <対象キャラ>(, <対象キャラ>, ....)

引数で指定したキャラのみを残し、他のキャラを全て削除する命令です。

MASTER:0、TARGET:0、ASSI:0などは自動で追随します。命令後手動で設定し直す必要はありません。

対象キャラに負の値を指定した場合エラーになりますが、MASTER、TARGET、ASSI等を対象に設定し、

その結果それらの変数の中身が負の値だった場合は、例外でエラーになりません（無視される）。

### EXISTCSV <数式>

対応するキャラが定義されているかどうかをチェックしRESULT:0に代入します。

定義されていれば1、されていなければ0を返します。

ADDCHARA noがエラーにならずに実行できるかどうかを調べることができます。

### FINDCHARA <キャラクタ変数>, <式>(, <数式>, <数式>)

### FINDLASTCHARA <キャラクタ変数>, <式>(, <数式>, <数式>)

FINDCHARA命令はキャラクタ変数と値を指定し、変数がその値であるキャラクタの登録番号をRESULT:0に返します。

複数見つかった場合、FINDCHARAは最初にヒットしたキャラを、

FINDLASTCHARAは最後にヒットしたキャラを返します。見つからなかった場合は-1を返します。

また、第3引数を指定することで検索の開始位置を、第4引数を指定することで検索の終了位置を指定できます。

ただし、検索範囲がキャラクタ数の範囲を超える場合はエラーとなります。

```
X = -1
WHILE 1
	FINDCHARA CFLAG:10, 123, X + 1
	X = RESULT
	SIF X < 0
		BREAK
	PRINTFORML %NAME:X%
WEND
```

### COPYCHARA <数式>, <数式>

第一引数で指定された登録番号のキャラの全てのデータを第二引数で指定された登録番号のキャラにコピーします。

### ADDCOPYCHARA <数式>

引数で指定された登録番号のキャラと同じデータであるキャラを新たに追加します。つまり、ADDCHARAの変種です。

----------------------------------------

## 変数操作・変数参照・CSV参照

### VARSIZE <変数名>

指定した変数の配列のサイズをRESULT:0に代入します。

多次元配列変数の場合、一番左の要素から順にRESULT:0, RESULT:1, RESULT:2と代入されます。

配列のサイズはVariableSize.csvで指定した値です。

```
VARSIZE FLAG
PRINTFORML <TEST1> = {RESULT:0}
VARSIZE SAVESTR
PRINTFORML <TEST2> = {RESULT:0}
VARSIZE TALENT
PRINTFORML <TEST3> = {RESULT:0}
WAIT
;結果(サイズを変更していない場合)
<TEST1> = 10000
<TEST2> = 100
<TEST3> = 1000
```

※実際に変数を参照するわけではないので配列外参照が発生することはありません。 上の例ではTARGET == -1の場合でも-1人目のTALENTを参照しようとしてエラー、ということにはなりません。

### RESETDATA

GLOBALとGLOBALSを除く全ての変数を初期化します。

具体的には全てのキャラを削除し、全てのローカル変数および全ての通常の変数に0又は空文字列を代入します。

また、PALAMLVやSTRなど初期値が設定されている変数については初期値を代入します。

### RESETGLOBAL

グローバル変数を初期化します。

具体的にはGLOBALに0を代入し、GLOBALSに空文字列を代入します。

### RESET\_STAIN <数式>

第1引数で指定したキャラクタのSTAINを初期化する命令です。 初期値はBEGIN TRAINのときに代入される値と同様で、\_replace.csvの「汚れの初期値」で指定できます。

### SWAP <変数1>, <変数2>

変数1と変数2の中身を入れ替えます

交換する2つの変数は同じ型（整数型と整数型、文字列型と文字列型）である必要があります

### CSVNAME <数式>

### CSVCALLNAME <数式>

### CSVNICKNAME <数式>

### CSVMASTERNAME <数式>

CSVで定義されたNAME、CALLNAME、NICKNAME、MASTERNAMEを直接呼び出す関数です。

所有してないキャラの名前とかが欲しいときとかにどうぞ

第一引数がキャラ番号(NOの方)です。

### CSVBASE <数式>, <数式>

### CSVCSTR <数式>, <数式>

### CSVABL <数式>, <数式>

### CSVTALENT <数式>, <数式>

### CSVMARK <数式>, <数式>

### CSVEXP <数式>, <数式>

### CSVRELATION <数式>, <数式>, <数式>

### CSVJULE <数式>, <数式>

### CSVEQUIP <数式>, <数式>

### CSVCFLAG <数式>, <数式>,

CSVで定義された値を直接呼び出す関数です。

第一引数がキャラ番号、第二引数が各変数のインデックスです。

CSVCSTRはRESULTSに文字列を代入し、その他はRESULTに数値を代入します。

### GETNUM <変数名>, <文字列式>

各csvで定義されている名称からその数値を取得し、RESULT:0に代入します。

例えば、abl.csvで"2,技巧"が定義されていれば、GETNUM ABL, "技巧"の結果、RESULT:0に2が代入されます。

定義されていない場合は-1になります。

csvと変数の対応は[Emueraの拡張文法#一般](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/exetc_jp.md)のページの「文字列による配列変数の要素の指定」に準じます。

### GETPALAMLV <数式>, <判定するLVの上限>

### GETEXPLV <数式>, <判定するLVの上限>

与えられた値の内容とPALAMLV・EXPLVを比較し、その引数がPALAMLV・EXPLVでどこまで以上かをRESULT:0に代入します。

第2引数は調査する最大のLVを表します。PALAMLV・EXPLVの値を設定してから使用してください。

### FINDELEMENT <一次元配列変数>, <検索対象(変数と同型)>, <検索初位置>, <検索終位置>, <厳密一致かのフラグ>

### FINDLASTELEMENT <一次元配列変数>, <検索対象(変数と同型)>, <検索初位置>, <検索終位置>, <厳密一致かのフラグ>

配列中の特定範囲から特定の要素の位置を取得する関数です。

第3・第4引数で指定された配列要素の検索範囲に第2引数で指定されたものと同じ要素があれば、その位置を返します。

複数ある場合はFINDELEMENTは最初にヒットしたものを、

FINDLASTELEMENTは最後にヒットしたものを返します。ヒットしない場合は-1を返します。

検索対象が文字列の場合はREPLACEと同様に正規表現を使えます。

第5引数は文字列の場合のみ有効で、0であれば文字列の一部が一致でもOKとし、

0以外であれば文字列と完全に一致した場合のみOKとします。

### VARSET <変数名>{, <数式 or 文字列式>, <配列範囲初値>, <配列範囲終値+1>}

指定した変数の配列の指定範囲に第二引数の値を代入します。

第二引数を省略した場合、0または空文字列が代入されます。

第三引数以降を省略した場合、配列の全てに代入されます。

例えば

```
VARSET FLAG, 0
VARSET STR, "あああ", 0, 10
VARSET TA:0:0:0,5678
```

この例ではFLAGの要素全てが0になります。

STR:0からSTR:9には"あああ"が代入され、TAについても三次元配列の全ての要素に5678が代入されます。

同じことはERB上でFOR-NEXTループなどを使って行うこともできますが、ループ回数が数十万回程度になると実行時間が無視できなくなります。

VARSET命令はERB上での代入よりはるかに早く処理を終わらせることができます。

キャラクタ変数をVARSET命令の対象にした場合、指定したキャラの要素のみに代入されます。

```
VARSET CFLAG:MASTER:0, 0
VARSET CSTR, ""
```


この例ではMASTERのCFLAG:0～999（変更していなければ）が0になりますが、他のキャラのCFLAGは影響を受けません。

また、対象を省略した場合は通常通りTARGETとみなされるのでTARGETのCSTRが全て""になります。他のキャラのCSTRは影響を受けません。

1次元配列および配列型キャラクタ変数以外の、DITEMTYPEやTA等に使用した場合、第三引数以降は無視され配列の全てに代入されます。

### CVARSET <キャラクタ変数>{, <数式>, <式>, <キャラクタ範囲初値>, <キャラクタ範囲終値+1>}

指定した登録キャラクタについてキャラクタ変数の特定要素へ代入する命令です。

第一引数で指定した変数の第四引数以降で指定した登録キャラクタについて、第二引数で指定した要素へ第三引数で指定した値を代入します。

NAME、ISASSIなどの一次元配列変数の場合、第二引数は処理に影響しません。そのため第三引数を省略しない場合、適当な値を指定してください。

第三引数を省略した場合、0又は""(空文字列)が代入されます。

第二引数も省略した場合、0番目の要素に代入されます。

第四引数以降を省略した場合、全ての登録キャラクタに代入されます。

```
CVARSET CFLAG, 10, 123
```


このスクリプトは以下と同じことです。

```
REPEAT CHARANUM
	CFLAG:COUNT:10 = 123
REND
```

### ARRAYSHIFT <対象変数>, <ずらす数>, <ずらしてできた空白領域の初期値>{, <ずらす配列範囲の初値>, <ずらす配列要素の範囲の数>}

以下、私家改造版更新履歴より、

```
配列をシフトする命令ARRAYSHIFT実装
　書式：ARRAYSHIFT <対象変数>, <ずらす数>, <ずらしてできた空白領域の初期値>{, <ずらず配列範囲の初値>, <ずらす配列要素の範囲の数>}
　内容：配列変数を指定した数だけずらす、正の値で添え字の大きい方へ、負の値で小さい方にずらす
　　　　配列の範囲からはみでた値は掃き捨て、ずらして出来た空白領域は第2引数で指定した値で満たす
　　　　省略可能な第4および第5引数を使うと一部の範囲のみをずらすことができる
```

1次元配列および配列型キャラクタ変数のみに対応しています。DITEMTYPEやTA等に使用することはできません。

### ARRAYREMOVE <対象変数>, <消す範囲初値>, <消す要素数>

以下、私家改造版更新履歴より、

```
配列要素を部分削除する命令ARRAYREMOVE実装
　書式：ARRAYREMOVE <対象変数>, <消す範囲初値>, <消す要素数>
　内容：配列変数を指定した初期値から要素数分だけ削除し、後ろを値を詰める
　　　　消す要素数を0以下にすると初期値から後ろ全て消去になります
```

1次元配列および配列型キャラクタ変数のみに対応しています。DITEMTYPEやTA等に使用することはできません。

### ARRAYSORT <対象変数>{, <ソート方式(FORWARD or BACK)>, <開始インデックス>, <対象要素数>}

以下、私家改造版更新履歴より、

```
配列変数をソートするARRAYSORT実装
　書式：ARRAYSORT [対象変数](, [ソート方式(FORWARD or BACK)], [開始インデックス], [対象要素数])
　内容：開始インデックスから対象要素数個の配列データをソートする
　　　　FORWARDで昇順、BACKで降順
```

### ARRAYCOPY <コピー元変数名>, <コピー先変数名>

以下、私家改造版更新履歴より、

```
無頓着な配列コピー命令ARRAYCOPY実装
　書式：ARRAYCOPY <コピー元変数名>, <コピー先変数名>
　内容：コピー元変数の値をコピー先変数へコピーする
　　　　型変数は型が同じで次元数が同じである必要がある
　　　　また、キャラクター変数には非対応
　　　　要素数が異なる場合はコピーできる分だけコピーする
```

書式例：ARRAYCOPY "A", "B"

### ARRAYMSORT array1{, array2...}

ARRAYMSORTはarray1を昇順でソートし、それと同じ順序でarray2以降の配列を並び替えます。

array1は一次元配列である必要があります。array2以降は多次元配列も受け付けます。

array1に0または空文字列の要素があるとき、それを配列の終端とみなし以降の要素はソートしません。

array2以降の配列の要素数がarray1のソートされた要素数よりも少ない場合場合、命令を中断しRESULT:0に0を代入して終了します。

全ての配列のソートに成功した場合、この命令はRESULT:0に非0を代入して終了します。

```
@TEST
#DIM ARRAY1,4
#DIM ARRAY2,4
#DIM ARRAY3,4,3
ARRAY1 = 3,1,2,0
ARRAY2 = 1001,1002,1003,0
ARRAY3:0:0 = 1, 101, 2763
ARRAY3:1:0 = 2, 102, 9615
ARRAY3:2:0 = 3, 103, 7035

ARRAYMSORT ARRAY1,ARRAY2,ARRAY3
PRINTFORML > ARRAY1 == {ARRAY1:0},{ARRAY1:1},{ARRAY1:2},{ARRAY1:3}
PRINTFORML > ARRAY2 == {ARRAY2:0},{ARRAY2:1},{ARRAY2:2},{ARRAY2:3}
FOR I,0,3
	PRINTFORML > ARRAY3:{I}:0 == {ARRAY3:I:0},{ARRAY3:I:1},{ARRAY3:I:2}
NEXT

;;;出力
> ARRAY1 == 1,2,3,0
> ARRAY2 == 1002,1003,1001,0
> ARRAY3:0:0 == 2,102,9615
> ARRAY3:1:0 == 3,103,7035
> ARRAY3:2:0 == 1,101,2763
```

### CUPCHECK <登録キャラクター番号>

以下、私家改造版更新履歴より、

```
CUP、CDOWNに対応するUPCHECKであるCUPCHECK追加
　書式：CUPCHECK <キャラ>
　内容：引数で指定したキャラに対するUPCHECKを走らせる、それだけ
```

当然ですがUP,DOWNの影響はありません。また、UPCHECKでは結果を表示していましたが、CUPCHECKによる結果は表示されません。

----------------------------------------

## セーブデータ操作

### SAVEDATA <数式>, <文字列式>

<数式>で示される番号のファイルに現在の状態をセーブします。

SAVEDATA命令は@SAVEINFOを呼び出さないのでPUTFORMでコメントを入れることができません。

代わりに2つ目の引数の<文字列式>でコメントを指定します。

(1.704からは文字列変数だけでなく文字列式が使用できます) 以下に例を示します。

```
	GETTIME
	STR:0 = %RESULTS:0% {DAY+1}日目
	SAVEDATA 14, STR:0
	SAVEDATA 15, RESULTS:0 + " " + @"{DAY+1}日目"
結果(ロード画面)
[13] ----
[14] 2009年03月28日 00:31:27 1日目
[15] 2009年03月28日 00:31:27 1日目
[16] ----
```

上書きの確認などは行わないので必要ならERB側で用意してください。

既にデータがあるかどうかはCHKDATA命令で調べることができます。

SAVEDATAは(SAVEGAME命令と違って)スクリプトのどの場所でも呼び出すことができます。

### LOADDATA <数式>

<数式>で示される番号のファイルのデータをロードします。

ロードに失敗した場合、エラー終了します。

必ずCHKDATA命令でロード可能かどうかを調べてから実行してください。

LOADDATAは(LOADGAME命令と違って)スクリプトのどの場所でも呼び出すことができます。

### DELDATA <数式>

<数式>で示される番号のファイルのデータを削除します。

ファイルが存在しなくてもエラーにはなりません。

### CHKDATA <数式>

<数式>で示される番号のファイルのデータの情報をRESULT:0とRESULTS:0に代入します。

RESULT:0は以下の値をとります。0の場合のみそのファイルをロードすることができます。

+ 0 - このファイルはロード可能です。
+ 1 - 指定されたファイルは存在しません。
+ 2 - ゲームのコードが違います。(gamebase.csvの"コード"の値が違うデータ)
+ 3 - バージョンが違います。(gamebase.csvの"バージョン"の値が異なり、許容されるバージョンでもないデータ)
+ 4 - 上記以外の問題があるファイルです。

RESULT:0が0のとき、RESULTS:0にはセーブデータのコメント（@SAVEINFOのPUTFORMで入力した文字列、またはSAVEDATAの第２引数）が代入されます。

RESULT:0が0以外のとき、RESULTS:0には"セーブデータのバーションが異なります"などのエラーメッセージが代入されます。

### SAVENOS <数値変数>

コンフィグ"表示するセーブデータ数"で指定された数を取得し指定された数値変数に代入します。標準は20です。

数値変数を省略することはできません。

### SAVEGLOBAL

変数GLOBALとGLOBALSをセーブします。保存先は"global.sav"です。

ERHファイル内でGLOBAL及びSAVEDATAフラグを持つ変数が定義されていればそれもセーブします。

### LOADGLOBAL

GLOBALとGLOBALSをロードします。保存先は"global.sav"です。

読み込みに失敗してもエラーにはなりません。

読み込みに成功するとRESULTに1を、失敗すると0を代入します。

通常のセーブデータと同様に、gamebase.csvで設定されたコード、バージョンが適切でないファイルはロードできません。

変数GLOBALの詳細は変数の節を参照してください。

### OUTPUTLOG

以下、私家改造版更新履歴より、

```
ログ出力命令OUTPUTLOG実装
　　やり過ぎはディスクの寿命を縮めるのでほどほどに
```

なお、ログの文字コードはUnicodeです。

### SAVECHARA str filename, str memo, int charano{, int charano2, ...}

指定したキャラクタのデータをファイルに保存する命令です。

第一引数はデータをセーブするファイル名(の一部)を指定します。実際のファイル名は"chara\_\*.dat"になります。

第二引数はセーブデータのメモとなる文字列を保存します。後にCHKCHARADATA関数により読むことができます。

第三引数以降にはセーブしたいキャラの登録番号を指定します。いくつでも可能ですが同一の登録番号を複数回指定することはできません。

datフォルダーが存在しない場合、フォルダの作成を試みます。作成に失敗した場合エラーになります。

また、第一引数が空文字列である、第一引数にファイル名に使えない文字が含まれるなどの場合エラーになります。

### LOADCHARA str filename

第一引数はデータをロードするファイル名(の一部)を指定します。実際のファイル名は"chara\_\*.dat"になります。

RESULT:0に、読み取りに失敗した場合は0を、成功した場合は1を代入します。

LOADVARの前にCHKCHARADATA関数によりファイルの適切さを確認すべきです。

LOADCHARAはSAVEされているキャラの数だけ新しいキャラを登録します。

したがって既存の登録キャラには影響しません。

何名のキャラが追加されたかを知るにはロード前後でのCHARANUMを比較してください。

### CHKCHARADATA str filename

datフォルダ内の"chara\_\*.dat"で示されるファイル名のデータの情報を返します。

RESULTにはロード可能な場合は0、何らかの理由により不可能な場合は非0が代入されます。

また、ロード可能な場合はRESULTS:0にセーブデータのメモを代入し、不可能な場合はその理由をRESULTS:0に代入します。

### FIND\_CHARADATA str filename

LOADCHARAの対象となり得るファイルをdatフォルダの中から探索しファイル名(chara\_\*.datの\*の部分)をRESULTSに代入します。

RESULTにはヒット数（発見されたファイル数）が代入されます。

引数はchara\_\*.datの\*の部分を指定できます。

例えばFIND\_CHARADATA("\*あなた\*")であれば、chara\_\*あなた\*.datを探し、chara\_001あなた.datやchara\_あなたABC.datがヒットします。

引数を省略した場合、"\*"を指定したことになりchara\_\*.datを探します。

なお、chara\_.dat(\*が空文字列)はLOADCHARAで指定できないのでヒットしません。

ヒット数がRESULTSの要素数を超えた場合はエラーにはなりませんが超えた分のファイル名は代入されません。

### SAVETEXT str text, int fileNo{, int force\_savdir, int force\_UTF8}

textで指定したテキストを、ファイル名textXX.txt（例えばfileNoが2ならtext02.txt）に保存します。

この命令はテキストにヘッダーなどを付け加えたり変更したりすることなく文字列そのままを保存します。

この命令は通常はオプション設定の影響を受け、savフォルダ内に作成されたり、UTF-8で保存されます。

第3引数に非0を指定した場合、オプションを無視して強制的にsavフォルダ内に保存します。savフォルダは必要に応じて作成されます。

第4引数に非0を指定した場合、オプションを無視して強制的にUTF-8エンコードで保存します。

成功した場合RESULT:0に非0が、失敗した場合0が代入されます。

短い時間中に同一ファイルに書き込むことを繰り返した場合、ウイルス対策ソフト等の影響で書き込みに失敗する可能性がありますので成否のチェックは重要です。

### LOADTEXT int fileNo{, int force\_savdir, int force\_UTF8}

LOADTEXT命令版はtextXX.savを読み取りその結果をRESULTS:0に代入します。

第2引数に非0を指定した場合、オプションによらずsavフォルダ内のファイルを探します。

第3引数に非0を指定した場合、UTF-8エンコードで保存されているものとして読み取ります。

失敗した場合、RESULTS:0が空文字列になります。

同名の式中関数もあり、RESULTS:0の代わりに返り値に読取結果又は空文字列を返します

----------------------------------------

## 日付・時刻取得

### GETTIME

パソコンの現在日時・時刻に関する情報をRESULT:0とRESULTS:0に代入します。

現在日時が2009年3月28日13時5分23秒678ミリ秒であれば、RESULT:0には"20090328130523678"が代入されます。

RESULTS:0には"2009年03月28日 13:05:23"が代入されます。

RESULTS:0は主にセーブデータのコメントに使用することを想定しています。

年月日について独自の表記をしたい場合はRESULT:0を分解して使用してください。

なお、RESULT:0の精度は実行する環境にもよりますが、十数～数十ミリ秒程度です。

（数ミリ秒しか経過していない場合、同じ値が帰ってくることがあります）

パフォーマンスの測定を目的とする場合は注意してください。

### GETMILLISECOND

西暦0001年1月1日からの経過時間をミリ秒単位で取得し、RESULT:0に代入します。

そのまま加減算ができるので経過時間などを調べるにはGETTIMEよりも適しています。

なお、RESULT:0の精度は実行する環境にもよりますが、十数～数十ミリ秒程度です。

（数ミリ秒しか経過していない場合、同じ値が帰ってくることがあります）

パフォーマンスの測定を目的とする場合は注意してください。

### GETSECOND

西暦0001年1月1日からの経過時間を秒単位で取得し、RESULT:0に代入します。

そのまま加減算ができるので経過時間などを調べるにはGETTIMEよりも適しています。

----------------------------------------

## 入力・ウェイト

### FORCEWAIT

右クリック、マクロのスキップでスキップできないWAIT命令です。

この命令に達した時点でこれらのスキップ状態は解除されます。

### INPUT {<数値>}

### INPUTS {<文字列>}

eramakerと同様の命令ですが、引数により空文字列を入力された場合のデフォルト入力値を設定することができます。

引数を省略し空文字列を入力した場合、従来と同様にINPUTは再入力、INPUTSはRESULTSに空文字列が代入され次の処理へ進みます。

### TINPUT <数値>, <数値>{, <数値>, <文字列>}

### TINPUTS <数値>, <文字列式>{, <数値>, <文字列>}

制限時間のある入力受付命令です。 1番目の引数は制限時間(ms)ですが、100msより細かい値を設定しても正確な動作はできません。

2番目の引数は時間切れ時のデフォルトのリターン値になります

3番目の引数は残り時間を表示するかで0なら非表示、他は表示となります。省略した場合は1（表示）です。

4番目の引数は時間切れ時に表示される文字列です。空文字列の場合はタイマー表示を消去して次の処理へ移ります。

なお、4番目の引数を設定した場合、3番目の引数は省略できません。

またTINPUTSにおいて、INPUTS同様にマクロ式を用いることができます。

文字列として()を使用する場合、を用いてエスケープしてください。

### TWAIT <数値>, <数値>

第一引数が制限時間、第二引数が入力受付フラグです。

制限時間経過するまで動作を停止します

実際の挙動は入力受付フラグの指定によって変化します

+ 入力受付フラグ = 0：入力を受け付け、入力がなされると制限時間前でも次に進みます
+ 入力受付フラグ ≠ 0：入力を受け付けません（制限時間まで強制的に待たせることができます）

### ONEINPUT {<数値>}

### ONEINPUTS {<文字列>}

以下、私家改造版更新履歴より、

```
一文字限定入力自動処理命令ONEINPUT、ONEINPUTS実装
　書式：ONEINPUT or ONEINPUTS
　内容：一文字のみの入力を受け付ける、入力すると自動的に次の処理に移る
```

ペースト等を用いて複数桁の数字（複数の文字）を一度に貼りつけた場合、最初の桁（文字）のみが入力されたものとして処理されます。

INPUTやINPUTS同様、引数により空文字列を入力された場合のデフォルト入力値を設定することができます。

ただし、ONEINPUTで負の値を指定した場合や、ONEINPUTSで空文字列を指定した場合は、引数は無効となり、引数なしの場合と同じ挙動になります。

また、複数桁の数字（複数の文字）を引数とした場合、最初の桁（文字）のみがデフォルト入力値となります。

引数を省略し空文字列を入力した場合、通常と同様にONEINPUTは再入力、ONEINPUTSはRESULTSに空文字列が代入され次の処理へ進みます。

ONEINPUTSの場合、空文字列のままEnterを押しても空文字列を入力したとみなされます。

なお、これらの命令を利用した場合にはEmueraのCONFIG設定においてキーボードマクロを使用する設定になっていても、

うまく働かない現象が起こりますがそれは仕様です。

またONEINPUTSにおいて、INPUTS同様にマクロ式を用いることができます。

文字列として()を使用する場合、を用いてエスケープしてください。

### TONEINPUT <数値>, <数値>{, <数値>, <文字列>}

### TONEINPUTS <数値>, <文字列式>{, <数値>, <文字列>}

引数はそれぞれTINPUT、TINPUTSと同じです。

それぞれONEINPUTとTINPUT、ONEINPUTSとTINPUTSの性質を併せ持つ入力受付命令です。

これらの命令を利用した場合にはEmueraのCONFIG設定においてキーボードマクロを使用する設定になっていても、

うまく働かない現象が起こりますがそれは仕様です。

またTONEINPUTSにおいて、INPUTS同様にマクロ式を用いることができます。

文字列として()を使用する場合、を用いてエスケープしてください。

### WAITANYKEY

いずれかのキー入力、またはマウスのクリックを待つWAIT命令です。

WAITのONEINPUT版ともいえます。

### INPUTMOUSEKEY {int time}

INPUTMOUSEKEY命令はマウスやキーボードの入力を直接認識する命令です。

引数はTINPUTのような時間切れ処理を行うまでの時間をミリ秒で指定します。

引数を省略したか0以下を指定した場合には時間切れ処理は行われません。

この命令は、ONEINPUT等では捕捉できないファンクションキーや方向キー、PageUpキー等も入力として認識することができます。

一方でこの命令による入力の受付待機中はESCキーや右クリックによるスキップ機能、マクロ機能、その他の機能が使用できず、単にESCキー等が押されたという結果のみ受け付けます。

また、この命令は時間切れ表示等を含めて一切のPRINT処理を行いません。

スキップ機能の実装や、入力を表示したい場合などはERB側で対応する必要があります。

第2引数にミリ秒単位で数値を指定することにより、時間切れ処理が行われます。 INPUTMOUSEKEYの返り値は最大5つであり、RESULT:0, RESULT:1, RESULT:2, RESULT:3, RESULT:4 にそれぞれ代入されます。

```
RESULT:0 == 1; マウス押下が検出された
 RESULT:1 ;マウスボタン - 左ボタン0x100000、右ボタン0x200000、中ボタン0x400000。C#のSystem.Windows.Forms.MouseButtons列挙体の整数値
 RESULT:2 ;マウスX座標 クライアント領域の左下を基準とする。常に正の値になる。
 RESULT:3 ;マウスY座標 クライアント領域の左下を基準とする。常に負の値になる。
 RESULT:4 ;CBGSETBMAPが実行されており、クリック座標直下の色の不透明度が0xFFである時、色の0xRRGGBBを返す。該当しない場合は-1。
RESULT:0 == 2; マウスホイールの回転が検出された
 RESULT:1 ;ホイール量
 RESULT:2 ;マウスX座標
 RESULT:3 ;マウスY座標
RESULT:0 == 3; キーボード押下が検出された
 RESULT:1 ;押されたキーのコード。修飾コード(Alt,Ctrl,Shift)を含まない。KeyCode相当。C#のSystem.Windows.Forms.Keys列挙体の整数値
 RESULT:2 ;押されたキーのコード。修飾コードを含む。KeyData相当
RESULT:0 == 4; 時間切れにより終了した
```
マウスのボタンについては\_VirtualKey.ERHのMB\_LEFT～MB\_MIDDLEを、キーコードについては\_VirtualKey.ERHのVK\_～を参照してください。

キーコードはGETKEY関数のものと共通です。

マウスホイールのホイール量は1や-1ではなく最低でも120など大きな値になるので注意してください。

また、Emueraの画面外にカーソルがある場合にホイールが検出されるかどうかはWindowsの設定次第でありEmuera側では変更できません。

初期設定ではWindows8.1以前は検出されますがWindows10では画面外のホイールは検出されないようです。

----------------------------------------

## ループ・分岐構文

### FOR <数値型変数>, <数式>, <数式>{, <数式>}

### NEXT

FOR～NEXTはREPEAT～RENDの機能強化版です。

第１引数はカウントに使用される変数を表します（REPEATでは常にCOUNT:0）。

第２引数は変数に最初に代入される値を表します（REPEATでは常に0）。

第３引数はループが終了される値を表します（REPEATで設定可能な値）。

第４引数はループごとに加算される値を表します（REPEATでは常に1）。

```
FOR COUNT, 0, X
	～～
NEXT
REPEAT X
	～～
REND
```

上の二つはほぼ同じ動作をします。

ともにX回の繰り返しを行う構文で、ループの途中でCONTINUEやBREAKを使用できます。

異なる点はカウント用の変数を指定できることと、開始値とステップを変更できることです。

また、FOR～NEXTは入れ子にすることができます。

```
FOR Y, 0, 100
	FOR X, 0, 100
		～～
	NEXT
NEXT
```

第１引数である<変数名>に指定できる変数は数値型の変数のみです。キャラクタ変数も使えません。

第４引数である<ステップ>は省略可能です。省略した場合、1です。

<ステップ>が正の値のとき、繰り返しのたびに<変数名>の変数に<ステップ>が加算され、第３引数<終了値>以上となったときにループが終了します。

<ステップ>が負の値のときは、<変数名>の変数が<終了値>以下となったときにループが終了します。

<ステップ>が0であれば無限ループになります。BREAK文が実行されるまで永久に繰り返します。

各値はループの開始と同時に固定され、ループの途中で変数が変化しても影響を受けません。

以下の２つは同じ結果になります。

```
	;１
	X = 10
	FOR COUNT:X, 0, X, X/10
		X = 10000
	NEXT
	;２
	FOR COUNT:10, 0, 10, 10/10
		X = 10000
	NEXT
```

なお、GOTO等の命令で直接FOR～NEXT内に入った場合、REPEAT～RENDと同様にNEXTの直前まで通常通り実行し、その後NEXTを無視して次の行から処理を続行します。

### WHILE <数式>

### WEND

REPEAT～RENDやFOR～NEXTのような繰り返し構文の一種です。

WHILEの<数式>が0以外である限りループを繰り返します。

常に満たし続ける条件を与えると、BREAKで抜けるようになっていない限り無限ループになります

あまりにループ処理が長いとEmueraが文句を言う場合があります

なお、GOTO等の命令で直接WHILE～WEND内に入った場合、通常どおりWENDに到達した時点でWHILEへループし、条件を判定します。

### DO

### LOOP <数式>

REPEAT～RENDやFOR～NEXTのような繰り返し構文の一種です。

Cのdo～while、VBのdo～loop while構文と同様、LOOPの<数式>が0以外である限り実行をループを繰り返します。

WHILE～WENDと異なり最低でも1回は実行されることが特徴です。

なお、DO～LOOP内のCONTINUEした場合にはLOOPの条件を満たしていなければそのままLOOPを抜けます。CONTINUEしてもDO文に戻るとは限らないことに注意してください。

また、GOTO等の命令で直接DO～LOOP内に入った場合、通常どおりLOOPに到達した時点で条件を判定し、<数式>が0以外ならDOへループします。

### SELECTCASE <式>

### CASE <CASE条件式>(, <CASE条件式>, <CASE条件式> ……)

### CASEELSE

### ENDSELECT

分岐構文です。Visual Basicの同名の構文と動作を似せています。

IF構文と似ていますが、SELECTCASEは1つの値を元に複数の行へ分岐する構文です。

SELECTCASEに指定した引数の値によって分岐します。 もっとも単純な使用法は以下のようになります。

```
SELECTCASE X
	CASE 1
		PRINTL Xは1です。
	CASE 3
		PRINTL Xは3です。
	CASEELSE
		PRINTL Xは1でも3でもありません。
ENDSELECT
```

このスクリプトはXの値によって分岐します。

SELECTCASE文が実行された時、Xが1であれば"CASE 1"の行に飛び、次のCASEまたはCASEELSEまでの行を実行します。

同様にXが3であれば"CASE 3"に飛びます。

Xの値に対応するCASE文がない時、CASEELSE文があればそこに飛びます。なければENDSELECTに飛びます。

Cなどのswitch文と異なり、1つのCASEから次のCASEに流れ落ちることはありません。

また、BREAK文でENDSELECTに飛ぶことはできません。

なお、GOTO等の命令で直接SELECTCASE～CASE～CASEELSE～ENDSELECT内に入った場合、IF～ELSEIF～ELSE～ENDIFと同様に

CASE、CASEELSE、ENDSELECTの直前まで通常通り実行したあとに、ENDSELECTの次の行へ飛び処理を続行します。

CASEの条件式には3種類の書式があります。

1つは上記のように値を直接指定する方法、2つ目は"IS <演算子> <数式>"、3つめは"<数式> TO <数式>"です。

"IS <演算子> <数式>"の場合、例えば"IS <= 30"であればXが30以下の場合、CASE以下が実行されます。

"<数式> TO <数式>"の場合、例えば"10 TO 20"であればXが10以上20以下の場合、CASE以下が実行されます。

また、CASEには複数の条件式をカンマで区切って指定することができます。

これらを利用して例えば以下のように書くことができます。

```
SELECTCASE X
	CASE 1
		PRINTL Xは1です。
	CASE 2,3
		PRINTL Xは1ではありません。
		PRINTL Xは2か3です。
	CASE 10 TO 20
		PRINTL Xは1でも2でも3でもありません。
		PRINTL Xは10以上20以下です。
	CASE IS <= 30
		PRINTL Xは1, 2, 3, 10以上20以下のどれでもありません。
		PRINTL Xは30以下です。
	CASE 40, 5 * 10 TO 6 * 10, IS >= 10 * 10
		PRINTL Xは30以下ではありません。
		PRINTL Xは40, 50以上60以下, 100以上のいずれかです。
	CASEELSE
		PRINTL Xは30以下, 40, 50以上60以下, 100以上のいずれにも該当しません。
ENDSELECT
```

ISやTOは"IS <演算子> <数式>"、"<数式> TO <数式>"の形で使わねばならないことに注意してください。

例えば"30 < IS"や"(10 TO 20) || (30 TO 40)"のような書き方はできません。

また、"<数式> TO <数式>"はあくまでも左辺以上、右辺以下の場合に真となります。

右辺が左辺より小さい場合はそのCASEが実行されることはありません。

1つのCASEに複数の条件式がある場合、短絡評価が起きることに注意してください。

条件は左から順にチェックされ、条件を満たすものが見つかった場合、残りの条件は評価されません。

SELECTCASEの引数として文字列式を使用することもできます。

SELECTCASEに文字列を指定した場合はCASEの条件式も文字列式である必要があります。

----------------------------------------

## 乱数制御

### RANDOMIZE <数式>

### DUMPRAND

### INITRAND

RAND:Xで得られる乱数を制御するための命令です。

RANDOMIZE命令は指定した値で乱数を初期化します。

同じ値で初期化したならば、RANDは必ず同じ結果を返します。

DUMPRANDは現在の乱数の状態をRANDDATA変数に保存します。

INITRANDはRANDDATA変数に保存したデータを読み出します。

DUMPRANDを行う前にINITRANDを行ってしまわないように注意してください。

RANDDATA変数の中身が不適当な場合、RANDが正常に動作しなくなります。

```
PRINTFORML {RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}
RANDOMIZE 23478612
PRINTFORML {RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}
RANDOMIZE 23478612
PRINTFORML {RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}
DUMPRAND
PRINTFORML {RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}
INITRAND
PRINTFORML {RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}
INITRAND
PRINTFORML {RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}/{RAND:100000}

;結果
92539/49469/48337/15839/48368/1604
34536/91889/81167/22434/87922/95565
34536/91889/81167/22434/87922/95565
68286/10690/68868/82610/90769/60789
68286/10690/68868/82610/90769/60789
68286/10690/68868/82610/90769/60789
```

上記の結果のうち、最初の行は不定です。実行するたびに結果が変わります。

2行目、3行目は同じ値でRANDOMIZEした直後なので必ずこの結果になります。

4行目の前にDUMPRAND命令を実行しています。

5行目の前にINITRAND命令を行うことで、RANDの状態をDUMPRAND命令で保存した状態まで戻しています。

そのため、4行目と5行目は結果が同じになっています。

6行目では再度INITRAND命令を行うことで、繰り返し同じ結果を得ています。

RANDDATA変数はセーブされる変数なので、セーブ前にDUMPRANDを行い、ロード直後にINITRANDを行うことで同じ乱数状態を続けて使うことができます。

----------------------------------------

## デバッグ補助・システムフロー制御

### BEGIN <キーワード>

BEGINはeramakerから存在する命令ですが、キーワードとして新しくFIRSTとTITLEが追加されました。

BEGIN FIRSTはタイトル画面で"[0]最初からはじめる"を選択した時と同じ効果で、イベント関数@EVENTFIRSTが実行されます。

BEGIN TITLEはタイトル画面に戻ります。

どちらも変数の初期化などは行いませんので適宜RESETDATA命令を実行してください。

### CALLTRAIN <コマンド数>

連続コマンド実行命令です。

あらかじめSELECTCOM:(1～)にコマンド番号を代入しておき、実行するコマンドの数を引数にして実行します。

```
SELECTCOM:1 = XXX
SELECTCOM:2 = YYY
　　　・
　　　・
　　　・
SELECTCOM:N = ZZZ

CALLTRAIN (設定したコマンドの数)
```

通常のコマンド実行と同様にSHOW\_STATUSやSHOW\_USERCOMも呼び出しますが、TRAINコマンド、USERCOMの表示はされません。

どうしてもUSERCOMの表示をしたい場合はNOSKIP～ENDNOSKIPを使うと良いでしょう。

CALLTRAINによる自動実行が終了後、システム関数@CALLTRAINENDが呼び出されます。

ただし、@CALLTRAINENDはイベント関数ではないため多重定義できないことに注意してください。

なお、コマンドの指定に使うコマンド番号は、ゲーム中の値でなく、TRAIN.CSVで指定した値になります

### DOTRAIN <数式>

強制的にTRAINを行う命令です。

@EVENTTRAIN、@SHOW\_STATUS、@SHOW\_USERCOM、@USERCOM、@EVENTCOMEND及びそこから呼び出された関数の中でのみ使用可能です。

引数で指定する番号はtrain.csvで定義した番号に対応しています。

動作はコマンドが選択された場合と同じで、UP、DOWNなどの変数を初期化し、SELECTCOMに引数を代入し、@EVENTCOMが呼ばれ、@COM{SELECTCOM}が呼ばれ……という流れになります。

引数が0未満であるか、TRAINNAMEの要素数以上の値であればエラーになりますが、それ以外のチェックは行われません。

引数がtrain.csvで定義されていない数字でも強制的に実行しようとします。

また、@COM\_ABLEを呼び出さず、強制的に実行されます。

必要であればDOTRAINの前に以下のようなチェックを行ってください。

```
SIF ( X < 0 || X >= VARSIZE("TRAINNAME") || TRAINNAME:X == "" )
	RETURN
RESULT = 1
TRYCALLFORM COM\_ABLE{X}
SIF RESULT == 0
	RETURN
DOTRAIN X
```

逆にDOTRAINを用いてTRAINのコマンドを独自に実装することもできます。

例えばtrain.csvを空にしておき、@SHOW\_USERCOMで独自に表示し、@USERCOMでDOTRAINを行います。

あるいはtrain.csvを空にする代わりに全ての@COM\_ABLEが0を返すようにしてもよいでしょう。

@COM\_ABLEを変更する代わりに、全ての@COM\_ABLEを削除し、\_replace.csvの"COM\_ABLE初期値"を0にする方法もあります。

なお、CALLTRAINの処理の途中でDOTRAINが行われた場合、CALLTRAINの残りは無効になります。

### THROW <FORM構文>

強制的にエラーとし、引数に与えた文字列でエラー表示を行う命令です。

----------------------------------------

## CALL・JUMP・GOTO系

### TRYJUMP <文字列> (, 引数1, 引数2……)

### TRYCALL <文字列> (, 引数1, 引数2……)

### TRYGOTO <文字列>

JUMP、CALL、GOTOと同じですが、指定した関数が存在しなくともエラーになりません。

指定した関数が存在しない場合は何もしません。

TRYJUMPとTRYCALLは引数を指定できます。詳しくは関数の「自作関数における引数指定」の項を参照してください。

なお、TRYGOTOで直接IF～ELSEIF～ELSE～ENDIF内に入った場合、ELSEIF、ELSE、ENDIFの直前まで通常通り実行したあとに、ENDIFの次の行へ飛び処理を続行します。

また直接REPEAT～REND内に入った場合、RENDの直前まで通常通り実行し、その後RENDを無視して次の行から処理を続行します。

これらの処理はGOTOや他のGOTO系命令と同様の処理です。その他のEmueraで追加されたループ・分岐構文についてはこのページの「ループ・分岐構文」「TRYC系」の項を参照してください。

### JUMPFORM <書式付文字列> (, 引数1, 引数2……)

### CALLFORM <書式付文字列> (, 引数1, 引数2……)

### GOTOFORM <書式付文字列>

JUMP、CALL、GOTOと同じですが、PRINTFORMなどと同じ形式で関数名を指定できます。

```
CALLFORM KOJO\_{NO:TARGET}\_{SELECTCOM}
```

のような使い方ができます。 JUMPFORMとCALLFORMは引数を指定できます。詳しくは関数の「自作関数における引数指定」の項を参照してください。

なお、GOTOFORMで直接ループ・分岐構文内に入った場合については「TRYGOTO」やこのページの「ループ・分岐構文」「TRYC系」の項を参照してください。

### TRYJUMPFORM <書式付文字列> (, 引数1, 引数2……)

### TRYCALLFORM <書式付文字列> (, 引数1, 引数2……)

### TRYGOTOFORM <書式付文字列>

JUMP、CALL、GOTOと同じですが、PRINTFORMなどと同じ形式で関数名を指定でき、関数が存在しなくてもエラーになりません。

TRYJUMPFORMとTRYCALLFORMは引数を指定できます。詳しくは関数の「自作関数における引数指定」の項を参照してください。

なお、TRYGOTOFORMで直接ループ・分岐構文内に入った場合については「TRYGOTO」やこのページの「ループ・分岐構文」「TRYC系」の項を参照してください。

### CALLF <文字列> (, 引数1, 引数2……)

### CALLFORMF <書式付文字列> (, 引数1, 引数2……)

以下、私家改造版更新履歴より、

```
式中関数を返り値無視で呼び出す命令CALLF、CALLFORMF実装
　書式：CALLF 関数名, 引数1, ....
　　　　（式中関数ですが、普通の関数の引数書式で呼び出してください）
　内容：式中関数を通常の関数扱いで呼び出す、返り値は破棄される
　　疑似SETTERを作りたくてやった、今は反省している
```

当然だがRESULTやRESULTSは呼んだ式中関数内で操作していない限り、変化しない。

### CALLEVENT <文字列>

イベント関数をイベント関数として呼び出します。

引数を与えることはできません。

またイベント関数中やイベント関数から呼び出された関数中で使用することもできません。

----------------------------------------

## CALL・JUMP・GOTO系2 (TRYC-CATCH-ENDCATCH)

### TRYCJUMP <文字列> (, 引数1, 引数2……)

### TRYCCALL <文字列> (, 引数1, 引数2……)

### TRYCGOTO <文字列>

### TRYCJUMPFORM <書式付文字列> (, 引数1, 引数2……)

### TRYCCALLFORM <書式付文字列> (, 引数1, 引数2……)

### TRYCGOTOFORM <書式付文字列>

### CATCH

### ENDCATCH

拡張書式：TRYC系関数呼び出し～CATCH～ENDCATCH

　(TRYC系はTRY系関数と同様の関数系が用意されてます)

内容：TRYC系の関数呼び出し時に関数が見つからなかった場合の挙動を制御

　文法としてはIF～ELSE～ENDIFと同様になりました（違いは関数があった場合の処理がなくてもよいこと）

そのため、GOTO等の命令で直接TRYC系～CATCH～ENDCATCH内に入った場合、IF～ELSEIF～ELSE～ENDIFと同様に

CATCH、ENDCATCHの直前まで通常通り実行したあとに、ENDCATCHの次の行へ飛び処理を続行します。

また、TRYCGOTO・TRYCGOTOFORMで直接ループ・分岐構文内に入った場合については「TRYGOTO」やこのページの「ループ・分岐構文」の項を参照してください。

```
TRYCCALL UNKNOWN\_FUNC ;存在しない関数
	関数があったとき、関数処理後に行う処理（あれば、なければ省略して直CATCHでOK）
CATCH
	関数がなかったときに行う処理
ENDCATCH
```

なお、入れ子可能です。

### TRYCALLLIST

### TRYJUMPLIST

### TRYGOTOLIST

### FUNC <文字列> (, 引数1, 引数2……)

### ENDFUNC

複数の関数（ラベル）を指定し、最初に見つかった関数（のみ）を呼び出すための構文です。

TRYLIST系～ENDFUNC内に上記の文法以外の記述をすることはできません。

なお、TRYGOTOLISTで直接ループ・分岐構文内に入った場合については「TRYGOTO」やこのページの「ループ・分岐構文」「TRYC系」の項を参照してください。

以下のように使用します。

```
TRYCALLLIST
	FUNC 関数1
	FUNC 関数2
ENDFUNC
```

FUNCで指定された関数の呼び出しを順に試み、成功すれば呼び出した後ENDFUNCへ、失敗すれば次の行のFUNC（又はENDFUNC）へ移動します。

これは以下のスクリプトと同等です。

```
TRYCCALL 関数1
CATCH
	TRYCCALL 関数2
	CATCH
	ENDCATCH
ENDCATCH
```

----------------------------------------

## RETURN系

### RETURN <数式>(, <数式>, <数式>, ...)

eramakerからある命令ですが、返り値に定数でない変数や数式も指定できるようになりました。

また、複数の返り値に対応しています。

複数の返り値を指定した場合、先頭からRESULT:0、RESULT:1...という風に代入されます。

### RETURNFORM <書式付文字列>(, <書式付文字列>, <書式付文字列>, ...)

RETURNの亜種です。

引数に指定された書式付文字列を数式として解析し、RETURNを行います。

例えば、以下のようなことができます。

```
	A = 100
	CALL TEST
	PRINTFORMW RESULT == {RESULT}

@TEST
	STR = A * 10
	RETURNFORM %STR%
```

RETURNと異なり、%は剰余演算子ではなく文字列式の開始とみなされるので注意してください。

```
;OK。Aの下２ケタを返す。
	RETURN A % 100

;エラー。%以降を文字列式として読もうとするので。
	RETURNFORM A % 100
```

また、複数の返り値に対応しています。

複数の返り値を指定した場合、先頭からRESULT:0、RESULT:1...という風に代入されます。

### RETURNF <式>

\#FUNCTIONまたは#FUNCTIONS属性を持つ関数専用の命令です。

詳細は[ユーザー定義の式中関数](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/usermeth_jp.md)を参照してください。

複数の返り値には対応していません。

## DEBUG系

DEBUG系命令はデバッグモードで起動したときのみ動作します。

非デバッグモード時には何もしません。

非デバッグモード時には引数の解析も行われないため、<書式付文字列>におかしな点ががあってもエラーになりません。

### DEBUGPRINT <文字列>

### DEBUGPRINTL <文字列>

### DEBUGPRINTFORM <書式付文字列>

### DEBUGPRINTFORML <書式付文字列>

これらはそれぞれPRINT命令やPRINTLと同様の動作をします。

異なる点は出力先がメインコンソールではなくデバッグコンソールである点です。

また、SKIPDISP命令の影響を受けず、nを使用することもできません。

### DEBUGCLEAR

デバッグコンソールのPRINT内容を全て削除します。

### ASSERT <数式>

引数が真(非0)のとき、何もしません。

引数が偽(0)の時、エラーを出力してスクリプトの実行を停止します。

----------------------------------------

## ツールチップ系

ボタン上にマウスカーソルを置くことにより表示されるツールチップを制御するための命令です。

ツールチップの設定法は[HTML\_PRINT関連](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/exhtml_jp.md)を参照してください。

### TOOLTIP\_SETCOLOR <数式>, <数式>

ツールチップの前景色及び背景色を0xRRGGBB形式の数値で設定します。

指定にR,G,B値や文字列を使いたい場合はCOLOR\_FROMRGBやCOLOR\_FROMNAME関数を使用してください。

### TOOLTIP\_SETDELAY <数式>

ツールチップが表示されるまでの時間をミリ秒単位で設定します。

ディフォルトは500(ミリ秒)、最大値は32767です。

### TOOLTIP\_SETDURATION int msDuration

以下、私家改造版更新履歴より、

```
○ツールチップの表示時間を設定する命令TOOLTIP\_SETDURATIONを追加
　　書式：TOOLTIP\_SETDURATION [表示時間(ms)]
　　内容：ツールチップの最大表示時間を[表示時間(ms)]に設定
　　引数：[表示時間(ms)]：0以上の整数値　0の場合デフォルトの挙動になります、後タイマーの特性上極端に短い時間は想定通りに動かないかもねー
```

----------------------------------------

## HTML系

htmlっぽいタグを利用してPRINTしたりする命令・関数群です。

詳細は[HTML\_PRINT関連](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/exhtml_jp.md)を参照してください。

### HTML\_PRINT <文字列式>

htmlっぽいタグを利用してPRINTする命令です。

引数がPRINTのような文字列ではなくPRINTSと同じ文字列式でり、自動的に改行するので実際はPRINTSLの動作に近いです。

HTML\_PRINTによる描画はALIGNMENT、SETFONT、COLOR、FONTSTYLE命令とその類似命令の影響を受けません。

これらの効果を得るには全てタグで指定する必要があります。

### HTML\_TAGSPLIT <文字列式>(, <数値変数>, <文字列変数>)

対象文字列をHTML文字列と解釈し、タグと平文に分割して分割数をRESULTに、分割後文字列をRESULTSに代入します。

第二、第三引数が指定されている場合、RESULT、RESULTSの代わりに指定された変数に代入します。

分割処理中にエラーが生じた場合、RESULTに-1が代入されます。

HTML\_TAGSPLITはタグの内容や対応関係の適否までは検証しません。

分割数がRESULTSの配列サイズを超えた場合、超えた分はRESULTSに代入されません。

----------------------------------------

## AWAIT関連

テキストボックスを経由せずに入力を行ったりするための命令・関数群です。

### AWAIT {int time}

ERBの実行を一時停止し、Windowsの処理を行います。

引数を指定した場合、指定したミリ秒数だけ実行を待機します。

AWAIT命令はEmueraの無限ループ警告を中断し、Emueraのプロセスが「応答なし」になることを防ぎます。

時間がかかる処理を行うときに使用して下さい。

ただし、AWAIT命令自体がそれなりの実行時間がかかるため、頻繁に行いすぎると遅くなります。

また、ユーザーを不安にしないため、例えば以下のように作業進度を逐次表示することをお勧めします。

```
REDRAW 0
FOR LCNT, 0, 100
	PRINTSL "作業中・・・ " + TOSTR(LCNT) + "％ 完了"
	AWAIT
	CLEARLINE 1
	;時間がかかる処理
NEXT
```

### GETKEY int vkey

キーボード及びマウスボタンの状態を返します。

引数で指定されるキーが押されていれば1、押されていなければ0を返します。

この関数はEmueraのウインドウがアクティブのときのみ1を返し、アクティブ状態でなければキー状態にかかわらず0を返します。

キーコードの数値と実際のキーの対応に関してはマイクロソフト社が提供するMSDNの[GetKeyState()](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/getkeystate_jp.md)の項を参照してください。

### GETKEYTRIGGERED int vkey

GETKEYと同様にキーボード及びマウスボタンの状態を返します。

GETKEYは現在押されているかどうかを取得するのに対し、GETKEYTRIGGEREDは押された直後のみ1を返します。

すなわち継続して押し続けている場合はGETKEYは1を返しますが、GETKEYTRIGGERDは最初のみ1を返し以降は0を返します。

この関数はEmueraのウインドウがアクティブのときのみ1を返し、アクティブ状態でなければキー状態にかかわらず0を返します。

キーコードの数値と実際のキーの対応に関してはマイクロソフト社が提供するMSDNの[GetKeyState()](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/getkeystate_jp.md)の項を参照してください。

### MOUSEX

### MOUSEY

マウスカーソルの現在のX座標またはY座標を取得します。

座標はクライアント領域の左下位置を(0,0)とする相対位置であり、右方向がx軸の正、下方向がy軸の正です。

カーソルがクライアント領域内にある場合MOUSEYは負の値を返すことに注意してください。

クライアント領域の広さはCLIENTWIDTH、CLIENTHEIGHT関数によって取得できます。

（クライアント領域左上を基準とするY座標が必要なら、MOUSEY()+CLIENTHEIGHT()によって取得できます）

この関数はEmueraのウインドウがアクティブでなくても、また、マウスカーソルがウインドウ外であっても正常に動作します。

### ISACTIVE

Emueraのウインドウの状態を返します。

アクティブであれば1、アクティブでなければ0を返します。

----------------------------------------
## 画像処理関連

画像処理関係の命令です。

Gで始まるGraphics系命令は、変更可能な描画領域を操作するための命令です。

G系命令を使用するには描画方式にGRAPHICSまたはTEXTRENDERERを指定する必要があります。

描画方式にWINAPIが指定されている場合、G系の命令は使用できずエラーになります。

SPRITEで始まるSprite系命令は、スプライトに関する命令です。

スプライトはresourcesフォルダで宣言したリソースと同様にPRINT\_IMG命令などで行中に表示することもできます。

CBGで始まる[ClientBackground](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/clientbackground_jp.md)系命令は、クライアント領域の背景画像に関連した命令です。

画像処理系の命令での色指定はRGBではなくアルファ値（不透明度）を含むARGB形式であることに注意して下さい。

ARGB型は16進数で0xAARRGGBBで表されます。

画像処理系の命令の大半は式中で関数として呼び出すこともできます。

関数として呼び出した場合には、結果の値はRESULTには代入されずに戻り値となります。

### GCREATE int ID, int width, int height

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したサイズで指定したIDのGraphicsを作成します。

GraphicsのIDは0以上の整数、width、heightは1以上8192以下の間の整数値でなければなりません。

引数がこの範囲を外れるとエラーです。

作成に成功した場合、非0を返します。

指定したIDのGraphicsが既に作成されている場合、0を返します。

Graphicsを作り直す場合はGDISPOSE命令で既存のGraphicsを廃棄してください。

### GCREATEFROMFILE int ID, str filepath

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

resourcesフォルダ内の画像ファイルを相対パスで指定し、その画像を開いてGraphicsを作成します。

resourcesフォルダ内のcsvファイルでリソースを宣言した場合と異なり、画像ファイルはロックされません。

作成に成功した場合、非0を返します。

指定したIDのGraphicsが既に作成されている場合はGraphicsの作成に失敗し、この命令は何もせずに0を返して終了します。

ファイルが存在しない、画像として認識できない、ファイルのサイズが大きすぎる、などで失敗した場合も0を返します。

### GDISPOSE int ID

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsを廃棄します。

廃棄に成功した場合、非0を返します。

指定したIDのGraphicsが未作成（廃棄済の場合を含む）の場合、0を返します。

### GCLEAR int ID, int cARGB

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsの全域を指定した色で置き換えます。

処理に成功した場合、非0を返します。

ID又は色指定が不適切な場合はエラーになります。

### GFILLRECTANGLE int ID, int x, int y, int width, int height

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsに(x, y, width, height)で指定した四角形を描画します。

処理に成功した場合、非0を返します。

描画の色はGSETBRUSH命令によってあらかじめ指定しなければEmueraコンフィグの文字色で描画されます。

### GDRAWG int destID, int srcID, int destX, int destY, int destWidth, int destHeight, int srcX, int srcY, int srcWidth, int srcHeight

### GDRAWG int destID, int srcID, int destX, int destY, int destWidth, int destHeight, int srcX, int srcY, int srcWidth, int srcHeight, var cm

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したdestIDのGraphicsに、指定したsrcIDのGraphicsを描画します。

描画先destのGraphicsの位置及びサイズを4つの整数で、描画元srcのGraphicsの位置及びサイズを4つの整数で指定します。

オプションとして、5x5以上の二次元数値配列をcmとして指定することでカラーマトリクスを適用して描画します。

colorMatrixは全要素を1/256にして.Net FrameworkのColorMatrixクラスに渡されます。つまり、対角がすべて256である5x5行列が単位行列になります。

処理に成功した場合、非0を返します。

描画先Graphics又は描画元Graphicsのいずれかが未作成であるなどの場合、0を返します。

描画先と描画元Graphicsは同一でも実行可能です。

### GDRAWGWITHMASK int destID, int srcID, int maskID, int destX, int destY

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したdestIDのGraphicsに、srcIDのGraphicsを、maskIDのGraphicsをマスクとして適用して描画します。

出力先destIDのGraphics内の描画位置をdestX, destYで指定します。

処理に成功した場合、非0を返します。

srcIDとmaskIDの幅及び高さが完全に一致すること、描画領域がdestIDからはみ出さないことが成功の条件です。

マスクとして適用して描画するとは、具体的には、マスク画像の青の値を不透明度としてソース画像に適用して描画することです。

例えば、マスク画像が完全に白一色（つまり全部の場所で青色がMAX）の場合、ソース画像はマスクなしの場合と同様にそのまま描画されます。

マスク画像が完全に黒一色（つまり全部の場所で青色が0）の場合、ソース画像は完全透明として扱われ何も起きません。

この命令の処理はGPUではなく、CPUがシングルスレッドで解決します。速度には期待しないでください。

### GDRAWSPRITE int ID, str sprName

### GDRAWSPRITE int ID, str sprName, int destX, int destY

### GDRAWSPRITE int ID, str sprName, int destX, int destY, int destWidth, int destHeight

### GDRAWSPRITE int ID, str sprName, int destX, int destY, int destWidth, int destHeight, var cm

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsに指定したsprNameのSpriteを描画します。

オプションとして、Graphics内部の位置をdestX,destYで指定することでその位置にSpriteを描画します。

また、描画幅及び高さをdestWidth,destHeightで指定することでそのサイズに拡大又は縮小してSpriteを描画します。

さらに、cmに5x5の行列を指定することでカラーマトリクスを適用して描画します。

なおSpriteのサイズはSPRITEWIDTH(str imgName), SPRITEHEIGHT(str imgName)関数で取得できます。

処理に成功した場合、非0を返します。

アニメーションスプライトを指定した場合、実行時のフレーム1つが描画されます。

### GSETCOLOR int ID, int cARGB, int x, int y

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsの指定位置のピクセルを指定した色に置き換えます。

処理に成功した場合、非0を返します。

この命令はそれほど高速ではありません。

GGETCOLOR命令と合わせて大きな画像の全体を書き換える試みは実用的な時間内には終わりません。

### GSETBRUSH int ID, int cARGB

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsに指定した色のブラシを設定します。

指定したブラシはGDISPOSE命令でGraphicsが破棄されるまで記憶されます。

処理に成功した場合、非0を返します。

ここで設定した色のブラシがGFILLRECTANGLE命令で使用されます。

### GSETFONT int ID, str fontName, int fontSize

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsに指定した名前およびサイズのフォントを設定します。

指定したフォントはGDISPOSE命令でGraphicsが破棄されるまで記憶されます。

処理に成功した場合、非0を返します。

設定したフォントを利用する命令・関数はバージョン1.824現在には存在しません。

### GSETPEN int ID, int cARGB, int penWidth

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsに指定した色及び幅のペンを設定します。

指定したペンはGDISPOSE命令でGraphicsが破棄されるまで記憶されます。

処理に成功した場合、非0を返します。

設定したペンを利用する命令・関数はバージョン1.824現在には存在しません。

### GCREATED int ID

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsが作成済みであるなら1を、未作成（廃棄済を含む）なら0を取得します。

### GWIDTH int ID

### GHEIGHT int ID

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsの幅または高さを取得します。

Graphicsが未作成（廃棄済を含む）なら0を返します。

### GGETCOLOR int ID, int x, int y

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsの指定位置の色を0xAARRGGBB形式の整数値で取得します。

Graphicsが未作成又は廃棄済み、あるいはx,yが画像外の位置であるなら-1を返します。

この命令のみ、失敗した場合に0ではなく-1を返すことに注意してください。

黒色かつ完全透明の位置の色を取得した場合に、この命令は0を返します。

### GSAVE int ID, int fileNo

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

指定したIDのGraphicsの画像を、fileNoの番号を付けたファイル名でpng形式で出力し保存します。

処理に成功した場合、非0を返します。

### GLOAD int ID, int fileNo

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

fileNoの番号を付けたファイル名の画像を開き、Graphicsを作成します。

動作としてはCREATEFORMFILE命令とほぼ同じですがresoucesフォルダ内の画像ではなくGSAVE命令で保存した画像から作成する点が異なります。

処理に成功した場合、非0を返します。

指定したIDのGraphicsが既に作成されている場合はGraphicsの作成に失敗し、この命令は何もせずに0を返して終了します。

### SPRITECREATE str spriteName, int gID

### SPRITECREATE str spriteName, int gID, int x, int y, int width, int height

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

gIDのGraphicsの一部または全部を元にして、spriteNameで指定したリソース名を持つスプライトを作成します。

(x, y, width, height)を指定することでGraphicsのその部分をスプライトとして切り取れます。

作成に成功した場合、非0を返します。

同じリソース名のスプライトが既に存在するなどで失敗した場合、0を返します。

スプライトは親GraphicsのIDと切取位置を記憶しているだけなので、親Graphicsに変更があるとスプライトも変更されます。

また、親Graphicsが破棄されるとスプライトも破棄された扱いになります。

作成したスプライトはresoucesフォルダ内のcsvで宣言したリソースとほぼ同様に扱うことができます。

例えばPRINT\_IMG命令やHTML\_PRINTのimgタグなどで使用できます。

### SPRITEANIMECREATE str spriteName, int width, int height

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

spriteNameで指定したリソース名を持つ、width及びheightで指定したサイズのアニメーションスプライトを作成します。 作成に成功した場合、非0を返します。

同じリソース名のスプライトが既に存在するなどで失敗した場合、0を返します。

アニメーションさせるためにはSPRITEANIMEADDFRAME命令によってフレームを追加する必要があります。

アニメーションスプライトに関する注意点については、[resouces](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/resouces_jp.md)も参照してください。

### SPRITEANIMEADDFRAME string spriteName, int gID, int x, int y, int width, int height, int offsetx, int offsety, int delay

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

spriteNameで指定したリソース名を持つアニメーションスプライトにフレームを追加します。

gIDで指定したGraphicsの(x, y, width, height)で指定した四角形の範囲をフレームとし、スプライト左上からoffsetx, offsetyの位置に配置します。

アニメーションスプライトの作成時に設定したサイズの範囲から外れた部分は描画されません。

delayにはこのフレームを表示する時間をミリ秒単位で指定します。

spriteNameのリソース名が存在しない、又はアニメーションスプライトでない場合はこの命令は失敗し、何もしません。

フレームの追加に成功した場合1を、失敗した場合は0を返します。

### SPRITEDISPOSE string spriteName

spriteNameで指定したリソース名を持つスプライトを廃棄します。

廃棄に成功した場合、非0を返します。

この命令はスプライトの元となったGraphics等には影響しません。

Graphicsに割り当てられたメモリを解放するにはGDISPOSE命令を使用してください。

### SPRITEGETCOLOR string spriteName, int x, int y

spriteNameで指定したリソース名を持つスプライトの指定位置の色を0xAARRGGBB形式の整数値で取得します。

spriteNameが未作成又は廃棄済み、あるいはx,yが画像外の位置であるなら-1を返します。

この命令のみ、失敗した場合に0ではなく-1を返すことに注意してください。

黒色かつ完全透明の位置の色を取得した場合に、この命令は0を返します。

### SPRITECREATED str spriteName

指定した名称のスプライトが作成済みであるなら1を、未作成又は廃棄済みであるなら0を返します。

### SPRITEWIDTH str spriteName

### SPRITEHEIGHT str spriteName

指定した名称のスプライトの幅または高さを取得します。

スプライトが未作成又は廃棄済みであるなら0を返します。

### SPRITEPOSX str spriteName

### SPRITEPOSY str spriteName

指定した名称のスプライトの相対位置のX、Yを取得します。

スプライトが未作成又は廃棄済みであるなら0を返します。

相対位置のX、Yが0なのか未作成又は廃棄済であるのかの区別には別途SPRITECREATEDを呼び出してください。

### SPRITESETPOS str spriteName, int posx, int posy

指定した名称のスプライトの相対位置のX、Yを設定します。

### SPRITEMOVE str spriteName, int movex, int movey

指定した名称のスプライトの相対位置のX、Yに指定した値を加算します。

つまり、

```
SPRITESETPOS spriteName, SPRITEPOSX(spriteName) + movex, SPRITEPOSY(spriteName) + movey
```

と同等です。

### CBGSETG int ID, int x, int y, int zdepth

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

IDで指定するGraphicsをクライアント領域に表示するように設定します。

(x, y)に0を指定した場合、クライアント領域の左下と画像の左下が一致するように表示されます。

xは右方向が正、yは下方向が正、zdepthは画面奥方向が正です。

zdepthは0以外の値を指定します。通常の文字描画がzdepth==0に相当し、zdepthが負であれば文字よりも手前に描画されます。

### CBGSETSPRITE str spriteName, int x, int y, int zdepth

spriteNameで指定したリソース名を持つスプライトをクライアント領域に表示するように設定します。

(x, y)に0を指定した場合、クライアント領域の左下と画像の左下が一致するように表示されます。

xは右方向が正、yは下方向が正、zdepthは画面奥方向が正です。

zdepthは0以外の値を指定します。通常の文字描画がzdepth==0に相当し、zdepthが負であれば文字よりも手前に描画されます。

### CBGCLEAR

CBGで始まる各種CBG系命令で設定した背景画像の設定を全て解除します。

### CBGCLEARBUTTON

CBGSETBUTTONSPRITE命令で設定したボタンの設定を解除します。

### CBGREMOVERANGE int zmin, int zmax

CBGSETG、CBGSETSPRITE、CBGSETBUTTONSPRITE命令で設定した画像のうち、Z深度がzmin以上zmax以下である画像を設定解除します。

### CBGREMOVEBMAP

CBGSETBMAPG命令で設定したボタンマップの設定を解除します。

### CBGSETBMAPG int ID

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

IDで指定するGraphicsをクライアント領域のボタンマップとして設定します。

ここで設定したボタンマップはCBGSETBUTTONSPRITE命令及びINPUTMOUSEKEY命令に影響します。

ボタンマップ画像は表示はされませんがCBGSETG命令で設定した画像と同様に画面左下と画像左下位置が一致するように配置されます。

マウスカーソル直下のボタンマップ画像の色が、ボタンの値として認識されます。

ただし、色のアルファ値が255でない（透明又は半透明である）ときにはボタンの値としては認識されません。

### CBGSETBUTTONSPRITE int button, str spriteName, str spriteNameB, int x, int y,int zdepth

### CBGSETBUTTONSPRITE int button, str spriteName, str spriteNameB, int x, int y,int zdepth, str tooltipmes

（※描画方法がGRAPHICS又はTEXTRENDERERのときのみ使用可能）

CBGSETBMAPG命令で設定したボタンマップと連動して選択可能なボタンを設定します。

マウス直下のボタンマップ画像の色の0xRRGGBB値が、引数buttonに等しい時に表示されるスプライトをspriteNameB、それ以外のときに表示されるスプライトをspriteNameに指定します。

spriteName又はspriteNameBは空文字列を指定することができ、そうした場合には非選択中又は選択中に何も表示しません。

x, y, zdepthについてはCBGSETSPRITEと同じです。基準位置(x,y) = (0,0)が画面左下と画像左下が一致する位置であることに注意してください。

オプションで当該ボタンを選択中に表示されるツールチップ文字列をtooltipmesで指定することができます。

同じbuttonの値に複数のCBGSETBUTTONSPRITEを割り当てることができ、また、ボタンの位置と一致する必要はありません。

そうした場合、ツールチップについては画像のxy位置とは関係なく、ツールチップ文字列が設定された中で最もzdepthが大きいもの（最先に描画され、最奥に見えるもの）の表示が優先されます。

spriteNameで指定したリソース名を持つスプライトをクライアント領域に表示するように設定します。

(x, y)に0を指定した場合、クライアント領域の左下と画像の左下が一致するように表示されます。

xは右方向が正、yは下方向が正、zdepthは画面奥方向が正です。

zdepthは0以外の値を指定します。通常の文字描画がzdepth==0に相当し、zdepthが負であれば文字よりも手前に描画されます。

### SETANIMETIMER int time

アニメーションスプライト用にミリ秒単位で再描画間隔を指定します。

Emueraは通常はINPUT等の入力待ち中に再描画を行いません。

この命令で再描画間隔を設定することでINPUT等の入力待ち中に画像をアニメーションさせることができます。

なお、TINPUTなどの時間切れ処理のある命令中には再描画を行いません。

実際の描画間隔はコンピュータの状態により、指定した時間よりもやや遅れます。

したがって描画間隔をアニメーションのdelayの値と同じ値にすると頻繁にフレームが飛ぶことになります。

delayよりも十分に短い間隔を指定してください。

この命令はコンフィグの「フレーム毎秒」の項目とは無関係です。

また、REDRAW命令による再描画抑止の効果を受けません。

## 未整理項目

### CLEARTEXTBOX

以下、私家改造版更新履歴より、
```
○入力欄を空にする命令CLEARTEXTBOX追加
　　書式：CLEARTEXTBOX
　　内容：最下部の入力欄のテキストを全て消去する
```
### STRDATA

以下、私家改造版更新履歴より、

```
○PRINTDATAの非表示、選択文字列返し版STRATA追加
　　書式：STRDATA <代入先文字列変数>
　　　　　　DATA、DATAFORM、DATALIST～ENDATA
　　　　　ENDDATA
　　内容：DATA構文で指定された文字列からランダムで1つを返す
　　　　　DATALIST構文中のDATA系は改行文字で連結して返されます
```

### STOPCALLTRAIN

以下、私家改造版更新履歴より、

```
○CALLTRAIN命令のフローをスクリプトから強制終了するSTOPCALLTRAIN追加
　　書式：STOPCALLTRAIN
　　内容：CALLTRAIN命令が動いている間に呼び出されると、その時点でCALLTRAINの処理を終了する
　　　　　それ以外の場合は何もしない
```
