---
title: 'Lync Server 2013: Location-Based ルーティングの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48fee2b9db45519ff4773b4dfe47b33745e5fb10
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520964"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 での Location-Based ルーティングの概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

Location-Based ルーティングでは、国内および国際間の PSTN 通話のルーティングを変更する新しいルールのセットを導入して、有料のバイパスを防ぐことができます。 Location-Based ルーティングでは、これらのルールを特定の地域、特定のゲートウェイ、または特定のユーザーのセットに限定するための柔軟性が提供されます。

次のシナリオでは、Location-Based ルーティングによって適用される可能性のある主な種類の制限について説明します。

  - [出口呼び出し] – Location-Based ルーティングは、発信者が PSTN 有料電話のバイパスを阻止する pstn ゲートウェイからの出口に対して発信呼び出しを強制することができます。これにより、発信者とは別の地域にある PSTN ゲートウェイからの呼び出しを阻止することができます。

  - 受信呼び出し– Location-Based ルーティングは、着信呼び出しをルーティングする PSTN ゲートウェイが Lync ユーザーと同じ地域にない場合に、Lync エンドポイントを着信させないようにすることができます。

  - 不明地域– Location-Based ルーティングによって、不定の場所にあるユーザーとの間で送受信される PSTN 通話を制限します (つまり、リモートユーザーがインターネットから接続するか、または不明な地域に配置されます)。

  - 国際地域– Location-Based ルーティングは、ユーザーの場所にローカルなゲートウェイが見つからない場合に、国際 PSTN ゲートウェイを経由して発信通話のルーティングを強制します。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Location-Based ルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

