# AUTOSARモデル内容一覧ツール
## 概要
AUTOSAR R4.2.2のarxmlファイルを読み込み，RTEに関連するAUTOSARモデル内容を複数の表に出力します．

## 表一覧
* ImplementationDataType(実装データ型)
* ApplicationDataType(アプリケーションデータ型)
* Port(SW-Cのポート)
* SenderReceiverInterface(S/Rインターフェース)
* ProvidedDataElement(S/Rの送信データ要素)
* RequiredDataElement(S/Rの受信データ要素)
* SR - Communication(S/R連携)
* ClientServerInterface(C/Sインターフェース)
* ClientOperation(C/Sのクライアントオペレーション要素)
* ServerOperation(C/Sのサーバオペレーション要素)
* TriggerInterface(外部トリガーインターフェース)
* ModeSwitchInterface(モード切替インターフェース)
* ModeManager(モードマネージャー)
* ModeUser(モードユーザー)
* AssemblyConnector(アセンブリコネクタ)
* DelegationConnector(デリゲーションコネクタ)
* Runnable(ランナブルエンティティ)
* ExclusiveArea(排他エリア)
* Schdulable(BSWスケジューラブルエンティティ)
* RunnableMapping(ランナブルエンティティとBSWエンティティのマッピング)
* Partition(パーティション)
* ComponentInstance(SW-C配置)
* OsTask(OSタスク)
* OsAlarm(OSアラーム)
* RteUsedOsActivation(RteUsedOsActivation)
* InterRunnableVariable(InterRunnableVariable)

## 実行環境設定
* Java環境設定(Java8以降)  
 Javaの実行環境をインストールし，PATHを通すか，bin/reporter.bat内のjava.exeをフルパスに変更してください．
* 必要なファイルの設定  
 AUTOSARのサイト(https://www.autosar.org/) から下記のzipファイルをダウンロードし，指定ファイルをschemaフォルダにコピーしてください．
* ダウンロードするファイル  
    * Methodology-and-Templates_Templates.zip (CATEGORIES: 4.2 (CP), CLASSIC PLATFORM)
* schemaフォルダにコピーするファイル  
    * AUTOSAR_4-2-2.xsd
    * xml.xsd

## ツールの使い方
コマンドプロンプトでreporter.batを実行してください．  
`$ reporter.bat <arxml file1> [<armxl file2> [<armxl file3>] ...] [-c <file>] [-e <file>]`
* デフォルトは標準出力へのCSV形式出力です．
* -c ファイル名.csv → CSV形式出力  
1つのシートに複数の表が入っています．  
"# ****"は表の名前を表しており，その次の行がヘッダーを表しています．  
ヘッダーの次の行からコンテンツが書かれています．タブ区切りです．  
* -e ファイル名.xlsx → Excel形式出力  
表ごとにシートが分かれています．青い行が表のヘッダーです．
* -cと-eは同時指定可能です．
* コンテンツがない表は出力されません．
* 例) `$ reporter.bat *.arxml -c sample.csv`  
カレントディレクトリにAUTOSARモデル内容一覧であるsample.csv(CSV形式)を出力します．

## 免責事項
自由にご利用いただけますが，本ソフトウェアの利用に伴ういかなる場合においても，著作権者は一切責任を負いません．

Copyright (C) 2019-2020 ESM, Inc. All rights reserved.
