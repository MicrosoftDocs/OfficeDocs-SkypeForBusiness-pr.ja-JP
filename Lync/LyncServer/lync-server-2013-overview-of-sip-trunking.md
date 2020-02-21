---
title: 'Lync Server 2013: SIP トランキングの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e71a1f02fda14c2bcbb54aaec5e12307421090e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 の SIP トランキングの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

SIP トランキングを展開することは、組織の通信方式を簡素化し、リアルタイム通信への最新の機能強化に備えるための大きなステップとなります。SIP トランキングの主な利点の 1 つは、一般に各ブランチ サイトからの個別のトランクを必要とする従来の時分割多重 (TDM) トランキングと異なり、組織の接続をセントラル サイトの公衆交換電話網 (PSTN) に集約できることです。

<div>

## <a name="sip-trunking-in-lync-server"></a>Lync Server の SIP トランキング

Lync Server 2013 SIP トランキング機能により、次のことが可能になります。

  - エンタープライズ ユーザーは企業のファイアウォールの内側と外側のどちらにいても、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。

  - PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。

</div>

<div>

## <a name="cost-savings"></a>費用の削減

SIP トランキングに関連する費用の削減はかなりのものです。

  - 長距離通話は、SIP トランクを介した場合よりもかなり安くすみます。

  - 管理コストを削減でき、展開を簡素化することが可能です。

  - SIP トランクを大幅な低コストで直接 ITSP に接続した場合、ベーシック レート インターフェイス (BRI) およびプライマリ レート インターフェイス (PRI) の料金をなくすことができます。TDM トランキングでは、サービス プロバイダーは分単位で通話に課金します。SIP トランキングの料金は帯域幅の使用量に基づくので、より少ない、より経済的な単位で購入できます (実際の料金は、使用する ITSP のサービス モデルによって異なります)。

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP トランキング対 PSTN ゲートウェイまたは IP-PBX のホスト

SIP トランクは直接サービス プロバイダーに接続されるため、PTSN ゲートウェイおよび管理費用を削除でき、接続が簡素化されます。SIP トランクを利用することでメンテナンス費用および管理費用を減らすことができ、相当な費用削減となります。

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>VoIP サービスの拡張

多くの場合、音声機能が SIP トランキングを展開する主な動機ではありますが、音声サポートは最初のステップにすぎません。 SIP トランキングを使用すると、VoIP 機能を拡張し、Lync Server 2013 を有効にして、より豊富なサービスセットを提供できます。 次に例を示します。

  - Lync Server 2013 を実行していないデバイスの拡張プレゼンス検出を使用すると、携帯電話との統合が向上し、ユーザーが携帯電話で通話しているときに表示されるようになります。

  - E9-1-1 緊急通話の場合、911 番の電話に出た当局者が、かかってきた電話番号から、その電話をかけた人物の場所を特定することが可能です。

<div>


> [!NOTE]  
> 組織で利用できる、ITSP がサポートするサービスの内容については、ご利用の ITSP に問い合わせてください。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

