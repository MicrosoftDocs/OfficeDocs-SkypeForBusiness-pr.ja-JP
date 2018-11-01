---
title: プライマリ管理サーバーの構成
TOCTitle: プライマリ管理サーバーの構成
ms:assetid: 44e2e9a8-c130-4c66-9871-80b1ff11b27c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204844(v=OCS.15)
ms:contentKeyID: 48271935
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# プライマリ管理サーバーの構成

 

_**トピックの最終更新日:** 2016-12-08_

Microsoft Lync Server 2013 に含まれる新しい状態監視機能を最大限に利用するために、管理者は最初にコンピューターがプライマリ管理サーバーとして動作するように指定し、そのコンピューターに System Center Operations Manager 2007 R2 または System Center Operations Manager 2012 をインストールする必要があります。さらに Operations Manager のバックエンド データベースとして機能するように、サポートされているバージョンの SQL Server をインストールする必要があります。System Center Operations Manager 2012 を使用している場合は、次のバージョンの SQL Server をバックエンド データベースとして使用できます。

  - SQL Server 2008 R2 Service Pack 1

  - SQL Server 2008 R2 Service Pack 2

System Center Operations Manager 2007 R2 を使用している場合は、SQL Server 2005 Service Pack 4 または SQL Server 2008 Service Pack 3 のどちらかをインストールすることをお勧めします。System Center Operations Manager 2007 R2 のバックエンド データベースとして SQL Server 2008 R2 を使用することもできます。System Center Operations Manager 2007 R2 と連携して動作するように SQL Server 2008 R2 を構成する方法の詳細については、このドキュメントの「付録 1」を参照してください。

System Center Operations Manager 2012 または System Center Operations Manager 2007 R2 をインストールする場合、次のような、その製品のすべてのコンポーネントをインストールする必要があります。

  - オペレーション データベース

  - サーバー

  - コンソール

  - Windows PowerShell のコマンドレット

  - Web コンソール

  - レポート

  - データ ウェアハウス

これらのコンポーネントとそのインストールの詳細については、このドキュメントでは説明しません。System Center Operations Manager 2007 R2 の詳細については、[http://go.microsoft.com/fwlink/?linkid=257526\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=257526%26clcid=0x411) の Operations Manager 2007 R2 のドキュメントと、[http://go.microsoft.com/fwlink/?linkid=257527\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=257527%26clcid=0x411) の System Center Operations Manager 2012 のドキュメントを参照してください。バックエンド データベースとして SQL Server 2005 または SQL Server 2008 Service Pack 1 を使用する場合は、これらの指示に従う必要があります。

System Center Operations Manager 2012 を使用している場合は、バックエンド データベースとして SQL Server 2012 を使用できます。SQL Server 2012 の詳細については、[http://go.microsoft.com/fwlink/?linkid=257528\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=257528%26clcid=0x411)の「SQL Server 2012 オンライン ブック」を参照してください。

Lync Server の展開ごとに設定できるのは 1 つのプライマリ管理サーバーだけであることに注意してください。また System Center Operations Manager 2012 または System Center Operations Manager 2007 R2 を使用しているときは、2 つのアプリケーションを同時に実行することはできません。どちらかを選ぶ必要があります。たとえば System Center Operations Manager 2012 を実行している場合は、すべての System Center エージェントでも System Center Operations Manager 2012 を実行している必要があります。あるエージェントでは System Center Operations Manager 2012 を実行し、別のエージェントでは System Center Operations Manager 2007 R2 を実行することはできません。

