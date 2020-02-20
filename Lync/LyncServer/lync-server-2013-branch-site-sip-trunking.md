---
title: 'Lync Server 2013: ブランチサイトの SIP トランキング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b0e24a0260e6be0bea8d23158f07ffcffcb53cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 でのブランチサイト SIP トランキング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

場合によっては、選択したブランチサイトでの分散 SIP トランキングの実装が必要になることがあります。 ブランチサイトに SIP トランクが必要かどうかを判断するには、「 [Lync Server 2013 での sip トランキングの実装方法](lync-server-2013-how-do-i-implement-sip-trunking.md)」の情報を参照してください。

ブランチサイトでの SIP トランクの展開でサポートされるトポロジオプションの詳細については、「 [Lync Server 2013 の「ブランチサイトの復元ソリューション](lync-server-2013-branch-site-resiliency-solutions.md)」を参照してください。

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>ブランチ サイト SIP トランク要件例の分析

ブランチサイトの SIP トランクを展開することを決定した場合は、サイト固有のコスト分析を実行する必要があります。 たとえば、Redmond、ワシントン、ニューヨークのブランチサイトに中央サイトがあるエンタープライズは、ニューヨークサイトからローカルサービスプロバイダへの SIP トランクを実装するかどうかを判断する分析を行う必要があります。

ニューヨークでの分散型 SIP トランクの費用対効果が高いかどうかを判断するには、SIP トランクを使用する Direct Inward Dialing (DID) 番号を識別し、レドモンド (425) 以外の地域にニューヨークからかける電話の回数を分析します。 中央サイトでブランチサイトの終了を完了しました。 たとえば、Redmond の中央サイトは、ニューヨークのブランチサイト用の電話番号をホストできます。 分散 SIP トランクを実装するコストがこれらの呼び出しのコストを下回っている場合は、ニューヨークブランチサイトで SIP トランクを実装することを検討してください。

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>その他のブランチ サイト SIP トランク要件

ゲートウェイの代わりに SIP トランクを展開する方法の選択は、各オプションの公衆交換電話網 (PSTN) 長距離通話料金の違いに基づいています。 ブランチサイトの SIP トランクを展開する場合は、復元および帯域幅の要件も決定する必要があります。 ブランチサイトと中央サイトの間のリンクが復元性があり、十分な帯域幅がある場合は、SIP トランクまたはゲートウェイを展開できます。 ブランチサイトで存続可能ブランチアプライアンスを展開する必要はありません。 ブランチサイトと中央サイトの間のリンクが復元できない場合は、存続可能 Branch Appliance を展開するか、ゲートウェイまたは SIP トランクを使用してブランチサイトに存続可能ブランチサーバーを展開します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

