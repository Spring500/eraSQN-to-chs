# デバッグコマンド

※標準ではデバッグコマンドは使用できません。
必要ならヘルプの設定から"デバッグコマンドを使用する"にチェックを入れてください。

※この機能は[デバッグモード](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/debug_jp.md)が無かったバージョンの簡易的な機能です。
現バージョンでのデバッグには[デバッグモード](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/debug_jp.md)での起動を勧めます。

スクリプト実行中（ゲーム中）、"@"で始まる文字列を入力するとデバッグコマンドとして受け付けられます。
大文字小文字を区別するかどうかはemuera.config中の"大文字小文字の違いを無視する"の指定に依存します。

デバッグコマンドはERBと同じ書式で指定します。
例えば、

```
@MONEY = 10000
@PRINTV FLAG:200
@PRINTFORM %NAME:MASTER%のCFAG(1) = {CFLAG:MASTER:1}
@ADDCHARA 1
```

のように書くことができます。
また、単に変数や数式を入力した場合、それらの値が出力されます
（下記の@の後の半角スペースは必須ではありません）
```
@ FLAG:200
@ @"%NAME:MASTER%のCFAG(1) = {CFLAG:MASTER:1}"
```

ただしIFやCALLのようなスクリプトの流れを変える命令や、INPUTやWAITのように入力を要求する命令は使えません。

いくつかのERBにはない命令があります。

+ `@REBOOT`

	再起動してemuera.configやcsv、erbファイルを読み直します。

+ `@OUTPUT`

	現在のログをemuera.logに出力します。既に存在する場合は上書きされます。

	これはOUTPUTLOG命令と同じ動作です。

+ `@EXIT`

	Emueraを終了します。QUIT命令と同じ動作です。

+ `@CONFIG`

	設定ダイアログを開きます。

+ `@DEBUG`

	デバッグダイアログを開きます。これは[デバッグモード](/Wiki/emuera_wiki/eramaker_base_dev_info_jp_edition/debug_jp.md)で起動した場合のみ有効です。

上記以外、つまり通常のERBの命令を実行した場合、MASTERの名前・呼び名が強制的に"イカサマ"になります。
これはデバッグコマンドがチートとしての性質も持つため、乱用を防ぐための措置です。