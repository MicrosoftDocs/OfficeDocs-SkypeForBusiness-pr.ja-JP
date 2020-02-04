---
title: 'Lync Server 2013: 会議のための場所に基づくルーティングの構成'
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
ms.openlocfilehash: d9ea90f30dcd9ec9fdde2e6f4db25e7d27ad12cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議のための場所に基づくルーティングの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-09-11_

場所に基づくルーティング会議アプリケーションは、Lync Server 2013 の場所に基づくルーティングの構成に依存します。 主な構成は次のとおりです。

  - 会議の参加者の場所は、ネットワーク サイトに基づいて決定されます。 場所に基づくルーティングを適用するには、ネットワークサイトと関連付けられたネットワークサブネットが Lync Server で定義されている必要があります。

  - 会議の位置情報に基づくルーティングを適用するには、場所に基づくルーティングで Lync の出席者を有効にする必要があります。

  - 会議に参加する PSTN エンドポイントの位置に基づくルーティングを適用するには、PSTN エンドポイントを接続するために使用される SIP トランクが位置情報に基づくルーティング用に構成されている必要があります。

Lync Server 2013 の位置情報に基づくルーティングの展開と構成の詳細については、「[場所ベースのルーティング](lync-server-2013-configuring-location-based-routing.md)を構成する」を参照してください。

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>位置に基づくルーティング会議アプリケーションを有効にする

場所に基づくルーティング会議アプリケーションは、既定では無効になっています。 このアプリケーションを有効にする前に、このアプリケーションに割り当てるのに適した優先順位を決める必要があります。 この優先度を決定するには、Lync Server 管理シェルで次のコマンドレットを実行します。

CsServerApplication-Identity Service: レジストラー:\<Pool FQDN\>

このコマンドレットで\<は、\>位置情報に基づくルーティング会議アプリケーションを有効にするプールをプールの FQDN として指定します。

このコマンドレットは、Lync Server によってホストされているアプリケーションの一覧とそれぞれの priority の値を返します。 場所に基づくルーティング会議アプリケーションには、"UdcAgent" アプリケーションよりも大きく、"DefaultRouting"、"ExumRouting"、"OutboundRouting" アプリケーションよりも小さい優先度の値を割り当てる必要があります。 場所に基づくルーティング会議アプリケーションは、"UdcAgent" アプリケーションの優先度値より1ポイント高い優先度の値に割り当てることをお勧めします。

たとえば、"UdcAgent" アプリケーションの優先度値が "2" の場合、"DefaultRouting" アプリケーションには "8" という優先度の値が設定されています。 "ExumRouting" アプリケーションの優先度値は "9" で、"OutboundRouting" アプリケーションには "10" という優先順位値があります。場所に基づくルーティング会議アプリケーションには、"3" の優先度の値を割り当てる必要があります。 その場合、アプリケーションの優先度は、その他のアプリケーション (優先度: 0 から 1)、"UdcAgent" (優先度: 2)、場所に基づくルーティング会議アプリケーション (優先度: 3)、その他のアプリケーション (優先度: 4 ~ 8)、"DefaultRouting "(優先度: 9)、" ExumRouting "(優先度:10) と" OutboundRouting "(Priority:11)。

場所に基づくルーティング会議アプリケーションの適切な優先度の値を見つけたら、次のコマンドレットを使用して、位置情報に基づくルーティングが有効になっている各フロントエンドプールまたは標準エディションのサーバーに対して、次のコマンドレットを入力します。

新しい-CsServerApplication-Identity Service: レジストラー:\<Pool FQDN\>/LBRouting-priority \<アプリケーション優先\> $true-重要な $true Urihttp://www.microsoft.com/LCS/LBRouting

次に例を示します。

新規の CsServerApplication-Identity Service: レジストラー: Ls2013cu2lbrLBRouting-Priority 3 $true--------------------------------------$truehttp://www.microsoft.com/LCS/LBRouting

このコマンドレットを使用した後、プールまたは場所ベースのルーティング会議アプリケーションが有効になっている Standard Edition サーバーで、すべてのフロントエンドサーバーを再起動します。

<div>


> [!IMPORTANT]  
> 会議への位置情報に基づくルーティング enforcements は、対象のプールまたは Standard Edition サーバーのすべてのフロントエンドサーバーが再起動されるまでは適用されません。



</div>

位置情報に基づくルーティング会議アプリケーションが正常に有効になり、適用可能なすべての Lync サーバーが再起動されると、PSTN の通話を許可しないように、場所ベースのルーティングが有効になっている Lync ユーザーが開催するすべての会議が監視されます

</div>

</div>

<span> </span>

</div>

</div>

</div>

