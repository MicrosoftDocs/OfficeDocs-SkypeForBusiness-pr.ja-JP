---
title: 'Lync Server 2013: 拡張9-1-1 の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 642117d89936741cf2610b4d76e1a20125336e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537114"
---
# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>Lync Server 2013 での拡張9-1-1 の構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-24_

拡張 9-1-1 (E9-1-1) は、発信者の電話番号を正式な住所または主要道路住所に関連付ける緊急通知機能です。緊急応答機関 (PSAP) はこの情報を使用して、支援を必要とする発信者に緊急サービスをすぐに派遣できます。

E9-1-1 をサポートするには、Lync Server 2013 が、場所をクライアントに正しく関連付け、緊急通話を最も近い PSAP にルーティングするためにこの情報が使用されるようにする必要があります。

E9-1-1 展開の計画の詳細については、「 [planning for エマージェンシーサービス (E9-1-1) (Lync Server 2013)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)」を参照してください。

<div>


> [!IMPORTANT]  
> Lync Server 2013 は、米国内の E9-1-1 のみをサポートします。 E9-1-1 を展開するには、認定 E9-1-1 サービス プロバイダーへの SIP 接続を構成するか、公衆交換電話網 (PSTN) ベースの E9-1-1 サービス プロバイダーへの緊急位置識別番号 (ELIN) ゲートウェイを展開する必要があります。 詳細については、「 <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1)」および「Lync server 2013 の仲介サーバー</A>」を参照してください。 トランク接続の構成の詳細については、「 <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Lync Server 2013 でメディアバイパスを使用してトランクを構成</A>する」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での E9-1-1 ボイスルートの構成](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Lync Server 2013 での場所のポリシーの作成](lync-server-2013-create-location-policies.md)

  - [Lync Server 2013 での E9-1-1 のサイト情報の構成](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Lync Server 2013 で場所データベースを構成する](lync-server-2013-configure-the-location-database.md)

  - [Lync Server 2013 の高度な E9-1-1 機能の構成](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

