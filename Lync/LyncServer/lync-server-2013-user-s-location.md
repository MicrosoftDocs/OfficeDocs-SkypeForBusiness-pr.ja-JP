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
ms.openlocfilehash: 854e887605cc1d3d2b6d394228ebd3e8059644ee
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518834"
---
# <a name="users-location-in-lync-server-2013"></a>Lync Server 2013 のユーザーの場所

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

Location-Based ルーティングでは、E9-1-1、CAC、および Media バイパスで使用される Lync Server で定義されているものと同じネットワーク地域、サイト、およびサブネットを利用して、PSTN の有料電話を回避するための通話ルーティング制限を適用します。 ユーザーの場所は、ユーザーの Lync エンドポイントの IP サブネットによって決まります。 各 IP サブネットは、管理者によって定義されたネットワーク領域に集約されたネットワークサイトに関連付けられています。 Location-Based ルーティングは、ユーザーのネットワークサイトに基づいて適用されます。

Location-Based ルーティングルールはネットワークサイト単位で適用されます。つまり、指定された一連のルールは、同じネットワークサイト内にある Location-Based ルーティングに対して有効になっているすべてのエンドポイントに適用されます。 管理者は、それを必要とするネットワークサイトに Location-Based ルーティングを適用できます。

音声ルーティングポリシーをネットワークサイトごとに定義して、PSTN 電話番号を呼び出すためにネットワークサイトに配置されているすべてのユーザーが使用する特定の PSTN ゲートウェイを定義できます。 このような音声ルーティングポリシーは、ユーザーの音声ポリシーによって定義されたルーティングよりも、ユーザーが Location-Based ルーティングが有効になっているネットワークサイトにある場合に優先されます。また、Location-Based ルーティングが有効になっている他の PSTN ゲートウェイ経由の呼び出しのルーティングを禁止します。 Lync ユーザーが PSTN 通話を行うと、ユーザーの音声ポリシーによって、ユーザーが通話を行うことを承認できるかどうかが決定されます。 ユーザーの音声ポリシーによってユーザーが通話を発信できるようにすると、Location-Based ルーティングによって、呼び出しの出力先となる PSTN ゲートウェイが決まります。 Location-Based ルーティングは、ユーザーの場所に基づいてこの判断を行います。

ユーザーの場所は、次の方法で分類できます。

  - ユーザーは、同じネットワークサイト (つまり office) に配置された PSTN ゲートウェイで Location-Based ルーティングと彼の DID (直接の外線番号) を使用できる既知のネットワークサイトにあります。 発信通話のルーティングは、ユーザーが配置されているネットワークサイトの音声ルーティングポリシーによって行われます。 ユーザーへの PSTN 通話の着信は、PSTN ゲートウェイと同じネットワークサイトにあるエンドポイントにルーティングされます。

  - ユーザーは、PSTN ゲートウェイが配置されているネットワークサイトとは異なる、既知のネットワークサイトにあります。 (つまり、ユーザーが別の会社のオフィスに旅行した)。 発信通話のルーティングは、ユーザーが配置されているネットワークサイトの音声ルーティングポリシーを使用して行われます。 ユーザーへの PSTN 通話の着信は、pstn ゲートウェイ以外のサイトにあるエンドポイントにルーティングされないため、pstn の有料電話番号はバイパスされます。

  - ユーザーが Lync Server の展開において不明なネットワークサイトに配置されている場合、発信通話のルーティングは、ユーザーに割り当てられた音声ポリシーに基づいて、Location-Based ルーティング制限にバインドされていない PSTN ゲートウェイになります。 着信 PSTN 通話は、不明なネットワークサイトに配置されているエンドポイントにルーティングされないため、PSTN の有料通話はバイパスされます。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Location-Based ルーティングに関するガイダンス](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

