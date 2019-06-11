---
title: 'Lync Server 2013: システム プラットフォームを設定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 317bfe0efed0417d49cc59dc8f6e7ad3bcca7d7a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>Lync Server 2013 でシステム プラットフォームを設定する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-21_

常設チャットサーバーの展開を開始する前に、サーバー上のシステム要件を満たすハードウェアに必要なオペレーティングシステムをインストールする必要があります。

Lync Server 2013、データベースサーバー、およびファイルサーバーを実行しているサーバーでサポートされているハードウェアの詳細については、サポートされているドキュメントで「 [Lync server 2013 でサポートされているハードウェア](lync-server-2013-supported-hardware.md)」を参照してください。 サポートされているオペレーティングシステムとデータベースソフトウェアの詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート](lync-server-2013-server-software-and-infrastructure-support.md)」を参照してください。 Windows の更新の要件の詳細については、サポートドキュメントの「 [Lync server 2013 のその他のサーバーのサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。

常設チャットサーバーのフロントエンドサーバーである**PersistentChatService**は、Lync Server 2013 Enterprise Edition プールの1つ以上のスタンドアロンコンピューターに展開することができます。 Lync Server Enterprise Edition のフロントエンドサーバーには、それらを併置することはできません。 常設チャットサーバーは、他の Lync Server の役割と同じように、ブートストラップによって展開できます。 **ファイルのアップロード/ダウンロード用の常設チャット Web サービス**と**チャットルーム管理用の常設チャット web サービス**は、Lync Server 2013 フロントエンドサーバーに展開されている web コンポーネントです。

1つの常設チャットサーバーフロントエンドサーバーは、2万アクティブユーザーをサポートできます。 最大4つのアクティブなフロントエンドの常設チャットサーバープールで、合計8万人の同時ユーザーをサポートすることができます。 常設チャットバックエンドサーバー **PersistentChatStore**は、チャットルームとカテゴリを保存します。 **PersistentChatStore**は、Enterprise Edition プールの専用 SQL Server バックエンドサーバーにインストールすることをお勧めします。ただし、同じ SQL Server インスタンス上での Lync Server 2013 バックエンドサーバーと**PersistentChatStore**の検索はサポートされています。

組織でコンプライアンスのサポートが必要な場合は、トポロジビルダーを使用してインストールできます。 常設チャット Server コンプライアンスサービスは、常設チャットサーバーフロントエンドサーバーと同じコンピューターにインストールされています。 コンプライアンスには、別のデータベースが必要です。 常設チャットサーバーのコンプライアンス要件の詳細については、計画ドキュメントの「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。

少なくとも、各トポロジには、Lync Server 2013 がインストールされているサーバーと SQL Server データベースソフトウェアがインストールされたサーバーが必要です。 Topology Builder は、複数の常設チャットサーバープールをサポートしています。 展開ドキュメントに[Lync Server 2013 を展開](lync-server-2013-deploying-lync-server.md)する場合と同様に、複数の常設チャットサーバープールを展開する場合と同じ展開手順に従います。

また、Lync Server 2013 Standard Edition で常設チャットサーバーを展開することもできます。 この場合、 **PersistentChatService**フロントエンドサーバーは Standard Edition サーバー上に配置されているため、 **PersistentChatStore**バックエンドサーバーをローカルの SQL Server Express インスタンスに展開することができます。

<div>


> [!IMPORTANT]  
> 高可用性を実現する常設 Chat&nbsp;Server 標準エディションはサポートされていません。 パフォーマンスとスケールは制限されます。 さらに、新しい常設チャット Server&nbsp;Standard Edition server の展開のみをサポートしています。 Lync server 2010、グループチャットサーバーを Lync Server 2013&nbsp;常設 Chat Server&nbsp;Standard Edition にアップグレードすることはサポートされていません。



</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の追加サーバー サポートおよび要件](lync-server-2013-additional-server-support-and-requirements.md)  


[Lync Server 2013 でサポートされるハードウェア](lync-server-2013-supported-hardware.md)  
[Lync Server 2013 でのサーバーのソフトウェアおよびインフラストラクチャ サポート](lync-server-2013-server-software-and-infrastructure-support.md)  
[Lync Server 2013 での常設チャット サーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)  
[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

