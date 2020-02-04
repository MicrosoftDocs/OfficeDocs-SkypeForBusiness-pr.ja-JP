---
title: 'Lync Server 2013: ブランチ サイトの展開'
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
ms.openlocfilehash: facfda5d1d7ce67ea08f71cbfb943792eeced7a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>Lync Server 2013 でのブランチ サイトの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

ブランチサイトユーザーは、ブランチサイトが関連付けられているセントラルサイトのサーバーから、Lync Server 2013 のほとんどの機能を利用できます。 各ブランチサイトは、1つのセントラルサイトと関連付けられます。 公衆交換電話網 (PSTN) との間で通話を発信するには、ブランチサイトに次のいずれかを含めることができます。

  - PSTN ゲートウェイと、おそらく Meditation Server

  - SIP トランク

  - 構内交換 (PBX) を使用する既存の音声インフラストラクチャ

  - Survivable Branch アプライアンス

  - Survivable ブランチサーバー

Survivable Branch Appliance または Survivable ブランチサーバーを使用しているブランチサイトでは、このようなソリューションを使用することなく、広域ネットワークまたはセントラルサイトの障害が発生した場合よりも高い弾力性があります。 たとえば、Survivable Branch Appliance または Survivable Branch Server が展開されているサイトでは、ブランチサイトをセントラルサイトに接続しているネットワークがダウンしている場合でも、ユーザーは PSTN 通話の発信と受信を行うことができます。 ブランチサイトの回復性を実現するもう1つの方法として、PSTN ゲートウェイまたは SIP トランクを使用して、ブランチサイトでのフルスケールの Lync Server 展開を利用することができます。

前提条件などの計画に関する考慮事項を含む、組織に適したブランチサイトの展開の詳細については、「 [Lync server 2013 での PSTN 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)」および「計画ドキュメントの[lync server 2013 でのブランチサイトのボイスの回復性の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 におけるブランチ サイトでの PSTN 接続の提供](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Lync Server 2013 を使用した存続可能ブランチ アプライアンスまたはサーバーの展開](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

