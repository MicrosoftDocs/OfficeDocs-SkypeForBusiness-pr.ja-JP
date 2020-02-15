---
title: 'Lync Server 2013: 通話受付管理と仲介サーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16158c8920279d95cfe3deed37f789eaedccc8b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 での通話受付管理と仲介サーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

最初に Lync Server 2010 で導入された通話受付管理 (CAC) では、使用可能な帯域幅に基づいてリアルタイムセッションの確立を管理し、混雑したネットワーク上のユーザーに対する QoE (Quality of Experience) の低下を防ぎます。 この機能をサポートするために、企業の音声インフラストラクチャとゲートウェイまたは SIP トランキングプロバイダー間でシグナリングとメディア変換を提供する仲介サーバーは、Lync での2つの相互作用について帯域幅管理を担当します。サーバー側とゲートウェイ側。 通話受付管理では、通話の終端エンティティが帯域幅の予約を処理します。 仲介サーバーがゲートウェイ側で対話するゲートウェイピア (PSTN ゲートウェイ、IP-PBX、SBC) は、Lync Server 2013 通話受付管理をサポートしていません。 そのため、仲介サーバーは、ゲートウェイピアの代わりに帯域幅の相互作用を処理する必要があります。 可能な限り、仲介サーバーは事前に帯域幅を予約します。 予約できない場合 (たとえば、ゲートウェイ側の最終的なメディア エンドポイントのローカリティが、ゲートウェイ ピアへの発信通話に対して不明な場合)、帯域幅は通話が開始されたときに予約されます。 この動作によって帯域幅のオーバーサブスクリプションが生じる可能性がありますが、これが誤着信を防ぐ唯一の方法です。

メディア バイパスと帯域幅の予約は同時に使用することはできません。 メディア バイパスを通話で使用する場合、その通話で通話受付管理を実行することはできません。 この場合、その通話で、制限された帯域幅を使用するリンクが関わっていないことが前提となります。 仲介サーバーを含む特定の呼び出しに対して通話受付管理を使用する場合、その呼び出しでメディアバイパスを使用することはできません。

メディアバイパスまたは通話受付管理の詳細については、「計画」のドキュメントの「 [lync server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」または「 [lync server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

