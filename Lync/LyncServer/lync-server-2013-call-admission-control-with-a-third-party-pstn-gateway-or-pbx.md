---
title: サードパーティの PSTN ゲートウェイまたは PBX での通話受付管理
description: サードパーティの PSTN ゲートウェイまたは PBX を使用した通話受付管理。
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
ms.openlocfilehash: aaab42992047ecedcc00ea1ecf5cf69023e51097
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545663"
---
# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>サードパーティの PSTN ゲートウェイまたは PBX での Lync Server 2013 での通話受付管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-20_

このトピックでは、仲介サーバーのゲートウェイインターフェイスと、サードパーティの公衆交換電話網 (PSTN) ゲートウェイまたは構内交換機 (PBX) との間のリンクに、通話受付管理 (CAC) を展開する方法の例について説明します。

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>ケース 1: 仲介サーバーと PSTN ゲートウェイ間の CAC

CAC は、仲介サーバーのゲートウェイインターフェイスから、サードパーティの PBX または PSTN ゲートウェイへの WAN リンク上に展開できます。

**ケース 1: 仲介サーバーと PSTN ゲートウェイ間の CAC**

![ケース 1: 仲介サーバーの PSTN ゲートウェイ間の CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "ケース 1: 仲介サーバーの PSTN ゲートウェイ間の CAC")

この例では、CAC が仲介サーバーと PSTN ゲートウェイの間で適用されます。 ネットワークサイト1の Lync クライアントユーザーが、ネットワークサイト2の PSTN ゲートウェイ経由で PSTN 通話を行う場合、メディアは WAN リンクを通過します。 そのため、PSTN セッションごとに2つの CAC チェックが実行されます。

  - Lync クライアントアプリケーションと仲介サーバーの間

  - 仲介サーバーと PSTN ゲートウェイの間

これは、ネットワークサイト1のクライアントへの PSTN 着信、およびネットワークサイト1のクライアントアプリケーションからの PSTN 通話の着信の両方で機能します。

<div>


> [!NOTE]
> PSTN ゲートウェイが属する IP サブネットが、構成され、ネットワークサイト2と関連付けられていることを確認します。<BR>仲介サーバーの両方のインターフェイスが属する IP サブネットが、構成され、ネットワークサイト1と関連付けられていることを確認します。<BR>詳細については、「 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013 でのネットワークサイトへのサブネットの関連付け</A>」を参照してください。



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>ケース 2: 仲介サーバーとメディア終端ポイントを含むサードパーティ製 PBX 間の CAC

この構成は、ケース1に似ています。 どちらの場合も、仲介サーバーは、WAN リンクの反対側でメディアを停止しているデバイスを認識します。また、メディア終端ポイント (MTP) を使用した PSTN ゲートウェイまたは PBX の IP アドレスは、仲介サーバーで次ホップとして構成されています。

**ケース 2: 仲介サーバーと MTP を含むサードパーティ製 PBX 間の CAC**

![ケース 2: 仲介サーバー PBX 間で MTP を使用した CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "ケース 2: 仲介サーバー PBX 間で MTP を使用した CAC")

この例では、CAC が仲介サーバーと PBX/MTP の間で適用されます。 ネットワークサイト1の Lync クライアントユーザーが、ネットワークサイト2にある PBX/MTP 経由で PSTN 通話を行う場合、メディアは WAN リンクを通過します。 そのため、PSTN セッションごとに、2つの CAC チェックが実行されます。

  - Lync クライアントアプリケーションと仲介サーバーの間

  - 仲介サーバーと PBX/MTP の間

これは、ネットワークサイト1のクライアントへの PSTN 着信、およびネットワークサイト1のクライアントからの PSTN 発信のどちらでも行われます。

<div>


> [!NOTE]
> MTP が属する IP サブネットが、構成済みで、ネットワークサイト2と関連付けられていることを確認します。<BR>仲介サーバーの両方のインターフェイスが属する IP サブネットが、構成され、ネットワークサイト1と関連付けられていることを確認します。<BR>詳細については、「 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013 でのネットワークサイトへのサブネットの関連付け</A>」を参照してください。



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>ケース 3: 仲介サーバーと、メディア終端ポイントを含まないサードパーティ製 PBX 間の CAC

ケース3は、最初の2つのケースとは少し異なります。 サードパーティの PBX に MTP がない場合、サードパーティの PBX への送信セッション要求に対して、仲介サーバーは、メディアが PBX 境界で終了する場所を認識しません。 この場合、メディアは、仲介サーバーとサードパーティ製エンドポイントデバイスとの間で直接転送されます。

**ケース 3: 仲介サーバーと MTP を使用しないサードパーティ製 PBX 間の CAC**

![ケース 3: 仲介サーバー PBX 間の CAC が非 MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "ケース 3: 仲介サーバー PBX 間の CAC が非 MTP")

この例では、ネットワークサイト1の Lync クライアントユーザーが PBX 経由でユーザーに電話を掛けた場合、仲介サーバーはプロキシレグ (Lync クライアントアプリケーションと仲介サーバーの間) でのみ CAC チェックを実行できます。 セッションが要求されている間は、仲介サーバーにはエンドポイントデバイスに関する情報が含まれていないため、呼び出しの確立前に、(仲介サーバーとサードパーティエンドポイントの間の) WAN リンク上で CAC チェックを実行することはできません。 しかし、セッションが確立されると、仲介サーバーはトランクで使用される帯域幅をアカウンティングする際に容易になります。

サードパーティ製エンドポイントから発信された通話の場合、そのエンドポイントデバイスに関する情報はセッション要求時に入手でき、仲介サーバーの両側で CAC チェックを実行できます。

<div>


> [!NOTE]
> エンドポイントデバイスが属する IP サブネットが、構成され、ネットワークサイト2と関連付けられていることを確認します。<BR>仲介サーバーの両方のインターフェイスが属する IP サブネットが、構成され、ネットワークサイト1と関連付けられていることを確認します。<BR>詳細については、「 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013 でのネットワークサイトへのサブネットの関連付け</A>」を参照してください。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

