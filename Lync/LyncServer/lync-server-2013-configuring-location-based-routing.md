---
title: 'Lync Server 2013: 場所に基づくルーティングの構成'
TOCTitle: 場所に基づくルーティングの構成
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994036(v=OCS.15)
ms:contentKeyID: 52056607
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の場所に基づくルーティングの構成

 

_**トピックの最終更新日:** 2015-03-09_

Lync Server 2013 CU1 の場所に基づくルーティングは、 エンタープライズ VoIP の機能です。場所に基づくルーティングは、 Lync Server 2013 CU1 による通話のルーティング方法を制御する通話管理機能です。この機能は、通話を PBX または PSTN の宛先にルーティングできるかどうに関して、Lync 発信者の場所に基づく制約を適用します。場所に基づくルーティングでは、発信者のネットワークの場所に基づいて PSTN 通話に通話承認規則を適用します。発信者の場所は、発信者が接続されたネットワーク サブネットに関連付けられたネットワーク サイトに基づいて決定されます。場所に基づくルーティングを構成するには、最初に エンタープライズ VoIP を展開してから、ネットワーク地域、サイト、サブネットを構成する必要があります。これにより、場所に基づくルーティングを有効にするための基礎が設定されます。

場所に基づくルーティングを展開する前に、まずエンタープライズ VoIP を展開し、ネットワーク地域、サイトを構成して、ネットワーク サブネットをネットワーク サイトに関連付ける必要があります。これが完了した後、場所に基づくルーティングを構成できます。ネットワーク地域、サイト、サブネットを構成する手順については、「 [Lync Server 2013 での高度なエンタープライズ VoIP 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)」を参照してください。

このセクションでは、次の例を使用して場所に基づくルーティングの構成方法を説明します。

![Enterprise Voice、位置情報に基づくルーティングの例](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice、位置情報に基づくルーティングの例")

  
この例で定義されているユーザーを次の表に示します。


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
<td><p>Delhi 会社事務所</p></td>
<td><p>DEL-LYNC-1、DEL-LYNC-2、DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Hyderabad 会社事務所</p></td>
<td><p>HYD-LYNC-1、HYD-LYNC-2、HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>不明 (ホテル)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>Delhi 会社事務所</p></td>
<td><p>DEL-PBX-1、DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Hyderabad 会社事務所</p></td>
<td><p>HYD-PBX-1、HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>不明</p></td>
<td><p>PSTN-1、PSTN-2、PSTN-3</p></td>
</tr>
</tbody>
</table>

  

この例で使用されているシステムを次の表に示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>システム</th>
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
<td><p>Lync Server 2013 CU1、 仲介サーバー</p></td>
<td><p>任意</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN ゲートウェイ 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN ゲートウェイ 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>RED-PBX</p></td>
</tr>
</tbody>
</table>


## このセクション中

  - [Lync Server 2013 でのエンタープライズ VoIP の構成](lync-server-2013-configuring-enterprise-voice.md)

  - [Lync Server 2013 でのネットワーク領域、サイト、サブネットの展開](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Lync Server 2013 での場所に基づくルーティングの有効化](lync-server-2013-enabling-location-based-routing.md)

## 関連項目

#### その他のリソース

[Lync Server 2013 での高度なエンタープライズ VoIP 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

