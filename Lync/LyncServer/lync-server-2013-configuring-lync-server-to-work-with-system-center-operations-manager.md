---
title: System Center Operations Manager と共に実行する Lync Server の構成
TOCTitle: System Center Operations Manager と共に実行する Lync Server の構成
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48273346
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# System Center Operations Manager と共に実行する Lync Server の構成

 

_**トピックの最終更新日:** 2012-10-22_

Microsoft Lync Server 2013 インフラストラクチャを構成して System Center Operations Manager を操作するためには、次の 3 つのことを行う必要があります。

  - プライマリ System Center Operations Manager 管理サーバーを特定して構成します。管理サーバーの構成には、System Center Operations Manager 2012 または System Center Operations Manager 2007 R2 のインストール、および SQL Server を使用するバックエンド データベースのセットアップが含まれます。使用する必要がある SQL Server の実際のバージョンは、使用している System Center Operations Manager のバージョンによって異なります。詳細については、「[プライマリ管理サーバーの構成](lync-server-2013-configuring-the-primary-management-server.md)」を参照してください。

  - 監視する Lync Server コンピューターを特定して構成します。System Center Operations Manager を使用して Lync Server コンピューターを監視するには、System Center Operations Manager エージェント ファイルをインストールし、プロキシとして動作するように各サーバーを構成する必要があります。

  - Lync Server*監視ノード*として動作するコンピューターを特定して構成します。監視ノードとは、Lync Server 代理トランザクションを定期的に実行するコンピューターのことです。代理トランザクションは、システムへのログオン機能やインスタント メッセージの交換機能などの主要な Lync Server コンポーネントが正常に動作することを検証する Windows PowerShell コマンドレットです。

このセクションのトピックでは、これらの各タスクを実行するための手順について説明しています。

## このセクションの内容

  - [プライマリ管理サーバーの構成](lync-server-2013-configuring-the-primary-management-server.md)

  - [Lync Server 2013 管理パックのインストール](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Lync Server コンピューターを監視する構成](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [監視ノードの構成とインストール](lync-server-2013-installing-and-configuring-watcher-nodes.md)

