---
title: 常設チャット データの復元
TOCTitle: 常設チャット データの復元
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945649(v=OCS.15)
ms:contentKeyID: 52056698
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 常設チャット データの復元

 

_**トピックの最終更新日:** 2013-02-18_

常設チャット ルームのコンテンツは、常設チャット データベース (mgc.mdf) に格納されます。これは、定期的なバックアップが必要なビジネス上重要なデータです。常設チャット データベースには、チャット ルームのコンテンツのほかに、プリンシパル (ユーザー、グループなど)、役割、およびチャット ルームやチャット ルームのコンテンツへのアクセスに関する情報も含まれます。

常設チャット データの復元方法は、バックアップに使用した方法に応じて異なります。

  - SQL Server のバックアップ手順を使用した場合は、SQL Server の復元手順を使用する必要があります。

  - **Export-CsPersistentChatData** コマンドレットを使用して常設チャット データをバックアップした場合は、データの復元に **Import-CsPersistentChatData** コマンドレットを使用する必要があります。

