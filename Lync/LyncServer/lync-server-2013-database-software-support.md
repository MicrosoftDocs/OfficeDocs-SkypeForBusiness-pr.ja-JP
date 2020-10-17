---
title: Lync Server 2013 データベースソフトウェアのサポート
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
ms.openlocfilehash: 7f7290a6d4e80c522d29c886b49723cca51d19e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516504"
---
# <a name="database-software-support-in-lync-server-2013"></a>Lync Server 2013 でのデータベースソフトウェアのサポート

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-12-01_

Lync Server 2013 では、次のデータベース管理システムがサポートされています。

  - **フロントエンドプールのバックエンドデータベース、アーカイブデータベース、監視データベース、常設チャットデータベース、および常設チャットコンプライアンスデータベース**
    
      - Microsoft SQL Server 2008 R2 Enterprise データベースソフトウェア (64 ビット版)。 また、最新のサービスパックを実行することをお勧めします。
    
      - Microsoft SQL Server 2008 R2 Standard (64-ビット版)。 また、最新のサービスパックを実行することをお勧めします。
    
      - Microsoft SQL Server 2012 Enterprise (64 ビット版)。 また、最新のサービスパックを実行することをお勧めします。
    
      - Microsoft SQL Server 2012 Standard (64 ビット版)。 また、最新のサービスパックを実行することをお勧めします。

  - **Standard Edition サーバーデータベースとフロントエンドサーバーデータベース**
    
      - Microsoft SQL Server 2012 Express (64 ビット版)。 また、最新のサービスパックを実行することをお勧めします。
        
        フロントエンドサーバーおよび Standard Edition サーバー上での Microsoft SQL Server のパッチとアップグレードをサポートしています。 ただし、フロントエンドサーバーで任意の種類のアップグレードまたはパッチを作成する場合は、クォーラム要件を考慮する必要があります。 詳細については、「lync [server 2013 でのフロントエンドサーバーのアップグレードまたは更新](lync-server-2013-upgrade-or-update-front-end-servers.md) 」および「 [lync server 2013 でのフロントエンドサーバー、インスタントメッセージング、プレゼンスのトポロジとコンポーネント](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64 ビット版) は、各 Standard Edition サーバーと各フロントエンドサーバーサーバーに Lync Server 2013 によって自動的にインストールされます。

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013 は、32ビット版の SQL Server をサポートしていません。 64ビット版を使用する必要があります。</P>
> <LI>
> <P>SQL Server Web edition および SQL Server Workgroup edition はサポートされていません。 これらを Lync Server 2013 で使用することはできません。</P>
> <LI>
> <P>Lync Server 2013 は、ネイティブデータベースミラーリングをサポートしています。</P>
> <LI>
> <P>監視サーバーの役割を使用するには、SQL Server Reporting Services をインストールする必要があります。</P></LI></UL>



</div>

フロントエンドプールでは、バックエンドデータベースを単一の SQL Server コンピューターにすることができます。

<div>


> [!IMPORTANT]  
> Lync Server データベースを他のデータベースと併置する場合は、可用性とパフォーマンスに影響する可能性のあるすべての要因を評価し、一方のノードに障害が発生した場合は、残りのノードが負荷を処理できることを確認することを強くお勧めします。 フェールオーバー機能を検証する場合は、すべてのフェールオーバー シナリオをテストすることをお勧めします。



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>SQL ミラーリングと SQL クラスタリングの使用

Lync Server 2013 では、各 Lync Server データベースに対して SQL ミラーリングまたは SQL クラスタリングの使用をサポートしています。 Lync Server 2013 のトポロジビルダーツールを使用して、SQL ミラーリングを簡単にセットアップできます。 SQL フェールオーバークラスタリングでは、セットアップに SQL Server を使用する必要があります。

Lync server 2013 では、greenfield の展開や、以前のバージョンの Lync Server からアップグレードした組織を含む、すべての展開において SQL ミラーリングと SQL クラスタリングの両方のトポロジがサポートされています。

SQL クラスタリングは、アクティブ/パッシブ構成でサポートされています。 パフォーマンス上の理由から、パッシブノードは他の SQL インスタンスと共有しないでください。

次のサポートが含まれています。

  - 次の2ノードフェールオーバークラスタリング:
    
      - Microsoft SQL Server 2012 Standard (64 ビット版)。 また、最新のサービスパックを実行することをお勧めします。
    
      - Microsoft SQL Server 2008 R2 Standard (64-ビット版)。 また、最新のサービスパックを実行することをお勧めします。

  - 最大16ノードのフェールオーバークラスタリングは次のとおりです。
    
      - Microsoft SQL Server 2012 Enterprise (64 ビット版)。 また、最新のサービスパックを実行することをお勧めします。
    
      - Microsoft SQL Server 2008 R2 Enterprise データベースソフトウェア (64 ビット版)。 また、最新のサービスパックを実行することをお勧めします。

SQL ミラーリングの詳細については、「 [Lync server 2013 のバックエンドサーバーの高可用性](lync-server-2013-back-end-server-high-availability.md)」を参照してください。 SQL クラスタリングを展開する方法の詳細については、「 [CONFIGURE Sql Server クラスタリング For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)」を参照してください。

SQL Server 2012 のフェールオーバークラスタリングの詳細とベストプラクティスについては、「」を参照してください <https://technet.microsoft.com/library/hh231721.aspx> 。 SQL Server 2008 のフェールオーバークラスタリングについては、「」を参照してください <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

