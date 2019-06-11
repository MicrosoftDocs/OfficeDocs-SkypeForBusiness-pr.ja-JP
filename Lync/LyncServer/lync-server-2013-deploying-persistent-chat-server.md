---
title: 'Lync Server 2013: 常設チャット サーバーの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a730057735f187dc5e5080d532515a4eb9db110
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 での常設チャット サーバーの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-03-31_

Lync Server 2013、常設チャットサーバーは Lync Server 2013 インフラストラクチャの一部です。

常設チャットサーバーを展開するには、次のことを行う必要があります。

  - トポロジビルダーを使って、トポロジと展開するコンポーネントを定義またはインポートして、その後で公開します。

  - 常設チャットサーバーコンポーネントを展開するための環境を準備します。

  - 展開用の常設チャットサーバーコンポーネントをインストールして構成します。

常設チャットサーバーは、Lync Server 2013 Enterprise Edition と個別のプールとして利用できます (Enterprise Edition のフロントエンドサーバーとは対応していません)。 常設チャットサーバーには、チャットルームのコンテンツやその他の関連するメタデータを保存するために、Enterprise Edition プールに SQL Server バックエンドサーバーが必要です。 **PersistentChatStore**は、専用の Sql server バックエンドサーバーにインストールすることをお勧めします。ただし、同一の sql server インスタンスで Lync server 2013 のバックエンドサーバーと**PersistentChatStore**を同じ列に配置することはサポートされています。

常設チャットサーバーは、Lync Server 2013 Standard Edition と共に展開することもできます。 この場合、 **PersistentChatService**フロントエンドサーバーは Standard Edition コンピューターにあり、 **PersistentChatStore**バックエンドサーバーはローカルの SQL Server Express インスタンスに展開できます。

サポートされているコロケーション構成の詳細については、「 [Lync server 2013 でサポートされているサーバーの collocation](lync-server-2013-supported-server-collocation.md)」を参照してください。

<div>


> [!IMPORTANT]  
> 常設チャット Server&nbsp;Standard Edition では、高可用性をサポートしていません。 パフォーマンスとスケールは制限されます。 さらに、新しい常設チャット Server&nbsp;Standard Edition Server のみをサポートしています。 Lync Server 2010、グループチャットサーバーを Lync Server 2013&nbsp;常設 Chat Server&nbsp;Standard Edition にアップグレードすることはサポートされていません。



</div>

組織でコンプライアンスのサポートが必要な場合は、常設チャットサーバーコンプライアンスサービスを常設チャットサーバーのフロントエンドサーバーにインストールできます。 コンプライアンスには、別のデータベースが必要です。

少なくとも、各トポロジには、Lync Server 2013 がインストールされているサーバーと SQL Server データベースソフトウェアがインストールされたサーバーが必要です。

[トポロジビルダーを使用して、Lync Server 2013 展開に常設チャットサーバーを追加します。 Topology Builder を使用して、1つ以上の常設チャットサーバープールを追加できます。 任意のプールの場合と同様に、複数の常設チャットサーバープールを展開する場合と同じ展開手順に従います。 詳細については、「展開ドキュメントの[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)」を参照してください。

利用可能なトポロジと、常設チャットサーバーをインストールするための技術およびソフトウェアの要件の詳細については、「 [Lync server 2013 での](lync-server-2013-planning-for-persistent-chat-server.md)常設チャットサーバーの計画」を参照してください。 [Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md)の計画ドキュメント、展開ドキュメント、または運用マニュアルに記載されています。また、[サポートされているドキュメントの lync server 2013 でサポートされているハードウェア](lync-server-2013-supported-hardware.md)。

証明書の取得、SQL Server データベースの作成、ファイルストアの作成の詳細については、「展開ドキュメントに[Lync Server 2013 を展開](lync-server-2013-deploying-lync-server.md)する」を参照してください。

1つの常設チャットサーバーフロントエンドサーバーは、2万アクティブユーザーをサポートできます。 最大4つのアクティブなフロントエンドサーバーには、常設チャットサーバープールを含めることができます。これには、合計8万の同時ユーザーがサポートされています。

常設チャットサーバーも仮想サーバーでサポートされています。 仮想サーバーは、物理サーバーの仕様と一致した場合に、最大で2万の同時ユーザーをサポートできます。

<div>


> [!IMPORTANT]  
> ファイルシステムのセキュリティを適用するには、常設チャットサーバーが NTFS ファイルシステムにインストールされている必要があります。 FAT32 は、常設チャットサーバーでサポートされているファイルシステムではありません。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での常設チャットサーバーの動作方法](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lync Server 2013 の常設チャット サーバーの展開チェックリスト](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Lync Server 2013 の常設チャットサーバーの技術要件](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013 での常設チャット サーバーのシステムおよびインフラストラクチャのセットアップ](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Lync Server 2013 での展開への常設チャットサーバーの追加](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Lync Server 2013 での常設チャット サーバーのインストール](lync-server-2013-installing-persistent-chat-server.md)

  - [Lync Server 2013 での常設チャット管理者の追加](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Lync Server 2013 での常設チャット サーバーの構成](lync-server-2013-configuring-persistent-chat-server.md)

  - [Windows PowerShell コマンドレットを使用した常設チャット サーバーの構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Lync Server 2013 での Windows PowerShell コマンドレットを使用した常設チャット サーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Lync Server 2013 の高可用性と障害復旧に対応した常設チャット サーバーの構成](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2013 での常設チャット サーバーのフェールオーバーとフェールバック](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

