---
title: 'Lync Server 2013: ビデオ会議の相互運用性に関する考慮事項'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6157b9dc8867b2f458eafb6f0343fd43a19af537
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Lync Server 2013 でのビデオ会議の相互運用性に関する考慮事項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

このセクションでは、レガシクライアントと Lync Server 2013 プールまたは Lync Server 2013 クライアントと従来のプールとの間に相互運用性がある場合に、移行の共存フェーズのユーザー環境を説明します。

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013 プール

従来のクライアントが Lync Server 2013 プールで使用されている場合、ユーザーには次のような動作が生じます。

  - 2 者間通話では、ビデオ解像度はレガシ プールと同じです。

  - マルチパーティの電話会議、ビデオ解像度、およびビデオ会議の機能は、レガシ プールと同じです。ギャラリー ビューと高解像度は使用できません。

</div>

<div>

## <a name="legacy-pools"></a>レガシ プール

従来のプールで Lync Server 2013 クライアントが使用されている場合、ユーザーには次のような動作が生じます。

  - 2者間通話では、Lync Server 2013 クライアントは次のように新しい機能を使用できます。
    
      - .H は、両方の参加者が Lync Server 2013 クライアントを使用している場合に使用できます。
    
      - 従来のサーバーはインバンドプロビジョニングでこの情報を送信しないため、Lync Server 2013 クライアントは TotalReceiveVideoBitRateKb の既定値を使用します。

  - マルチパーティの電話会議、ビデオ解像度、およびビデオ会議の機能は、レガシ プール内のレガシ クライアントでのユーザー エクスペリエンスと同じです。

<div>


> [!NOTE]  
> 従来のサーバーが Lync Server 2013 クライアントをホストしている場合は、ビデオ会議の帯域幅を構成して、プール上のすべてのユーザーが低解像度のビデオを受信し、高解像度のビデオを送信できるようにすることができます。 この例は、メディア構成で MaxVideoRateAllowed が CIF-250K に設定され、会議ポリシーで VideoBitRateKb が 2000 kbps に設定された場合です。 この設定では、プール上のユーザーは高解像度を送信できないことになります。<BR>MaxVideoRateAllowed は Lync Server 2013 クライアントでは使用されなくなったため、Lync Server 2013 クライアントが高解像度のビデオを要求することを防ぐことはできません。 その代わりに、すべてのプール上のユーザーの会議ポリシーで VideoBitRateKb を MaxVideoRateAllowed と同じ値に設定します (つまり、CIF が 250 kbps、VGA が 600 kbps、HD が 1500 kbps に設定されます)。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

