---
title: 'Lync Server 2013: 会議用の Location-Based ルーティングの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5ada5e4af1ed4ed43434ddf4d82abc25f4cd5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507804"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の Location-Based ルーティングの構成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-09-11_

Location-Based ルーティング会議アプリケーションは、Lync Server 2013 Location-Based ルーティングの構成に依存します。 主な構成は次のとおりです。

  - 会議に参加する参加者の場所は、ネットワークサイトに基づいて決定されます。 Location-Based ルーティングを適用するには、ネットワークサイトとそれに関連付けられたネットワークサブネットが Lync Server で定義されている必要があります。

  - 会議の Location-Based ルーティングを適用するには、Location-Based ルーティングに対して Lync の参加者を有効にする必要があります。

  - 会議に参加する PSTN エンドポイントの Location-Based ルーティングを適用するには、PSTN エンドポイントへの接続に使用される SIP トランクが Location-Based ルーティング用に構成されている必要があります。

Lync Server 2013 Location-Based ルーティングの展開および構成の詳細については、「 [場所に基づくルーティング](lync-server-2013-configuring-location-based-routing.md)の構成」を参照してください。

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Location-Based ルーティング会議アプリケーションを有効にする

Location-Based ルーティング会議アプリケーションは、既定では無効になっています。 このアプリケーションを有効にする前に、アプリケーションに割り当てる適切な優先順位を決定する必要があります。 この優先度を確認するには、Lync Server 管理シェルで次のコマンドレットを実行します。

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

このコマンドレットで \<Pool FQDN\> は、Location-Based ルーティング会議アプリケーションを有効にするプールを指定します。

このコマンドレットは、Lync Server でホストされているアプリケーションの一覧とそれぞれの優先度の値を返します。 Location-Based ルーティング会議アプリケーションには、"UdcAgent" アプリケーションよりも大きく、"DefaultRouting"、"ExumRouting"、および "OutboundRouting" アプリケーションよりも小さい優先度の値を割り当てる必要があります。 Location-Based ルーティング会議アプリケーションには、"UdcAgent" アプリケーションの優先度の値よりも1ポイント大きい優先度の値を割り当てることをお勧めします。

たとえば、"UdcAgent" アプリケーションの優先度の値が "2" の場合は、"DefaultRouting" アプリケーションの優先度値は "8" で、"ExumRouting" アプリケーションの優先度値は "9" で、"OutboundRouting" アプリケーションの優先度は "10" に設定されています。その場合は、Location-Based ルーティング会議アプリケーションに優先度の値 "3" を割り当ててください。 これにより、アプリケーションの優先度は次の順序で設定されます。その他のアプリケーション (優先度: 0 から 1)、"UdcAgent" (優先度: 2)、Location-Based ルーティング会議アプリケーション (優先度: 3)、その他のアプリケーション (優先度: 4 ~ 8)、"DefaultRouting" (優先度:10)、"OutboundRouting" (優先度:11)。

Location-Based ルーティング会議アプリケーションの正しい優先度値を確認した後、Location-Based ルーティングに対してユーザーを有効にした各 Front-End プールまたは Standard Edition サーバーに対して次のコマンドレットを入力します。

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

以下に例を示します。

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

このコマンドレットを使用した後、プール内のすべてのフロントエンドサーバー、または Location-Based ルーティング会議アプリケーションが有効になっている Standard Edition サーバーを再起動します。

<div>


> [!IMPORTANT]  
> 強制を電話会議またはコンサルティング転送にルーティングする Location-Based は、該当するプールまたは Standard Edition サーバーのすべてのフロントエンドサーバーが再起動されるまで適用されません。



</div>

Location-Based ルーティング会議アプリケーションが正常に有効になり、適用可能なすべての Lync サーバーが再起動されると、Location-Based ルーティングを有効にした Lync ユーザーが開催したすべての会議が監視され、PSTN 有料電話のバイパスが禁止されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

