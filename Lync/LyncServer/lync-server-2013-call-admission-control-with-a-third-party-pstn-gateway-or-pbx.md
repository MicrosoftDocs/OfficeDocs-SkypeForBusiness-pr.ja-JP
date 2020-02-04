---
title: サードパーティの PSTN ゲートウェイまたは PBX での通話受付管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09aae207844fed12c840918a533fb181ca36634e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>サードパーティの PSTN ゲートウェイまたは PBX での Lync Server 2013 における通話受付管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-20_

このトピックでは、仲介サーバーのゲートウェイ インターフェイス、およびサードパーティの公衆交換電話網 (PSTN) ゲートウェイまたは構内交換機 (PBX) の間のリンクに、どのように通話受付管理 (CAC) を配置することができるのかという例を説明します。

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>ケース 1: 仲介サーバーおよび PSTN ゲートウェイ間の CAC

CAC は、仲介サーバーのゲートウェイ インターフェイスから、サードパーティの PBX または PSTN ゲートウェイへの WAN リンクに展開させることができます。

**ケース 1: 仲介サーバーおよび PSTN ゲートウェイ間の CAC**

![ケース 1: 仲介サーバーと PSTN ゲートウェイ間の CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "ケース 1: 仲介サーバーと PSTN ゲートウェイ間の CAC")

この例では、仲介サーバーと PSTN ゲートウェイの間で CAC が適用されています。 ネットワークサイト1の Lync クライアントユーザーが、ネットワークサイト2の PSTN ゲートウェイ経由で PSTN 通話を発信した場合、メディアは WAN リンクを通じて流れることになります。 そのため、PSTN セッションごとに 2 度の CAC チェックが行われます。

  - Lync クライアントアプリケーションと仲介サーバーの間

  - 仲介サーバーと PSTN ゲートウェイの間

これは、ネットワーク サイト 1 のクライアントへの PSTN 着信、およびネットワーク サイト 1 のクライアント アプリケーションからの PSTN 発信のどちらでも行われます。

<div>


> [!NOTE]
> PSTN ゲートウェイが属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。<BR>仲介サーバーの両方のインターフェイスが所属する IP サブネットが構成されていて、ネットワークサイト1に関連付けられていることを確認します。<BR>詳細については、「 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013 でサブネットとネットワークサイトを関連付ける</A>」を参照してください。



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>ケース 2: 仲介サーバーとサードパーティ PBX との間の CAC でメディア終了ポイントが使用される

この構成はケース 1 に類似したものです。 どちらの場合も、仲介サーバーは、WAN リンクの反対側でメディアを終了させるデバイスを認識します。また、PSTN ゲートウェイまたは PBX の IP アドレスは、仲介サーバー上で次ホップとして構成されています。

**ケース 2: 仲介サーバーおよび MTP を含むサードパーティ製 PBX 間の CAC**

![ケース 2: 仲介サーバーと PBX (MTP が含まれる) 間の CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "ケース 2: 仲介サーバーと PBX (MTP が含まれる) 間の CAC")

この例では、仲介サーバーと PBX/MTP の間で CAC が適用されています。 ネットワークサイト1の Lync クライアントユーザーが、ネットワークサイト2にある PBX/MTP 経由で PSTN 通話を発信した場合、メディアは WAN リンクを通じて流れることになります。 そのため、それぞれの PSTN セッションごとに 2 度の CAC チェックが行われます。

  - Lync クライアントアプリケーションと仲介サーバーの間

  - 仲介サーバーと PBX/MTP の間

これは、ネットワーク サイト 1 のクライアントへの PSTN 着信、およびネットワーク サイト 1 のクライアントからの PSTN 発信のどちらでも行われます。

<div>


> [!NOTE]
> MTP が属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。<BR>仲介サーバーの両方のインターフェイスが所属する IP サブネットが構成されていて、ネットワークサイト1に関連付けられていることを確認します。<BR>詳細については、「 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013 でサブネットとネットワークサイトを関連付ける</A>」を参照してください。



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>ケース 3: メディア終了ポイントのない仲介サーバーとサードパーティ PBX 間の CAC

ケース 3 は、最初の 2 つのケースとは少し異なります。 サードパーティ PBX 上に MTP がない場合、サードパーティ PBX への送信セッション要求については、仲介サーバーが PBX 境界でメディアを終了させる場所を把握していません。 この場合、メディアは、仲介サーバーとサードパーティエンドポイントデバイスの間で直接フローします。

**ケース 3: 仲介サーバーおよび MTP が含まれないサードパーティ製 PBX 間の CAC**

![ケース 3: 仲介サーバーと PBX (MTP が含まれない) 間の CAC](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "ケース 3: 仲介サーバーと PBX (MTP が含まれない) 間の CAC")

この例では、ネットワークサイト1の Lync クライアントユーザーが PBX を通じてユーザーに通話を発信した場合、仲介サーバーはプロキシレグ上 (Lync クライアントアプリケーションと仲介サーバーの間) でのみ CAC チェックを実行できます。 仲介サーバーには、セッションが要求されている間、エンドポイントデバイスに関する情報が含まれていないため、発信する前に、(仲介サーバーとサードパーティのエンドポイント間の) WAN リンクで CAC チェックを実行することはできません。 ただし、セッションが確立されると、仲介サーバーによって、トランクで使用される帯域幅のアカウンティングが容易になります。

サードパーティのエンドポイントから発信された通話の場合、そのエンドポイントデバイスに関する情報はセッション要求の時点で利用できます。 CAC のチェックは、仲介サーバーの両方の側で実行できます。

<div>


> [!NOTE]
> エンドポイント デバイスが属する IP サブネットが、確実に構成され、ネットワーク サイト 2 と関連付けられているようにしてください。<BR>仲介サーバーの両方のインターフェイスが所属する IP サブネットが構成されていて、ネットワークサイト1に関連付けられていることを確認します。<BR>詳細については、「 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013 でサブネットとネットワークサイトを関連付ける</A>」を参照してください。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

