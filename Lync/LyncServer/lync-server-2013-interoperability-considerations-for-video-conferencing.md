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
ms.openlocfilehash: b8cdfa88cf6d6f58478ff3c6b44210545e24a765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Lync Server 2013 でのビデオ会議の相互運用性に関する考慮事項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-02_

このセクションでは、従来のクライアントと Lync Server 2013 プールの間、または Lync Server 2013 クライアントと従来のプールの間で相互運用性がある場合に、移行の共存フェーズでのユーザーエクスペリエンスについて説明します。

<div>

## <a name="lync-server-2013-pools"></a>Lync Server 2013 プール

Lync Server 2013 プールでレガシクライアントが使用されている場合、ユーザーには次の動作が発生します。

  - 2パーティーの通話では、ビデオ解像度は従来のプールと同じです。

  - マルチパーティ会議の場合、ビデオの解像度とビデオ会議の機能は、従来のプールと同じです。 ギャラリービューと高解像度は使用できません。

</div>

<div>

## <a name="legacy-pools"></a>従来のプール

従来のプールで Lync Server 2013 クライアントが使用されている場合、ユーザーには次の動作が発生します。

  - 2パーティの通話の場合、Lync Server 2013 クライアントでは次のような新機能を使用できます。
    
      - 両方の参加者が Lync Server 2013 クライアントを使用している場合は、"264. 264" を使うことができます。
    
      - 従来のサーバーは、インバンドプロビジョニングでこの情報を送信しないため、Lync Server 2013 クライアントは TotalReceiveVideoBitRateKb の既定値を使います。

  - マルチパーティ会議の場合、ビデオの解像度とビデオ会議の機能は、従来のプールのレガシクライアントでの経験と同じです。

<div>


> [!NOTE]  
> 従来のサーバーが Lync Server 2013 クライアントをホストしている場合は、プールのすべてのユーザーが低解像度のビデオを受信できるだけで、高解像度のビデオを送信できるように、ビデオ会議の帯域幅を構成することができます。 この例としては、メディア構成の MaxVideoRateAllowed が250K に設定されていて、VideoBitRateKb が会議ポリシーで 2000 kbps に設定されている場合です。 この状況では、プールのユーザーに対して高解像度を実現することはできません。<BR>MaxVideoRateAllowed は Lync Server 2013 クライアントでは使われなくなったため、Lync Server 2013 クライアントから高解像度ビデオを要求することはできません。 代わりに、プールのすべてのユーザーに対して、プールのすべてのユーザーに対して、VideoBitRateKb を MaxVideoRateAllowed (つまり、250 kbps に設定されているか、VGA が 600 kbps に設定されているか、HD が 1500 kbps に設定されている) と同じ値に設定します。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

