---
title: 'Lync Server 2013: システムプラットフォームのセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up system platforms
ms:assetid: 2e72e49d-2737-4b5b-8c0a-60f6ecb15bf1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204783(v=OCS.15)
ms:contentKeyID: 48183756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec8b2e923b4c0815449ce7fd7beb2624fe728623
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-system-platforms-in-lync-server-2013"></a>Lync Server 2013 でのシステムプラットフォームのセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

常設チャットサーバーの展開を開始する前に、サーバーのシステム要件を満たすハードウェアに、必要なオペレーティングシステムをインストールする必要があります。

Lync Server 2013、データベースサーバー、およびファイルサーバーを実行しているサーバーでサポートされているハードウェアの詳細については、「サポート」のドキュメントの「supported [hardware For Lync Server 2013](lync-server-2013-supported-hardware.md) 」を参照してください。 サポートされているオペレーティングシステムとデータベースソフトウェアの詳細については、「サポート」のドキュメントの「 [server software and infrastructure support In Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) 」を参照してください。 Windows 更新の要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 の追加サーバーサポートと要件](lync-server-2013-additional-server-support-and-requirements.md)」を参照してください。

常設チャットサーバーのフロントエンドサーバー **PersistentChatService**は、Lync Server 2013 Enterprise Edition プール内の1台以上のスタンドアロンコンピューターに展開できます。 Lync Server Enterprise Edition フロントエンドサーバーに併置することはできません。 常設チャットサーバーは、他の Lync Server の役割と同様に、ブートストラップによって展開できます。 **ファイルのアップロード/ダウンロード用の常設チャット Web サービス**、および**チャットルーム管理用の常設チャット web**サービスは、Lync Server 2013 フロントエンドサーバーに展開される web コンポーネントです。

1台の常設チャットサーバーフロントエンドサーバーでは、2万アクティブユーザーをサポートできます。 最大4つのアクティブなフロントエンドを持つ常設チャットサーバープールを使用して、合計8万の同時ユーザーをサポートすることができます。 常設チャットのバックエンドサーバー **PersistentChatStore**は、チャットルームとカテゴリを格納します。 **PersistentChatStore**は、Enterprise Edition プールの専用の SQL Server バックエンドサーバーにインストールすることをお勧めします。Lync Server 2013 バックエンドサーバーと**PersistentChatStore**を同じ SQL Server インスタンスに併置するのは、併置をサポートするものです。

組織でコンプライアンスのサポートが必要な場合は、トポロジビルダーを使用してインストールできます。 常設チャットサーバーのコンプライアンスサービスは、常設チャットサーバーのフロントエンドサーバーと同じコンピューターにインストールされます。 コンプライアンスには別のデータベースが必要です。 常設チャットサーバーのコンプライアンス要件の詳細については、「計画」のドキュメントの「 [Lync server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)」を参照してください。

少なくとも、各トポロジには、Lync Server 2013 がインストールされたサーバーと SQL Server データベースソフトウェアがインストールされたサーバーが必要です。 トポロジビルダーは、複数の常設チャットサーバープールをサポートしています。 展開のドキュメントで[Lync Server 2013](lync-server-2013-deploying-lync-server.md)を展開する場合と同じように、複数の常設チャットサーバープールを展開する場合と同じ展開手順に従います。

また、Lync Server 2013 Standard Edition を使用して常設チャットサーバーを展開することもできます。 この場合、 **PersistentChatService**フロントエンドサーバーは Standard Edition サーバーに併置されており、ローカルの SQL Server Express インスタンスに**PersistentChatStore**バックエンドサーバーを展開することができます。

<div>


> [!IMPORTANT]  
> 高可用性のために常設チャット&nbsp;サーバー Standard Edition はサポートしていません。 パフォーマンスとスケーラビリティ には制限があります。 さらに、新しい常設チャットサーバー&nbsp;Standard Edition サーバーの展開のみをサポートしています。 Lync server 2013&nbsp;常設チャットサーバー&nbsp;Standard Edition への lync server 2010 のアップグレードはサポートされていません。



</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 におけるその他のサーバーのサポートおよび要件](lync-server-2013-additional-server-support-and-requirements.md)  


[Lync Server 2013 でサポートされているハードウェア](lync-server-2013-supported-hardware.md)  
[Lync Server 2013 でのサーバーソフトウェアとインフラストラクチャのサポート](lync-server-2013-server-software-and-infrastructure-support.md)  
[Lync Server 2013 での常設チャットサーバーの計画](lync-server-2013-planning-for-persistent-chat-server.md)  
[Lync Server 2013 の展開 ](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

