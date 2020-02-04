---
title: 'Lync Server 2013: データベース ソフトウェアのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4c39a51f742266c12f618f687c23c645977ffdb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Lync Server 2013 でのデータベース ソフトウェアのサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-12-01_

Lync Server 2013 では、次のデータベース管理システムがサポートされています。

  - **フロントエンド プールのバックエンド データベース、アーカイブ データベース、監視データベース、グループ チャット データベース、およびグループ チャット コンプライアンス データベース**
    
      - Microsoft SQL Server 2008 R2 Enterprise データベース ソフトウェア (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。
    
      - Microsoft SQL Server 2008 R2 Standard (64 ビット版)。 追加で最新のサービス パックを実行することをお勧めします。
    
      - Microsoft SQL Server 2012 Enterprise (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。
    
      - Microsoft SQL Server 2012 Standard (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。

  - **Standard Edition server データベースとフロントエンドサーバーデータベース**
    
      - Microsoft SQL Server 2012 Express (64 ビット版)。 追加で最新のサービス パックを実行することをお勧めします。
        
        Microsoft は、フロントエンドサーバーと Standard Edition サーバーにおける Microsoft SQL Server の修正プログラムとアップグレードをサポートしています。 ただし、フロントエンドサーバーに対して何らかのアップグレードまたは更新プログラムを作成する場合は、クォーラム要件を考慮する必要があります。 詳細については、「[Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)」および「[Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64 ビット版) は、Lync Server 2013 (各標準エディションサーバーおよび各フロントエンドサーバーサーバー上) によって自動的にインストールされます。

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 では、32ビット版の SQL Server はサポートされていません。 64 ビット版を使用する必要があります。</P>
> <LI>
> <P>SQL Server Web edition と SQL Server Workgroup edition はサポートされていません。 Lync Server 2013 では使用できません。</P>
> <LI>
> <P>Lync Server 2013 では、ネイティブデータベースのミラーリングがサポートされています。</P>
> <LI>
> <P>監視サーバーの役割を使用するには、SQL Server Reporting Services をインストールする必要があります。</P></LI></UL>



</div>

フロントエンドプールでは、バックエンドデータベースを単一の SQL Server コンピューターにすることができます。

<div>


> [!IMPORTANT]  
> 他のデータベースを使用して Lync Server データベースを作成する場合は、可用性とパフォーマンスに影響する可能性のあるすべての要素を評価することと、1つのノードに障害が発生した場合に、残りのノードがその読み込みを処理できることを確認することを強くお勧めします。 フェールオーバー機能を検証する場合は、すべてのフェールオーバー シナリオをテストすることをお勧めします。



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>SQL ミラーリングと SQL クラスタリングの使用

Lync Server 2013 では、各 Lync Server データベースに対して SQL ミラーリングと SQL クラスタリングのいずれかがサポートされています。 Lync Server 2013 のトポロジビルダーツールを使用して、簡単に SQL ミラーリングを設定することができます。 SQL フェールオーバー クラスタリングの場合、設定に SQL Server を使用する必要があります。

Lync Server 2013 は、以前のバージョンの Lync Server からアップグレードしたから始めの展開や組織を含む、すべての展開で SQL ミラーリングと SQL クラスタリングのトポロジの両方をサポートしています。

SQL クラスタリングのサポートは、アクティブ/パッシブ構成用です。パフォーマンス上の理由から、パッシブ ノードを他の SQL インスタンスと共有しないでください。

次のサポートが含まれます。

  - 以下の製品用の 2 ノードのフェールオーバー クラスタリング:
    
      - Microsoft SQL Server 2012 Standard (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。
    
      - Microsoft SQL Server 2008 R2 Standard (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。

  - 以下の製品用の最大 16 ノードのフェールオーバー クラスタリング:
    
      - Microsoft SQL Server 2012 Enterprise (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。
    
      - Microsoft SQL Server 2008 R2 Enterprise データベース ソフトウェア (64 ビット版)。追加で最新のサービス パックを実行することをお勧めします。

SQL のミラーリングの詳細については、「 [Lync Server 2013 のバックエンドサーバーの高可用性](lync-server-2013-back-end-server-high-availability.md)」を参照してください。 SQL クラスタリングの展開方法の詳細については、「 [Lync server 2013 用の Sql Server クラスタリングを構成](lync-server-2013-configure-sql-server-clustering.md)する」を参照してください。

SQL Server 2012 のフェールオーバークラスタリングの詳細とベストプラクティスについて<http://technet.microsoft.com/en-us/library/hh231721.aspx>は、を参照してください。 SQL Server 2008 のフェールオーバークラスタリングについ<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>ては、を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

