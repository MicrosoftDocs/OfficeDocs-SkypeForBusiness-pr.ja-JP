---
title: 'Lync Server 2013: 常設チャット データベースのスキーマ'
TOCTitle: 常設チャット データベースのスキーマ
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48272160
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の常設チャット データベースのスキーマ

 

_**トピックの最終更新日:** 2012-09-18_

ここでは、Lync Server 2013通信ソフトウェアの 常設チャット データベースのスキーマについて説明します。

常設チャット データベースは、Lync Server 2013 バックエンド サーバーの役割である **PersistentChatStore** (mgc データベースに対応) と **PersistentChatComplianceStore** (mgccomp データベースに対応) に対応するデータベースを参照します。このスキーマを公開する目的は、クエリを作成し、チャットの使用状況、アクティブなルーム、上位のポスターなどに関する有用なレポートの作成について理解できるようにすることです。


> [!IMPORTANT]
> Microsoft はこのスキーマを進化させる権利があります。Microsoft では、公開されたこのスキーマとの完全な下位互換性を維持することは一切保証していません。



次のベスト プラクティスに従ってください。

  - 列一覧は拡大される可能性があるため、SELECT\* // はサポートされません。

  - ユーザーが生成したスキーマの変更はサポートされません。

  - 書き込み操作はサポートされません。

  - 作成したクエリを標準的なサイズのデータベースでテストして、ニーズを満たすレベルでクエリを実行できることを確認してください。

## このセクション中

  - [Lync Server 2013 の常設チャット サーバーのテーブルのリスト](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Lync Server 2013 の常設チャット サーバーのコンプライアンス テーブルのリスト](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Lync Server 2013 の常設チャット サーバー テーブルの詳細](lync-server-2013-persistent-chat-server-table-details.md)

  - [Lync Server 2013 の常設チャット データベースのクエリのサンプル](lync-server-2013-sample-persistent-chat-database-queries.md)

