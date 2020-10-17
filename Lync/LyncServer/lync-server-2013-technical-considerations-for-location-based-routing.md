---
title: 'Lync Server 2013: Location-Based ルーティングに関する技術的な考慮事項'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80364f35ffaf361353815988bcae12f29bca019c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536184"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 での Location-Based ルーティングに関する技術的考慮事項

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

Location-Based ルーティングを計画するときは、次のシナリオに対する影響を考慮する必要があります。

<div>

## <a name="disaster-recovery"></a>障害回復

プライマリプールからバックアッププールへのフェールオーバーに加えて、プライマリプールへの通常の操作の復元時には、Location-Based ルーティングは障害発生時および回復手順中に常に適用されたままになります。

</div>

<div>

## <a name="survivable-branch-appliance"></a>存続可能ブランチ アプライアンス

Location-Based ルーティングを構成すると、存続可能 Branch アプライアンスに関連付けられているゲートウェイを展開する場所の計画に影響します。 SBA に関連付けられているゲートウェイは、存続可能ブランチアプライアンスと同じネットワークサイトに配置する必要があります。そうしないと、存続可能ブランチアプライアンスに所属するユーザーは Location-Based ルーティングが構成されている場合に、送信呼び出しをすることはできません。 存続可能ブランチアプライアンスと中央サイトとの間の WAN 接続がダウンすると、Location-Based ルーティング制限が適用されたままになります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Location-Based ルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

