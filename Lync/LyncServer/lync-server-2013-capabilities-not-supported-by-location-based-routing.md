---
title: 'Lync Server 2013: 場所に基づくルーティングでサポートされていない機能'
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
ms.openlocfilehash: 967b5b7388ce60eafd46791c226bf1a3edbe0c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capabilities-not-supported-by-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 の場所に基づくルーティングでサポートされていない機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-03-12_

位置情報に基づくルーティングは、次の種類の操作には適用されません。 Lync エンドポイントがこれらの機能を使って PSTN エンドポイントを操作する場合、位置情報に基づくルーティングは強制されません。

  - 会議への PSTN ダイヤルイン

  - 応答グループによる PSTN 通話の着信および発信

  - 通話保留による PSTN 通話の保留または再開

  - アナウンス サービスへの PSTN 通話の着信

  - 着信 PSTN 通話のグループ通話ピックアップによる再開

次の一覧の操作の種類に位置ベースのルーティングルールを適用するには、会議で位置情報に基づくルーティングを有効にする必要があります。

  - 会議からの PSTN ダイヤルアウト

  - ピアツーピアの音声会話から PSTN エンドポイントを利用する会議へのエスカレーション

  - PSTN エンドポイントを利用する取次転送

会議で位置情報に基づくルーティングを有効にするには、「 [Lync Server 2013 の会議での位置情報に基づくルーティング](lync-server-2013-location-based-routing-for-conferencing.md)」を参照してください。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

