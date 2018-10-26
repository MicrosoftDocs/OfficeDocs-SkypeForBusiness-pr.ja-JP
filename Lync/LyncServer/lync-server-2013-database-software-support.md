---
title: 'Lync Server 2013: データベース ソフトウェアのサポート'
TOCTitle: データベース ソフトウェアのサポート
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48273828
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのデータベース ソフトウェアのサポート

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 は、次のデータベース管理システムをサポートしています。

  - **フロントエンド プールのバックエンド データベース、アーカイブ データベース、監視データベース、グループ チャット データベース、およびグループ チャット コンプライアンス データベース**
    
      - Microsoft SQL Server 2008 R2 Enterprise データベース ソフトウェア (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。
    
      - Microsoft SQL Server 2008 R2 Standard (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。
    
      - Microsoft SQL Server 2012 Enterprise (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。
    
      - Microsoft SQL Server 2012 Standard (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。

  - **Standard Edition サーバー データベースと フロント エンド サーバー データベース**
    
      - Microsoft SQL Server 2012 Express (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。
        
        フロント エンド サーバー および Standard Edition サーバー での Microsoft SQL Server へのパッチ適用およびアップグレードをサポートしています。ただし、フロント エンド サーバー で何らかの種類のアップグレードまたはパッチを行う場合は、クォーラム要件を考慮する必要があります。詳細については、「[Lync Server 2013 でのフロントエンド サーバーのアップグレードまたは更新](lync-server-2013-upgrade-or-update-front-end-servers.md)」および「[Lync Server 2013 フロントエンド サーバー、インスタント メッセージングおよびプレゼンスのトポロジおよびコンポーネント](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。
    
    > [!NOTE]
    > Microsoft SQL Server 2012 Express (64 ビット版) は、Lync Server 2013 によって、各 Standard Edition サーバーと各 フロント エンド サーバー サーバーに自動的にインストールされます。



> [!IMPORTANT]
> <UL>
> <LI>
> <P>Lync Server 2013 では、 SQL Server32 ビット版はサポートされていません。64 ビット版を使用する必要があります。</P>
> <LI>
> <P>SQL Server Web edition と SQL Server Workgroup edition はサポートされていません。これらのエディションは Lync Server 2013 とともに使用できません。</P>
> <LI>
> <P>Lync Server 2013 では、ネイティブ データベース ミラーリングはサポートされていません。</P>
> <LI>
> <P>監視サーバーの役割を使用するには、 SQL Server レポート サービスをインストール必要があります。</P></LI></UL>



フロントエンド プールでは、1 台の SQL Server コンピューターをバック エンド データベースとして使用できます。


> [!IMPORTANT]
> Lync Serverデータベースを他のデータベースと一緒に使用する場合は、可用性とパフォーマンスに影響を与える可能性のあるすべての要素を評価すること、さらに 1 つのノードが失敗した場合に、残りのノードが負荷に対応できるようにすることを強くお勧めします。フェールオーバー機能を検証する場合は、すべてのフェールオーバー シナリオをテストすることをお勧めします。



## SQL ミラーリングと SQL クラスタリングの使用

Lync Server 2013 では、Lync Server データベースごとの SQL ミラーリングや SQL クラスタリングの使用をサポートしています。 Lync Server 2013 では トポロジ ビルダー ツールを使用して、SQL ミラーリングを簡単に設定できます。SQL フェールオーバー クラスタリングの場合、設定に SQL Server を使用する必要があります。

Lync Server 2013 では、すべての展開 (新規展開や、前のバージョンの Lync Server からアップグレードした組織を含む) で SQL ミラーリングと SQL クラスタリング両方のトポロジをサポートしています。

SQL クラスタリングのサポートは、アクティブ/パッシブ構成用です。パフォーマンス上の理由から、パッシブ ノードを他の SQL インスタンスと共有しないでください。

次のサポートが含まれます。

  - 以下の製品用の 2 ノードのフェールオーバー クラスタリング:
    
      - Microsoft SQL Server 2012 Standard (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。
    
      - Microsoft SQL Server 2008 R2 Standard (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。

  - 以下の製品用の最大 16 ノードのフェールオーバー クラスタリング:
    
      - Microsoft SQL Server 2012 Enterprise (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。
    
      - Microsoft SQL Server 2008 R2 Enterprise データベース ソフトウェア (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。

SQL ミラーリングの詳細については、「[Lync Server 2013 のバックエンド サーバーの高可用性](lync-server-2013-back-end-server-high-availability.md)」を参照してください。SQL クラスタリングの展開方法の詳細については、「[Lync Server 2013 での SQL Server クラスタリングの構成](lync-server-2013-configure-sql-server-clustering.md)」を参照してください。

SQL Server 2012 のフェールオーバー クラスタリングの詳細とベスト プラクティスについては、<http://technet.microsoft.com/ja-jp/library/hh231721.aspx> を参照してください。SQL Server 2008 のフェールオーバー クラスタリングについては、<http://technet.microsoft.com/ja-jp/library/ms189134(v=sql.105).aspx> を参照してください。

