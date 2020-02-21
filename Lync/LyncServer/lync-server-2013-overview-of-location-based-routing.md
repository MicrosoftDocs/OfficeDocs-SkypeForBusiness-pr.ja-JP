---
title: 'Lync Server 2013: 場所に基づくルーティングの概要'
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
ms.openlocfilehash: 85d24aeb94a0c16e93d885c5b6db20385cdf0f26
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 での場所に基づくルーティングの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-21_

場所に基づくルーティングでは、国内および国際間の PSTN 通話のルーティングを変更して、有料のバイパスを防止する新しいルールのセットが導入されています。 場所に基づくルーティングは、これらのルールを特定の地域、特定のゲートウェイ、または特定のユーザーのセットに限定するための柔軟性を提供します。

次のシナリオでは、場所に基づいたルーティングによって実行される主な種類の制限について説明します。

  - 出口呼び出し–場所に基づいたルーティングでは、発信者が PSTN の通話を禁止しているのと同じ地域に配置されている pstn ゲートウェイからの発信呼び出しを強制できます。これにより、別の地域にある PSTN ゲートウェイからの呼び出しが、コール.

  - 受信呼び出し–場所に基づくルーティングは、着信呼び出しをルーティングする PSTN ゲートウェイが Lync ユーザーと同じ地域にない場合に、Lync エンドポイントを着信させないようにすることができます。

  - 不明な地域–場所に基づいたルーティングでは、不定の場所にあるユーザーとの間で送受信される PSTN 通話を制限します (つまり、リモートユーザーがインターネットから接続するか、または不明な地域に配置されます)。

  - 国際的な地域–場所に基づいたルーティングによって、ユーザーの場所にローカルのゲートウェイが見つからない場合は、国際 PSTN ゲートウェイを経由した発信呼び出しのルーティングが強制されます。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

