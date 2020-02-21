---
title: 'Lync Server 2013: 場所に基づくルーティングに関する技術的な考慮事項'
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
ms.openlocfilehash: 89180087909b71bc9f53f24ee02bbc077d459a17
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 での場所に基づくルーティングに関する技術的考慮事項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

場所に基づくルーティングを計画するときは、次のシナリオに対する影響を考慮する必要があります。

<div>

## <a name="disaster-recovery"></a>障害復旧

プライマリプールからバックアッププールへのフェールオーバーに加えて、プライマリプールへの通常の操作の復元時には、場所に基づくルーティングは障害発生時および回復手順中に常に適用されたままになります。

</div>

<div>

## <a name="survivable-branch-appliance"></a>存続可能ブランチ アプライアンス

場所に基づくルーティングを構成すると、存続可能ブランチアプライアンスに関連付けられているゲートウェイの展開計画に影響します。 SBA に関連付けられているゲートウェイは、存続可能ブランチアプライアンスと同じネットワークサイトに配置する必要があります。そうしないと、存続可能 Branch アプライアンスに所属するユーザーは、場所に基づくルーティングが構成されている場合に、送信呼び出しを行うことができなくなります。 存続可能ブランチアプライアンスと中央サイトとの間の WAN 接続がダウンすると、場所に基づくルーティング制限が適用されたままになります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

