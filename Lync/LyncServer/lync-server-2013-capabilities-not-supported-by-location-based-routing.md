---
title: 'Lync Server 2013: Location-Based ルーティングでサポートされていない機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capabilities not supported by Location-Based Routing
ms:assetid: c3d54953-a7d6-4465-a6c3-ae411b2d8ea9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994071(v=OCS.15)
ms:contentKeyID: 51803982
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40a7d32c0448abfe3552fdfe657b9c6bec960a08
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512864"
---
# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 での Location-Based ルーティングでサポートされていない機能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-03-12_

Location-Based ルーティングは、次の種類の相互作用には適用されません。 Lync エンドポイントがこれらの機能を使用して PSTN エンドポイントと対話する場合、Location-Based ルーティングは適用されません。

  - 電話会議への PSTN ダイヤルイン

  - 応答グループを介した着信および発信 PSTN 通話

  - コールパークによる PSTN 通話のコールパークまたは取得

  - アナウンスサービスへの PSTN 通話の着信

  - グループ通話ピックアップで取得した PSTN 通話の着信

次の一覧の操作の種類に Location-Based ルーティングルールを適用するには、電話会議用に Location-Based ルーティングを有効にする必要があります。

  - 会議からの PSTN ダイヤルアウト

  - ピアツーピア音声会話から PSTN エンドポイントを含む会議へのエスカレーション

  - PSTN エンドポイントを含む提案転送

会議の Location-Based ルーティングを有効にするには、「 [Lync Server 2013 の会議の場所に基づくルーティング](lync-server-2013-location-based-routing-for-conferencing.md)」を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Location-Based ルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

