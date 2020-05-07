# フロー図

フロー図は[DiagramDesigner](http://logicnet.dk/DiagramDesigner/)を用いて作成した。

データファイルは[こちら](/Wiki/emuera_wiki/resources/flow1821.ddd)。

以下の説明文中で特に明示されていない場合は文の主語はEmuera.exeである。

----------------------------------------

# TITLE

起動してerbを読み終えた後、およびBEGIN TITLE実行後。

![フロー図](/Wiki/emuera_wiki/resources/title.gif)

@SYSTEM_TITLEが定義されていればそれを呼び出し、他には何もしない。

@SYSTEM_TITLE中でBEGIN命令やLOADDATA命令が行われずにRETURNされると次に実行する処理がなくなりエラー終了する。

@SYSTEM_TITLEが定義されていなければ標準のタイトル処理を行う。

標準のタイトル画面の"[0] 最初からはじめる"などの文字は変更可能である。

詳細は[\_replace.csv](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/replace_jp.md)を参照。

"[0] 最初からはじめる"が選択された場合、まずデータの初期化を行う。

具体的にはSTRやPRINTLVの初期値の設定（RESETDATA命令と同じ）、ADDCHARA 0など。

次にBEGIN FIRSTを実行し、FIRSTへ遷移する。

"[1] ロードしてはじめる"が選択された場合、@TITLE_LOADGAMEが定義されていればそれを呼び出す。

定義されていなければ標準のロード画面を表示する。

LOADGAMEで呼ばれる画面とは微妙に異なる。

----------------------------------------

# FIRST

タイトル画面で"[0] 最初からはじめる"を選んだ時、およびBEGIN FIRST実行後。

@EVENTFIRST内でBEGIN命令が行われなかった場合、次に実行する処理がなくなりエラー終了する。

![フロー図](/Wiki/emuera_wiki/resources/first.gif)

----------------------------------------
# SHOP

ロード後、およびBEGIN SHOP実行後。

ロード後の場合は@EVENTSHOPの処理を行わない。

![フロー図](/Wiki/emuera_wiki/resources/shop.gif)

@SHOW_SHOP呼び出し後に入力を要求する。 この入力において、0～99が入力されると購入処理、それ以外が入力されると@USERSHOPを呼び出す。

この範囲は_replace.csvによって変更可能である。詳細は[\_replace.csv](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/replace_jp.md)を参照。

なお、PRINT_ITEMSHOP命令で表示されるアイテムの範囲はITEMNAMEとITEMSALESの要素数のいずれか小さい方まで（標準は1000）。

購入処理が呼ばれた場合、対応するITEMSALESが0以外であるか、MONEYがITEMPRICEより大きいかどうかを判定する。

購入判定に失敗した場合、再度入力を要求する。

eramakerでは購入に失敗した場合は@SHOW_SHOPからやり直していた。

購入判定に成功した場合、BOUGHT変数にITEM番号を代入し、ITEM:BOUGHTを1増やし、MONEYをITEMPRICE:BOUGHTだけ減らす。

@EVENTBUYを呼び出し@SHOW_SHOPへ戻る。

どこかでBEGIN命令が行われない限り、SHOPから出ることはない。

----------------------------------------

# TRAIN

BEGIN TRAIN実行後。

![フロー図](/Wiki/emuera_wiki/resources/train.gif)

まず一部の変数の初期化を行う。

具体的には、ASSIPLAY:0に0、PREVCOM:0、NEXTCOM:0に-1を代入する。

さらにTFLAGを全て0にし、全てのキャラのGOTJUEL、TEQUIP、EX、PALAM、SOURCEを全て0にする。

最後に全てのキャラのSTAIN:2に2、STAIN:3に1、STAIN:4に8、その他に0を代入する。

TRAINを出るときには初期化を行わないので、SHOPでセーブするとセーブデータにこれらの値が残ることになる。

@SAVEINFOなどでキャラのGOTJUEL、TEQUIP、EX、PALAMなどに0を代入しておくことでセーブデータのサイズを節約することができる。

NEXTCOMに非負の値を代入した場合の動作は重大な不具合を抱えているためここでは解説しない。

EmueraのNEXTCOMは旧来のコードの動作を前記不具合を含めて再現する目的で実装されたものであり、新規の利用は想定されていない。

CALLTRAIN命令に関しては[拡張命令](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/excom_jp.md)を参照。

@SHOW_STATUS呼び出し後に実行可能なTRAINを表示する。

TRAINNAMEが定義されているものについて、@COM_ABLExxを探す。

探索範囲（図中のMAX_TRAIN）はEmueraではVariableSize.csvで指定したTRAINNAMEの範囲まで、eramakerなら2147483647まで。

@COM_ABLExxが定義されていないか、0以外の値を返したなら実行可能なのでTRAINNAMEを表示する。

@COM_ABLExxが0を返したなら実行できないのでTRAINNAMEを表示しない。

この時に実行可能かどうかを記憶しておく。（実行時に再度@COM_ABLExxを呼び出すわけではない。）

TRAINNAMEの表示が終わったら@SHOW_USERCOMを呼び出す。

@SHOW_USERCOM後、入力の前にUP、DOWN、LOSEBASEを初期化する。

その後、入力を要求する。

入力結果を先の@COM_ABLExxの結果と照らし合わせ、実行可能なコマンドであれば対応する@COMxxを呼び出す流れになる。

まず、SELECTCOM変数にTRAIN番号を代入し、全てのキャラのNOWEXの全ての要素を0にする。

次に@EVENTCOMを呼びだし、その後に対応する@COMを呼び出す。

@COMが0でない値を返したならば@SOURCE_CHECK、@EVENTCOMENDを呼び出し、@SHOW_STATUSに戻る。

@SOURCE_CHECK終了後、@EVENTCOMEND呼び出し前に全てのキャラのSOURCEの全ての要素を0にする。

@SOURCE_CHECK終了後、@EVENTCOMENDが存在しないか@EVENTCOMEND内で一度もWAIT命令が行われない場合、@SHOW_STATUSの直前にWAITを発生させる。

@COMが0を返したならば@SHOW_STATUSに戻る。

なお、UPCHECK命令が実行されるとTARGETのPALAMにUPとDOWNの値が加算・減算され、UPとDOWNの全てに0が代入される。

入力結果が実行可能なコマンドでなければ@USERCOMを呼びだし、@SHOW_STATUSに戻る。

どこかでBEGIN命令が行われない限り、TRAINから出ることはない。

----------------------------------------

# ABLUP

BEGIN ABLUP実行後。

![フロー図](/Wiki/emuera_wiki/resources/ablup.gif)

@SHOW_JUEL、@SHOW_ABLUP_SELECTを呼び出し、入力を要求する。

入力が0～99の範囲内である場合、対応する@ABLUPを探す。

対応する@ABLUPが定義されていれば@ABLUPを呼び出し、@SHOW_JUELに戻る。

定義されていない場合、再度入力を要求する。

eramakerでは定義されていない場合は@SHOW_JUELからやり直していた。

入力が0～99の範囲外である場合、@USERABLUPを呼び出し、@SHOW_JUELに戻る。

Emuera1.705現在ではこの範囲を変える方法はない。

どこかでBEGIN命令が行われない限り、ABLUPから出ることはない。

----------------------------------------

# AFTERTRAIN

BEGIN AFTERTRAIN実行後。

@EVENTEND内でBEGIN命令が行われなかった場合、次に実行する処理がなくなりエラー終了する。

![フロー図](/Wiki/emuera_wiki/resources/aftertrain.gif)

----------------------------------------
# TURNEND

BEGIN TURNEND実行後。

@EVENTTURNEND内でBEGIN命令が行われなかった場合、次に実行する処理がなくなりエラー終了する。

![フロー図](/Wiki/emuera_wiki/resources/turnend.gif)

----------------------------------------
# LOADGAME

LOADGAME命令の実行時。

BEGIN命令はRETURN命令を内包しBEGIN以下の文は決して実行されないが、LOADDATAとSAVEDATA命令はCALL命令と同様に元の場所に帰ってくる。

ただし、LOADが実行された場合はもとの位置を忘れてLOADDATAENDへ遷移する。

![フロー図](/Wiki/emuera_wiki/resources/loadgame.gif)

----------------------------------------
# SAVEGAME

SAVEGAME命令の実行時。

@SAVEINFOを呼び出すタイミングは実際に書き込みが行われる直前である。

![フロー図](/Wiki/emuera_wiki/resources/savegame.gif)

----------------------------------------
# LOADDATAEND

LOADGAMEでLOADが実行された後、およびLOADDATA命令の実行後。

LOADが行われた時点で呼び出し中の関数などこれまでの状態は全て消去される。

![フロー図](/Wiki/emuera_wiki/resources/loaddataend1821.gif)

eramakerだとここでは何もせず、@SHOW_SHOPに遷移する。

Emueraでは、@SYSTEM_LOADENDが定義されていれば@SYSTEM_LOADENDを実行する。

@SYSTEM_LOADEND終了までにBEGIN命令が行われれば、そちらへ遷移する。

でなければ@EVENTLOADが定義されていれば@EVENTLOADを実行する。

@EVENTLOAD終了までにBEGIN命令が行われれば、そちらへ遷移する。

BEGIN命令が行われなければ通常通り@SHOW_SHOPに遷移する。