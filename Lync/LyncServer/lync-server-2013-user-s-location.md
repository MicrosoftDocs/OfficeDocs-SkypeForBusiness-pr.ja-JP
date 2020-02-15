---
title: 'Lync Server 2013: ユーザーの場所'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbb581f049e8d45d16ace385fc26908d3d8301b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Lync Server 2013 のユーザーの場所

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

場所に基づくルーティングでは、E9-1-1、CAC、および Media バイパスで使用される Lync Server で定義されているものと同じネットワーク地域、サイト、およびサブネットを活用して、通話ルーティング制限を適用して PSTN の有料電話がバイパスされないようにします。 ユーザーの場所は、ユーザーの Lync エンドポイントの IP サブネットによって決まります。 各 IP サブネットは、管理者によって定義されたネットワーク領域に集約されたネットワークサイトに関連付けられています。 場所に基づくルーティングは、ユーザーのネットワークサイトに基づいて適用されます。

場所に基づくルーティングルールは、ネットワークサイト単位で適用されます。つまり、指定された一連のルールが、同じネットワークサイト内に配置された場所に基づいたルーティングで有効になっているすべてのエンドポイントに適用されることを意味します。 管理者は、場所に基づいたルーティングを必要とするネットワークサイトに適用できます。

音声ルーティングポリシーをネットワークサイトごとに定義して、PSTN 電話番号を呼び出すためにネットワークサイトに配置されているすべてのユーザーが使用する特定の PSTN ゲートウェイを定義できます。 このような音声ルーティングポリシーは、ユーザーの音声ポリシーによって、場所に基づくルーティングが有効になっているネットワークサイトにある場合に、ユーザーの音声ポリシーによって定義されたルーティングよりも優先されます。場所に基づくルーティング。 Lync ユーザーが PSTN 通話を行うと、ユーザーの音声ポリシーによって、ユーザーが通話を行うことを承認できるかどうかが決定されます。 ユーザーの音声ポリシーによってユーザーが通話を発信できるようにすると、場所に基づくルーティングによって、呼び出しの出口を決める PSTN ゲートウェイが決まります。 場所に基づくルーティングでは、ユーザーの場所に基づいて、この判断が行われます。

ユーザーの場所は、次の方法で分類できます。

  - ユーザーは、同じネットワークサイト (つまり、office) に配置された PSTN ゲートウェイで、場所に基づいたルーティングと彼の DID (直接の外線番号) を使用できる既知のネットワークサイトにあります。 発信通話のルーティングは、ユーザーが配置されているネットワークサイトの音声ルーティングポリシーによって行われます。 ユーザーへの PSTN 通話の着信は、PSTN ゲートウェイと同じネットワークサイトにあるエンドポイントにルーティングされます。

  - ユーザーは、PSTN ゲートウェイが配置されているネットワークサイトとは異なる、既知のネットワークサイトにあります。 (つまり、ユーザーが別の会社のオフィスに旅行した)。 発信通話のルーティングは、ユーザーが配置されているネットワークサイトの音声ルーティングポリシーを使用して行われます。 ユーザーへの PSTN 通話の着信は、pstn ゲートウェイ以外のサイトにあるエンドポイントにルーティングされないため、pstn の有料電話番号はバイパスされます。

  - ユーザーが Lync Server の展開において不明なネットワークサイトに配置されている場合、発信通話のルーティングは、ユーザーに割り当てられた音声ポリシーに基づいて、場所に基づくルーティング制限にバインドされていない PSTN ゲートウェイに基づきます。 着信 PSTN 通話は、不明なネットワークサイトに配置されているエンドポイントにルーティングされないため、PSTN の有料通話はバイパスされます。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所に基づくルーティングのガイダンス](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

