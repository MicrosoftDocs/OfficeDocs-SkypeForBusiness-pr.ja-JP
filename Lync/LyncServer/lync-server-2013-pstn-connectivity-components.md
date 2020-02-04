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
ms.openlocfilehash: 63b5534b817477ea42dbefd5244c974fc70881f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Lync Server 2013 の PSTN 接続コンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

エンタープライズ レベルの VoIP ソリューションでは、サービスの品質 (QoS) を低下させずに公衆交換電話網 (PSTN) との通話の発信および着信を処理する必要があります。 また、通話の発信時および着信時に、基礎となるテクノロジをユーザーが意識しなくても済むようにする必要があります。 ユーザーから見れば、エンタープライズボイスインフラストラクチャと PSTN 間の通話は、別の SIP セッションと同じように見えます。

PSTN 接続を行うには、(PBX (直接 SIP リンク) を使用して、または PBX を使用せずに) SIP トランクまたは PSTN ゲートウェイを展開します。

<div>

## <a name="sip-trunking"></a>SIP トランキング

PSTN ゲートウェイを使用する代わりに、SIP トランキングを使用してエンタープライズ Voip ソリューションを PSTN に接続することもできます。 SIP トランキングを使用すると、次のようなシナリオが実現します。

  - 企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーが、E.164 準拠の番号で指定される市内通話や長距離通話を発信できます。この通話は、対応するサービス プロバイダーのサービスとして PSTN 上で終端されます。

  - PSTN サブスクライバーはだれでも、エンタープライズ ユーザーに関連付けられた Direct Inward Dialing (DID) 番号をダイヤルして、企業のファイアウォールの内側または外側にいるエンタープライズ ユーザーに連絡することができます。

この展開ソリューションを使用するには、SIP トランキング サービス プロバイダーが必要です。

</div>

<div>

## <a name="pstn-gateways"></a>PSTN ゲートウェイ

PSTN ゲートウェイは、エンタープライズボイスインフラストラクチャと PSTN または PBX 間のシグナリングおよびメディアを変換するサードパーティ製のデバイスです。 PSTN ゲートウェイは、仲介サーバーと連携して、エンタープライズボイスクライアントに PSTN または PBX 通話を提供します。 また、仲介サーバーは、PSTN または PBX にルーティングするために、エンタープライズボイスクライアントから PSTN ゲートウェイへの通話を提供します。 Microsoft と連携して Lync Server で動作するデバイスを提供しているパートナーのリストについては、Microsoft ユニファイ[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)ドコミュニケーションパートナーの web サイトを参照してください。

</div>

<div>

## <a name="private-branch-exchanges"></a>構内交換機

プライベートブランチ exchange (PBX) を使用する既存の音声インフラストラクチャを使用している場合は、お使いの PBX で Lync Server Enterprise Voice を使用できます。

サポートされているエンタープライズ Voip 統合シナリオは、次のとおりです。

  - 仲介サーバーでメディアバイパスをサポートする IP PBX。

  - スタンドアロンの PSTN ゲートウェイが必要な IP-PBX。

  - 時分割多重 (TDM) PBX とスタンドアロンの PSTN ゲートウェイ。

<div>


> [!NOTE]  
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。 マイクロソフトでは、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。 メディアのバイパスは、統合された通信のオープンな相互運用性プログラム– Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>の製品とバージョンでのみサポートされます。



</div>

エンタープライズ Voip ソリューションを提供しているパートナーの詳細については、Microsoft ユニファイ[http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)ドコミュニケーションパートナーの web サイトを参照してください。

PSTN ゲートウェイなど、エンタープライズボイスハードウェアソリューションを提供しているパートナーの詳細については、Microsoft [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)ユニファイドコミュニケーションパートナーの web サイトを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

