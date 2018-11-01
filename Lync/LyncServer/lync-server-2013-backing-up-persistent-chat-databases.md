---
title: 常設チャット データベースのバックアップ
TOCTitle: 常設チャット データベースのバックアップ
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945646(v=OCS.15)
ms:contentKeyID: 52056687
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 常設チャット データベースのバックアップ

 

_**トピックの最終更新日:** 2013-02-17_

常設チャット ルームのコンテンツは、常設チャット データベース (Mgc.mdf) に格納されます。これは、定期的なバックアップが必要なビジネス上重要なデータです。常設チャット データベースには、チャット ルームのコンテンツのほかに、プリンシパル (ユーザー、ユーザー グループなど)、役割、およびチャット ルームへのアクセスに関する情報が含まれます。

常設チャット データのバックアップには、2 つの方法があります。

  - SQL Server バックアップ

  - 常設チャット データをファイルとしてエクスポートする `Export-CsPersistentChatData` コマンドレット

SQL Server バックアップを使用して作成されたデータには、非常に多くのディスク容量 (場合によっては、`Export-CsPersistentChatData` で作成される場合の 20 倍) が必要ですが、SQL Server バックアップは、管理者がよく利用する方法です。

