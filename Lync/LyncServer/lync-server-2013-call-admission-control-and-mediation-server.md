---
title: 'Lync Server 2013: 通話受付管理と仲介サーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 787e312bcdee289050f2147912e87ef542433db4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013 の通話受付管理と仲介サーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

通話受付制御 (CAC) は、最初に Lync Server 2010 で導入されたものであり、使用可能な帯域幅に基づいてリアルタイムのセッションの確立を管理して、混雑したネットワーク上のユーザーに対して低品質のエクスペリエンス (QoE) を防ぐことができます。 この機能をサポートするために、企業のボイスインフラストラクチャとゲートウェイまたは SIP トランクプロバイダーの間でシグナリングとメディアの翻訳を提供する仲介サーバーが、Lync 上の2つの操作の帯域幅管理を担当しています。サーバー側とゲートウェイ側。 通話受付管理では、通話の終端エンティティが帯域幅の予約を処理します。 仲介サーバーがゲートウェイ側でやり取りするゲートウェイピア (PSTN ゲートウェイ、IP PBX、SBC) では、Lync Server 2013 の通話受付制御はサポートされていません。 そのため、仲介サーバーは、ゲートウェイピアの代わりに帯域幅の操作を処理する必要があります。 可能な限り、仲介サーバーは事前に帯域幅を予約します。 予約できない場合 (たとえば、ゲートウェイ側の最終的なメディア エンドポイントのローカリティが、ゲートウェイ ピアへの発信通話に対して不明な場合)、帯域幅は通話が開始されたときに予約されます。 この動作によって帯域幅のオーバーサブスクリプションが生じる可能性がありますが、これが誤着信を防ぐ唯一の方法です。

メディア バイパスと帯域幅の予約は同時に使用することはできません。 通話にメディアバイパスが採用されている場合、通話受付制御はその通話に対して実行されません。 この場合、その通話で、制限された帯域幅を使用するリンクがかかわっていないことが前提となります。 仲介サーバーに関連する特定の通話に通話受付制御が使われている場合、その呼び出しでメディアのバイパスを使用することはできません。

メディアバイパスまたは通話受付制御の詳細については、「 [Lync server 2013 でのメディアのバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」または「計画ドキュメントの[lync server 2013 での通話受付制御の計画](lync-server-2013-planning-for-call-admission-control.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

