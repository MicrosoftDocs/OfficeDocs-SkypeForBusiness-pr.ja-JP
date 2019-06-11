---
title: 'Lync Server 2013: Exchange ユニファイド メッセージング (UM) のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8c952ed8aa407e2a4cbc836372c9238d4888572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Lync Server 2013 での Exchange ユニファイド メッセージング (UM) のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

Lync Server 2013 は、音声メッセージとメールメッセージを1つのメッセージングインフラストラクチャに統合するための Exchange ユニファイドメッセージング (UM) との統合をサポートしています。 Exchange 2013 では、exchange UM は、メールボックスサーバーにインストールされて実行される Exchange UM サービスで構成され、クライアントアクセスサーバー上にインストールされて実行される UM 呼び出しルーターです。 Lync Server 2013 エンタープライズ Voip 展開の場合、Exchange UM では、音声メッセージとメールメッセージが、電話からアクセスできる単一のストア (つまり、Outlook Voice Access) またはコンピューターに統合されています。 Exchange UM および Lync Server 2013 は、エンタープライズボイスのユーザーに対して、通話の応答、Outlook Voice Access、自動応答サービスを提供するために連携します。

Lync Server 2013 は、Exchange UM のオンプレミス展開との統合に加えて、ホストされた Exchange UM との統合をサポートしています。 これにより、一部またはすべてのユーザーを、Microsoft Exchange Online などのホストされた Exchange サービスプロバイダーに移行した場合に、ユーザーに音声メッセージを提供できます。

Lync Server 2013 では、次のバージョンがサポートされています。

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (必須) または最新の service pack (推奨)

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) (必須) または最新の Service pack (推奨)

Lync Server 2013 または Lync Server 2013 データベースで Exchange UM を検索することはできません。 Exchange UM と Lync Server 2013 は、別々のフォレストにインストールできます。

<div>


> [!NOTE]  
> Pbx が展開されているエンタープライズ Voip 展開では、すべてのユーザーにボイスメールと関連サービスを提供することができるため、Exchange UM が不要な場合があります。 最終的に PBX を廃止する場合 (たとえば、公衆交換電話網 (PSTN) 接続用に SIP トランクを展開した場合など) は、PBX ボイスメールシステムを使用していたユーザーにボイスメールを提供するように Exchange UM を再設定する必要があります。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 の社内ユニファイド メッセージングのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Lync Server 2013 でのホスト型 Exchange UM 統合のサポート](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

