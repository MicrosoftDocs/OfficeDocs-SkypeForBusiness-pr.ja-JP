---
title: 'Lync Server 2013: 会議の場所に基づくルーティングの構成'
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
ms.openlocfilehash: 6f982f6e484412234c75eadaea925b65ee11bcbb
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の場所に基づくルーティングの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-09-11_

場所に基づくルーティング会議アプリケーションは、Lync Server 2013 の場所に基づくルーティングの構成に依存します。 主な構成は次のとおりです。

  - 会議に参加する参加者の場所は、ネットワークサイトに基づいて決定されます。 場所に基づくルーティングを適用するために、ネットワークサイトとそれに関連付けられたネットワークサブネットが Lync Server で定義されている必要があります。

  - 会議の場所に基づいたルーティングを実施するには、場所に基づいたルーティングで Lync の参加者を有効にする必要があります。

  - 会議に参加する PSTN エンドポイントの場所ベースのルーティングを適用するには、PSTN エンドポイントへの接続に使用される SIP トランクを、場所に基づいたルーティング用に構成する必要があります。

Lync Server 2013 の場所に基づくルーティングの展開および構成の詳細については、「[場所に基づくルーティング](lync-server-2013-configuring-location-based-routing.md)の構成」を参照してください。

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>場所に基づくルーティング会議アプリケーションを有効にする

場所に基づくルーティング会議アプリケーションは、既定では無効になっています。 このアプリケーションを有効にする前に、アプリケーションに割り当てる適切な優先順位を決定する必要があります。 この優先度を確認するには、Lync Server 管理シェルで次のコマンドレットを実行します。

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

このコマンドレットで \<Pool FQDN\> は、は、場所に基づいたルーティング会議アプリケーションを有効にするプールです。

このコマンドレットは、Lync Server でホストされているアプリケーションの一覧とそれぞれの優先度の値を返します。 場所に基づくルーティング会議アプリケーションには、"UdcAgent" アプリケーションよりも大きく、"DefaultRouting"、"ExumRouting"、および "OutboundRouting" アプリケーションより小さい優先度の値を割り当てる必要があります。 場所に基づくルーティング会議アプリケーションは、"UdcAgent" アプリケーションの優先度の値より1ポイント高い優先度の値に割り当てることをお勧めします。

たとえば、"UdcAgent" アプリケーションの優先度の値が "2" の場合は、"DefaultRouting" アプリケーションの優先度値は "8" で、"ExumRouting" アプリケーションの優先度値は "9" で、"OutboundRouting" アプリケーションの優先度値は "10" に設定されている場合は、場所に基づいたルーティング会議アプリケーションに優先度の値 "3" を割り当てる必要があります。 これにより、アプリケーションの優先度は次の順序で設定されます。その他のアプリケーション (優先順位: 0 から 1)、"UdcAgent" (優先度: 2)、場所に基づくルーティング会議アプリケーション (優先度: 3)、その他のアプリケーション (優先度: 4 ~ 8)、"DefaultRouting" (優先度: 9)、"ExumRouting" (優先度:11)。

場所に基づくルーティング会議アプリケーションの正しい優先度の値を見つけたら、次のコマンドレットを各フロントエンドプールまたは Standard Edition サーバーに対して入力します。これは、場所に基づくルーティングが有効になっているユーザーのホームユーザーです。

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

以下に例を示します。

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

このコマンドレットを使用した後、プール内のすべてのフロントエンドサーバー、または場所に基づくルーティング会議アプリケーションが有効になっている Standard Edition サーバーを再起動します。

<div>


> [!IMPORTANT]  
> 場所に基づくルーティング強制から電話会議またはコンサルティング転送は、該当するプールまたは Standard Edition サーバーのすべてのフロントエンドサーバーが再起動されるまで適用されません。



</div>

場所に基づくルーティング会議アプリケーションが正常に有効になり、適用可能なすべての Lync サーバーが再起動されると、場所に基づくルーティングが有効になっている Lync ユーザーによって開催されたすべての会議が監視され、PSTN の有料電話のバイパスが防止されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

