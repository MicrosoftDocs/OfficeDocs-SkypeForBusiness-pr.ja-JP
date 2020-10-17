---
title: 'Lync Server 2013: ブランチサイトの展開'
description: 'Lync Server 2013: ブランチサイトの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d653e3f06de832693d97bfb229f122a67c28640e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552643"
---
# <a name="deploying-branch-sites-in-lync-server-2013"></a>Lync Server 2013 でのブランチサイトの展開

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

ブランチサイトユーザーは、ブランチサイトが関連付けられている中央サイトのサーバーから Lync Server 2013 の機能の大部分を取得します。 各ブランチ サイトは、1 つだけのセントラル サイトに関連付けられています。 公衆交換電話網 (PSTN) へ、または公衆交換電話網 (PSTN) からの通話を提供するため、ブランチ サイトは次のいずれかを含みます。

  - PSTN ゲートウェイおよび場合によっては仲介サーバー

  - SIP トランク

  - 構内交換機 (PBX) と既存の音声インフラストラクチャ

  - 存続可能ブランチアプライアンス

  - 存続可能ブランチサーバー

存続可能 Branch Appliance または存続可能ブランチサーバーを使用するブランチサイトでは、これらのソリューションのいずれも含まれていないブランチサイトと比べて、広域ネットワークまたは中央サイトの障害が発生する時間での復元が向上します。 たとえば、存続可能 Branch Appliance または存続可能 Branch Server が展開されているサイトでは、ブランチサイトを中央サイトに接続しているネットワークがダウンしている場合でも、ユーザーは PSTN 通話を発信および受信できます。 ブランチサイトの復元を実現するもう1つの方法は、ブランチサイトでのフルスケールの Lync Server 展開を使用した PSTN ゲートウェイまたは SIP トランクの使用です。

前提条件やその他の計画に関する考慮事項など、組織に適したブランチサイト展開の詳細については、「計画」のドキュメントの「lync server [2013 での PSTN 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md) 」および「 [lync server 2013 でのブランチサイト音声の復元の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 」を参照してください。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のブランチサイトでの PSTN 接続の提供](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Lync Server 2013 を使用した存続可能ブランチアプライアンスまたはサーバーの展開](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

