---
title: 'Lync Server 2013: 障害回復のための拡張型の常設チャット サーバー プールの使用'
TOCTitle: 障害回復のための拡張型の常設チャット サーバー プールの使用
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48272471
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 における障害回復のための拡張型の常設チャット サーバー プールの使用

 

_**トピックの最終更新日:** 2012-10-06_

常設チャット サーバーの障害復旧ソリューションは、拡張型の 常設チャット サーバー プール上に構築されています。これは、Lync Server 2010 における大都市サイトの復元に類似しています。ただし、ストレッチ仮想ローカル エリア ネットワークに関する要件はありません。常設チャット サーバー プールを拡張することで、論理的にはトポロジ内に 1 つのプールを原則として構成しますが、物理的にはこのプール内のサーバーを 2 つの異なるデータ センターに配置することになります。データベースの SQL Server ミラーリングを同じ方法で構成し、データベースとそのミラーを同じデータ センター内に展開します。セカンダリ データ センターでは、(障害復旧時に高可用性を提供するためにオプションのミラーを使用して) バックアップ データベースを構成する必要があります。これは、障害復旧時にフェールオーバー用に使用されるバックアップ データベースです。

SQL Server ミラーリングを高可用性のために構成する方法の詳細については、「[Lync Server 2013 での SQL Server のミラーリング](lync-server-2013-sql-server-mirroring.md)」を参照してください。障害復旧のためのデータベースのフェールオーバーの詳細については、「[Lync Server 2013 で常設チャット サーバーのプライマリ データベースの SQL Server ログ配布を設定する](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)」と「[Lync Server 2013 でのプライマリ ミラーとログ配布セカンダリ データベース間での SQL Server ログ配布のセットアップ](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md)」を参照してください。

