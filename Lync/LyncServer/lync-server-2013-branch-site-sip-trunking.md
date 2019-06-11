---
title: 'Lync Server 2013: ブランチサイト SIP トランク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 955e920138021941db0e75832d56d06499738edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Branch site SIP trunking in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

場合によっては、選択したブランチサイトに配布 SIP トランキングを実装する必要があります。 ブランチサイトに SIP トランクが必要かどうかを判断するには、「 [Lync Server 2013 で sip トランクを実装する方法](lync-server-2013-how-do-i-implement-sip-trunking.md)」の情報を確認します。

ブランチサイトでの SIP trunks の展開についてサポートされているトポロジーオプションの詳細については、「 [Lync Server 2013 でのブランチサイトの回復性ソリューション](lync-server-2013-branch-site-resiliency-solutions.md)」を参照してください。

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>ブランチ サイト SIP トランク要件例の分析

ブランチサイト SIP トランクの展開を決定する際には、サイト固有のコスト分析を実行する必要があります。 たとえば、ニューヨークのレドモンド、ワシントン、支店にセントラルサイトがある企業では、ニューヨークサイトの SIP トランクをローカルサービスプロバイダに実装するかどうかを判断する分析を行う必要があります。

ニューヨークでの分散型 SIP トランクの費用対効果が高いかどうかを判断するには、SIP トランクを使用する Direct Inward Dialing (DID) 番号を識別し、レドモンド (425) 以外の地域にニューヨークからかける電話の回数を分析します。 セントラルサイトでブランチサイトの終了ができました。 たとえば、Redmond のセントラルサイトでは、ニューヨーク支社のサイトの番号をホストできます。 分散 SIP トランクの実装のコストがこれらの通話のコストよりも少ない場合は、ニューヨーク支店のサイトで SIP トランクを実装することを検討してください。

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>その他のブランチ サイト SIP トランク要件

ゲートウェイの代わりに SIP トランクを展開するには、各オプションの PSTN (公衆交換電話網) の長距離電話料金の差に基づいて選択することができます。 ブランチサイト SIP トランクを展開する場合は、回復性と帯域幅の要件を特定する必要もあります。 ブランチサイトとセントラルサイト間のリンクが回復可能であり、十分な帯域幅がある場合は、SIP トランクまたはゲートウェイを展開できます。 ブランチサイトに Survivable Branch Appliance を展開する必要はありません。 ブランチサイトとセントラルサイト間のリンクが復元できない場合は、Survivable Branch Appliance を展開するか、ゲートウェイまたは SIP トランクのいずれかでブランチサイトに Survivable ブランチサーバーを展開してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

