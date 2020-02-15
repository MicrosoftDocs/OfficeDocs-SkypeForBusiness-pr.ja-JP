---
title: 'Lync Server 2013: Exchange ユニファイドメッセージング (UM) のサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange Unified Messaging (UM) support
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398179(v=OCS.15)
ms:contentKeyID: 48183405
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e906b6194572d0ed7f797a2be64c7b66982436b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-unified-messaging-um-support-in-lync-server-2013"></a>Lync Server 2013 での Exchange ユニファイドメッセージング (UM) のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

Lync Server 2013 は、ボイスメッセージングと電子メールメッセージングを単一のメッセージングインフラストラクチャに結合するための Exchange ユニファイドメッセージング (UM) との統合をサポートしています。 Exchange 2013 では、exchange UM はメールボックスサーバー上にインストールされて実行される Exchange UM サービスで構成され、UM 呼び出しルーターはクライアントアクセスサーバー上にインストールされて実行されます。 Lync Server 2013 エンタープライズ Voip 展開の場合、Exchange UM はボイスメッセージングと電子メールメッセージングを、電話 (つまり、Outlook Voice Access) またはコンピューターからアクセスできる単一のストアに結合します。 Exchange UM と Lync Server 2013 は連携して、エンタープライズ Voip のユーザーに通話応答、Outlook Voice Access、および自動応答サービスを提供します。

Exchange UM の社内展開との統合のサポートに加えて、Lync Server 2013 では、hosted Exchange UM との統合がサポートされています。 これにより、Microsoft Exchange Online などの Hosted Exchange サービス プロバイダーにユーザーの一部または全部を移行すると、音声メッセージングをユーザーに提供できるようになります。

Lync Server 2013 では、次のバージョンがサポートされています。

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010 (必須) または最新の service pack (推奨)

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) (必須) または最新のサービスパック (推奨)

Exchange UM を Lync Server 2013 または Lync Server 2013 データベースと併置することはできません。 Exchange UM と Lync Server 2013 は、別のフォレストにインストールできます。

<div>


> [!NOTE]  
> Pbx は、すべてのユーザーにボイスメールと関連サービスを継続的に提供できるため、PBX が展開されているエンタープライズ Voip 展開では Exchange UM を必要としない場合があります。 最終的に PBX の使用を中止した場合 (たとえば、公衆交換電話網 (PSTN) 接続用に SIP トランキングを展開する場合)、Exchange UM を再構成して、以前 PBX ボイスメールシステムを使用していたユーザーにボイスメールを提供する必要があります。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのオンプレミスのユニファイドメッセージングのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Lync Server 2013 での hosted Exchange UM 統合のサポート](lync-server-2013-support-for-hosted-exchange-um-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

