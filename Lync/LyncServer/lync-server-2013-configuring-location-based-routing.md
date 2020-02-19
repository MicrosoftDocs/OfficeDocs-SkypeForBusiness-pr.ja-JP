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
ms.openlocfilehash: 64e7df946d5e120352c2f0253a87197cb22b7276
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 での場所に基づくルーティングの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-12_

Lync Server 2013 CU1、場所に基づくルーティングはエンタープライズ Voip の機能です。 場所に基づくルーティングは、通話が Lync Server 2013 CU1 によってルーティングされる方法を制御する通話管理機能です。 Lync の発信者の場所に基づいて通話を PBX または PSTN の宛先にルーティングできるかどうかに関する制限を適用します。 場所に基づくルーティングでは、発信者のネットワークの場所に基づいて通話の承認ルールが PSTN 通話に適用されます。 発信者の場所は、発信者が接続されているネットワークサブネットに関連付けられているネットワークサイトに基づいて決定されます。 場所に基づくルーティングを構成するには、最初にエンタープライズ Voip を展開してから、ネットワーク地域、サイト、およびサブネットを構成する必要があります。 これにより、場所に基づくルーティングを有効にするための基盤が設定されます。

場所に基づくルーティングを展開する前に、まずエンタープライズ Voip を展開し、ネットワーク地域、サイトを構成して、ネットワークサブネットをネットワークサイトに関連付ける必要があります。 完了したら、場所に基づくルーティングを構成できます。 ネットワーク地域、サイト、およびサブネットを構成する手順については、「 [Lync Server 2013 での高度なエンタープライズ voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)」を参照してください。

このセクションでは、次の例を使用して、場所に基づくルーティングを構成する手順を説明します。

![エンタープライズ Voip の場所に基づくルーティングの例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "エンタープライズ Voip の場所に基づくルーティングの例")

  
次の表は、この例で定義されているユーザーを表しています。


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
<td><p>ニューデリー企業オフィス</p></td>
<td><p>「DEL-LYNC-1, DEL-LYNC-2, DEL-3」</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Hyderabad 企業オフィス</p></td>
<td><p>HYD-1、HYD、HYD (LYNC-3)</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>不明 (つまりホテル)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>ニューデリー企業オフィス</p></td>
<td><p>DEL-PBX-1、DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Hyderabad 企業オフィス</p></td>
<td><p>HYD-1、HYD (PBX)</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>不明</p></td>
<td><p>PSTN-1、PSTN-2、PSTN-3</p></td>
</tr>
</tbody>
</table>

  

次の表は、この環境例で示されているシステムを示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>System</th>
<th>場所</th>
<th>名前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1 プール</p></td>
<td><p>any</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1、仲介サーバー</p></td>
<td><p>any</p></td>
<td><p>PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN ゲートウェイ1</p></td>
<td><p>デリー</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN ゲートウェイ2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>デリー</p></td>
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

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのエンタープライズ Voip の構成](lync-server-2013-configuring-enterprise-voice.md)

  - [Lync Server 2013 でのネットワーク地域、サイト、およびサブネットの展開](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Lync Server 2013 での場所に基づくルーティングの有効化](lync-server-2013-enabling-location-based-routing.md)

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

