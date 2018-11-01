---
title: バックエンド サーバー上の SQL Server のインスタンスおよびデータベースの削除
TOCTitle: バックエンド サーバー上の SQL Server のインスタンスおよびデータベースの削除
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49886904
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# バックエンド サーバー上の SQL Server のインスタンスおよびデータベースの削除

 

_**トピックの最終更新日:** 2012-10-19_

Microsoft SQL Server のデータベースとインスタンスに依存している Lync Server 2010 を実行するサーバーを削除した後、または Lync Server 2010 を実行するサーバーを別のデータベースを使用するように再構成した後で、そのデータベースとインスタンスを削除します。現在の SQL Server の使用を中止する場合、または Lync Server 2010 を実行する現在のサーバーを再構成してデータベースを廃止または使用不可にする場合は、このトピックの手順を実行する必要があります。

アーカイブ サーバーまたは 監視サーバー用のデータベースまたはインスタンスを削除するには、最初にサーバーの役割を削除する必要があります。同様に、フロント エンド プール用のインスタンスまたはデータベースを削除するには、最初に依存サーバー役割を削除または再構成する必要があります。これらの手順では、サーバーの併置されたデータベースと個別のインスタンスは区別されません。データベースの併置によって手順が影響を受けることはありません。

## このセクション中

  - [フロントエンド プールの SQL Server データベースの削除](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [監視サーバーの SQL Server データベースを削除する](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [アーカイブ サーバー用の SQL Server データベースを削除する](remove-the-sql-server-database-for-an-archiving-server.md)

