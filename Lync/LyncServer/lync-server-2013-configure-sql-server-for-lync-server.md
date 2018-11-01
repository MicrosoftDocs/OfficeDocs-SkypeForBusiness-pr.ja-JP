---
title: 'Lync Server 2013: Lync Server 用 SQL Server の構成'
TOCTitle: Lync Server 2013 用 SQL Server の構成
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48271751
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 用 SQL Server の構成

 

_**トピックの最終更新日:** 2013-08-12_

このセクションのトピックでは、Lync Server の Enterprise 展開で使用する、SQL Server を展開および構成する方法について説明します。Standard Edition サーバー サーバーは、Standard Edition サーバーの負荷に適した、併置されている SQL Server Express バージョンの SQL Server を使用します。

Lync Server 2013  中央管理ストアは、プール内のすべての Enterprise Edition サーバーのユーザー データを保持しており、SQL Server ベースのバックエンド サーバーに配置されるように設計されています。集中管理されたリポジトリである 中央管理ストアは、他の Lync Server 2013 の役割を持つコンピューターにはインストールできません。中央管理ストアは、プール内の Enterprise Edition サーバー上には配置できません。中央管理ストアは、初めてトポロジを公開し、データベースの作成を選択する際に自動的に作成されます。インストールを正常に完了させるには、バックエンド サーバーとして使用するコンピューターで、あらかじめ SQL Server データベース ソフトウェアを実行しておく必要があります。

## このセクション中

  - [Lync Server 2013 の SQL Server データとログ ファイルの配置](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Lync Server 2013 での SQL Server の構成](lync-server-2013-configure-sql-server.md)

  - [Lync Server 2013 の SQL Server の展開のアクセス許可](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Lync Server 2013 での Lync Server 管理シェルを使用したデータベースのインストール](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Lync Server 2013 での SQL Server のファイアウォール要件について](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Lync Server 2013 での SQL Server クラスタリングの構成](lync-server-2013-configure-sql-server-clustering.md)

