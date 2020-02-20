---
title: 'Lync Server 2013: 常設チャットサーバーの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a23190033bca9047a3d1a6d70b914d02017db8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013 での常設チャットサーバーの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-03-31_

Lync Server 2013、常設チャットサーバーは Lync Server 2013 インフラストラクチャの一部です。

常設チャットサーバーを展開するには、次のことを行う必要があります。

  - トポロジビルダーを使用して、展開するトポロジとコンポーネントを定義またはインポートし、続けて公開します。

  - 常設チャットサーバーコンポーネントを展開するための環境を準備します。

  - 展開用に常設チャットサーバーコンポーネントをインストールして構成します。

常設チャットサーバーは、Lync Server 2013 Enterprise Edition と別のプールとして使用できます (Enterprise Edition フロントエンドサーバーと併置されていません)。 常設チャットサーバーには、エンタープライズエディションのプールに SQL Server バックエンドサーバーが必要です。これには、チャットルームのコンテンツやその他の関連するメタデータを格納します。 **PersistentChatStore**は、専用の Sql Server バックエンドサーバーにインストールすることをお勧めします。ただし、Lync server 2013 のバックエンドサーバーと**PERSISTENTCHATSTORE**を同じ sql server インスタンスに併置することはサポートされています。

常設チャットサーバーは、Lync Server 2013 Standard Edition と共に展開することもできます。 この場合、 **PersistentChatService**フロントエンドサーバーは Standard Edition コンピューターに併置され、 **PersistentChatStore**バックエンドサーバーをローカルの SQL Server Express インスタンスに展開することができます。

サポートされている colocation 構成の詳細については、「 [Lync server 2013 でサポートされるサーバーの併置](lync-server-2013-supported-server-collocation.md)」を参照してください。

<div>


> [!IMPORTANT]  
> 常設チャットサーバー&nbsp;Standard Edition では高可用性がサポートされていません。 パフォーマンスとスケーラビリティ には制限があります。 さらに、新しい常設チャットサーバー&nbsp;Standard Edition サーバーのみをサポートしています。 Lync server 2010 のグループチャットサーバーから Lync Server 2013&nbsp;常設チャットサーバー&nbsp;Standard Edition へのアップグレードはサポートされていません。



</div>

組織でコンプライアンスサポートが必要な場合は、常設チャットサーバーのフロントエンドサーバーに常設チャットサーバーコンプライアンスサービスをインストールすることができます。 コンプライアンスには別のデータベースが必要です。

少なくとも、各トポロジには、Lync Server 2013 がインストールされたサーバーと SQL Server データベースソフトウェアがインストールされたサーバーが必要です。

トポロジビルダーを使用して、Lync Server 2013 展開に常設チャットサーバーを追加します。 トポロジビルダーを使用して、1つまたは複数の常設チャットサーバープールを追加することを選択できます。 他のプールの場合と同じように、複数の常設チャットサーバープールを展開する場合の同じ展開手順に従います。 詳細については、「展開」のドキュメントの「[Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md)」を参照してください。

利用可能なトポロジの詳細、および常設チャットサーバーをインストールするための技術およびソフトウェアの要件の詳細については、「計画」の[](lync-server-2013-how-persistent-chat-server-works.md)ドキュメントの「Planning [for persistent Chat 2013 2013 server](lync-server-2013-planning-for-persistent-chat-server.md) 」、「計画」のドキュメント、「展開」のドキュメント、または「操作」のドキュメント、および「サポート」2013のドキュメントの「[サポートされるハードウェア](lync-server-2013-supported-hardware.md)」を参照

証明書の取得、SQL Server データベースの作成、およびファイルストアの作成の詳細については、「展開」のドキュメントの「[展開 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 」を参照してください。

1台の常設チャットサーバーフロントエンドサーバーでは、2万アクティブユーザーをサポートできます。 合計8万の同時ユーザーをサポートする最大4台のアクティブなフロントエンドサーバーで、常設チャットサーバープールを使用することができます。

常設チャットサーバーは、仮想サーバーでもサポートされています。 仮想サーバーは、物理サーバーの仕様に適合していれば、20,000 人のユーザーまで同時にサポートできます。

<div>


> [!IMPORTANT]  
> ファイルシステムのセキュリティを適用するには、NTFS ファイルシステムに常設チャットサーバーをインストールする必要があります。 FAT32 は、常設チャットサーバー用のファイルシステムとしてサポートされていません。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での常設チャットサーバーの動作](lync-server-2013-how-persistent-chat-server-works.md)

  - [Lync Server 2013 の常設チャットサーバーの展開チェックリスト](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [Lync Server 2013 の常設チャットサーバーの技術要件](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013 での常設チャットサーバーのシステムおよびインフラストラクチャのセットアップ](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [Lync Server 2013 での展開への常設チャットサーバーの追加](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [Lync Server 2013 での常設チャットサーバーのインストール](lync-server-2013-installing-persistent-chat-server.md)

  - [Lync Server 2013 での常設チャット管理者の追加](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [Lync Server 2013 での常設チャットサーバーの構成](lync-server-2013-configuring-persistent-chat-server.md)

  - [Windows PowerShell コマンドレットを使用して常設チャットサーバーを構成する](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [Lync Server 2013 での Windows PowerShell コマンドレットを使用した常設チャットサーバー構成のトラブルシューティング](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [Lync Server 2013 での高可用性および障害復旧用の常設チャットサーバーの構成](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2013 での常設チャットサーバーのフェールオーバーとフェールバック](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

