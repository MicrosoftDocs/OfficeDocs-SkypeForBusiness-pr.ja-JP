---
title: 'Lync Server 2013: PSTN 接続コンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 973962c7f52474f65766e6772647359c8089daee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Lync Server 2013 の PSTN 接続コンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。また、通話の発信時および着信時に、基礎となるテクノロジをユーザーが意識しなくても済むようにする必要があります。ユーザーからは、エンタープライズ VoIP インフラストラクチャと PSTN 間の通話は、別の SIP セッションのように見えます。

PSTN 接続の場合は、SIP トランクまたは PSTN ゲートウェイを展開できます (PBX (直接 SIP リンクとも呼ばれる) か、PBX を使用しない)。

<div>

## <a name="sip-trunking"></a>SIP トランキング

PSTN ゲートウェイを使用する代わりに、SIP トランキングを使用してエンタープライズ VoIP ソリューションを PSTN に接続することもできます。 SIP トランキングを使用すると、次のようなシナリオが実現します。

  - 企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーが、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。

  - PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。

この展開ソリューションを使用するには、SIP トランキング サービス プロバイダーが必要です。

</div>

<div>

## <a name="pstn-gateways"></a>PSTN ゲートウェイ

PSTN ゲートウェイは、エンタープライズ VoIP インフラストラクチャと PSTN または PBX の間の信号とメディアを変換する、サードパーティのデバイスです。 PSTN ゲートウェイは、仲介サーバーと連携して、エンタープライズ VoIP クライアントへの PSTN または PBX の通話を処理します。 また、仲介サーバーは、PSTN または PBX にルーティングするために、エンタープライズ VoIP クライアントから PSTN ゲートウェイへの通話も処理します。 Microsoft と連携して Lync Server と連携するデバイスを提供するパートナーの一覧については、Microsoft ユニファイドコミュニケーション[https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836)パートナーの web サイト () を参照してください。

</div>

<div>

## <a name="private-branch-exchanges"></a>構内交換機

構内交換業者 (PBX) を使用する既存の音声インフラストラクチャがある場合は、その PBX を Lync Server エンタープライズ Voip で使用できます。

サポートされているエンタープライズ VoIP と PBX の統合シナリオは、次のとおりです。

  - メディア バイパスをサポートしている IP-PBX と仲介サーバー。

  - スタンドアロンの PSTN ゲートウェイが必要な IP-PBX。

  - 時分割多重 (TDM) PBX とスタンドアロンの PSTN ゲートウェイ。

<div>


> [!NOTE]  
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。 Microsoft は、認定パートナーで PSTN ゲートウェイと sbc のセットをテストしており、Cisco IP-PBX でいくつかのテストを行いました。 メディアバイパスがサポートされるのは、統合コミュニケーションのオープン相互運用性プログラム– Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>の製品およびバージョンのみです。



</div>

エンタープライズ Voip ソリューションを提供しているパートナーの詳細については、Microsoft ユニファイ[https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836)ドコミュニケーションパートナーの web サイト () を参照してください。

PSTN ゲートウェイを含むエンタープライズ Voip ハードウェアソリューションを提供しているパートナーの詳細については、「 [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836)Microsoft 統合コミュニケーションパートナーの web サイト」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

