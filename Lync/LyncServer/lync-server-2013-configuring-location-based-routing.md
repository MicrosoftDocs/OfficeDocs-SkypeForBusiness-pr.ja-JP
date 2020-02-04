---
title: 'Lync Server 2013: 場所に基づくルーティングの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e82ae8a0dd9961bfeb9d2a513cb77b0affb2c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 の場所に基づくルーティングの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-12_

Lync Server 2013 CU1、場所に基づくルーティングはエンタープライズ Voip の機能です。 位置情報に基づくルーティングは、Lync Server 2013 CU1 による通話のルーティング方法を制御する通話管理機能です。 Lync の発信者の所在地に基づいて、通話を PBX または PSTN にルーティングできるかどうかに関する制限を適用します。 位置情報に基づくルーティングは、呼び出し元のネットワークの場所に基づいて、着信の承認規則を PSTN 通話に適用します。 発信者の場所は、発信者が接続されているネットワークサブネットに関連付けられたネットワークサイトに基づいて決定されます。 場所に基づくルーティングを構成するには、最初にエンタープライズボイスを展開してから、ネットワークのリージョン、サイト、サブネットを構成する必要があります。 これにより、位置に基づくルーティングを有効にするための基盤が設定されます。

位置情報に基づくルーティングを展開する前に、まずエンタープライズ Voip を展開し、ネットワークの地域、サイトを構成し、ネットワークのサブネットをネットワークサイトに関連付ける必要があります。 完了したら、位置ベースのルーティングを構成できます。 ネットワークの地域、サイト、サブネットを構成する手順については、「 [Lync Server 2013 での高度なエンタープライズ voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)」を参照してください。

このセクションでは、図に示すように、次の例を使用して位置情報に基づくルーティングを構成する方法について説明します。

![エンタープライズ Voip の位置情報に基づくルーティングの例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "エンタープライズ Voip の位置情報に基づくルーティングの例")

  
次の表は、この例で定義されているユーザーを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>エンドポイントの種類</th>
<th>場所</th>
<th>ユーザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>ニューデリーの会社オフィス</p></td>
<td><p>DEL-LYNC-1、DEL-LYNC-2、DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Hyderabad 企業オフィス</p></td>
<td><p>HYD-1、HYD、LYNC-2、HYD、LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>不明 (例: ホテル)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>ニューデリーの会社オフィス</p></td>
<td><p>DELETE-PBX-1、DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Hyderabad 企業オフィス</p></td>
<td><p>HYD-1、HYD、PBX-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>未</p></td>
<td><p>PSTN-1、PSTN-2、PSTN-3</p></td>
</tr>
</tbody>
</table>

  

次の表は、この例の環境で示されているシステムを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Bios</th>
<th>場所</th>
<th>名前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 プール</p></td>
<td><p>任意</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1、仲介サーバー</p></td>
<td><p>任意</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN ゲートウェイ1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN ゲートウェイ2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>赤-PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのエンタープライズ Voip の設定](lync-server-2013-configuring-enterprise-voice.md)

  - [Lync Server 2013 でのネットワークのリージョン、サイト、サブネットの展開](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Lync Server 2013 で位置情報に基づくルーティングを有効にする](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での高度なエンタープライズ Voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

