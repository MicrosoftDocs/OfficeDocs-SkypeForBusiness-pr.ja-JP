---
title: 'Lync Server 2013: 場所に基づくルーティングの展開プロセス'
TOCTitle: 場所に基づくルーティングの展開プロセス
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994055(v=OCS.15)
ms:contentKeyID: 52056656
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の場所に基づくルーティングの展開プロセス

 

_**トピックの最終更新日:** 2015-03-09_

ここでは、場所に基づくルーティングの構成に関連するプロセスの概要を説明します。場所に基づくルーティングを構成する前に、エンタープライズ VoIP を使用して Lync ServerEnterprise Edition または Standard Edition を展開する必要があります。場所に基づくルーティングに必要なコンポーネントはあらかじめインストールされていて、エンタープライズ VoIP を展開すると有効になります。

### 場所に基づくルーティングの展開プロセス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>ステップ</th>
<th>必要なグループおよび役割</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>エンタープライズ VoIP の展開</p></td>
<td><ul>
<li><p>トランクの構成</p></li>
<li><p>音声ポリシーの作成</p></li>
<li><p>ボイス ルートの定義</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>エンタープライズ VoIP の展開</p></td>
</tr>
<tr class="even">
<td><p>エンタープライズ VoIP 展開の確認</p></td>
<td><p></p></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>ネットワーク領域、サイト、およびサブネットの構成</p></td>
<td><ul>
<li><p>ネットワーク領域の作成</p></li>
<li><p>ネットワーク サイトの作成</p></li>
<li><p>ネットワーク サイトとサブネットの関連付け</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>ネットワーク領域、サイト、およびサブネットについて<br />
ネットワーク領域の作成または変更<br />
ネットワーク サイトの作成または変更<br />
ネットワーク サイトとサブネットの関連付け</p></td>
</tr>
<tr class="even">
<td><p>場所に基づくルーティングの構成</p></td>
<td><ul>
<li><p>音声ルート ポリシーの作成</p></li>
<li><p>トランクごとに個別の構成設定を定義する</p></li>
<li><p>音声ポリシーの変更</p></li>
<li><p>場所に基づくルーティングの構成設定の有効化</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## 展開例

次の展開を使用して、場所に基づくルーティングで有効になるメカニズムを詳しく示します。

![場所に基づくルーティング トポロジ](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "場所に基づくルーティング トポロジ")

## PSTN 着信

管理者は、場所に基づくルーティングについて、通話を「サイト 1 のゲートウェイ」にルーティングするよう定義されたトランクを有効にして、「サイト 1 のゲートウェイ」をサイト 1 に関連付けることができます。このトランクを有効にすると、「サイト 1 のゲートウェイ」を通ってルーティングされる通話は、サイト 1 にいるユーザーにのみルーティングされます。サイト 2 などの別のサイトにいるユーザー宛ての通話が「サイト 1 のゲートウェイ」のトランクを通ってルーティングされると、PSTN 料の回避を防ぐためにすべてブロックされます。

「サイト 1 のゲートウェイ」を通るすべての PSTN 着信は、サイト 1 にあるエンドポイントにのみルーティングできます。たとえば、「Lync ユーザー 1」がサイト 2 に移動した場合、「サイト 1 のゲートウェイ」を通るすべての PSTN 着信は、サイト 2 にある「Lync ユーザー 1」のエンドポイントにはルーティングされません。「Lync ユーザー 1」が不明なネットワーク サイトに移動して、ユーザーの場所が特定できない場合も、同じルーティング ルールが適用されます。

次の表に、この状況における「Lync ユーザー 1」のユーザー エクスペリエンスを示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>ネットワーク サイト 1 にある Lync ユーザー 1 のエンドポイント</th>
<th>ネットワーク サイト 2 にある Lync ユーザー 1 のエンドポイント</th>
<th>不明なネットワーク サイトにある Lync ユーザー 1 のエンドポイント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー 1 への PSTN 着信</p></td>
<td><p>この場所にあるエンドポイントには通話がルーティングされます。</p></td>
<td><p>この場所にあるエンドポイントには通話がルーティングされません。</p></td>
<td><p>この場所にあるエンドポイントには通話がルーティングされません。</p></td>
</tr>
</tbody>
</table>


## PSTN 発信

ボイス ルートは、ユーザーに直接割り当てられた音声ポリシーと、ネットワーク サイトに割り当てられた音声ルート ポリシーの両方で参照されます。どちらのポリシーにもルートへの参照が含まれ、異なるルーティングに使用できます。たとえば、管理者は、一部のユーザーの音声ポリシーですべての発信のルートが「サイト 2 のゲートウェイ」を通るように定義されていても、ネットワーク サイト 1 にいるすべてのユーザー用の音声ルート ポリシーを、すべての発信が「サイト 1 のゲートウェイ」を通ってルーティングされるように定義できます。その一部のユーザーがネットワーク サイト 1 にいる間は、そのユーザーの発信は「サイト 1 のゲートウェイ」を通ってルーティングされます。

ユーザーが、場所に基づくルーティングが構成されたネットワーク サイトにいる場合、ネットワーク サイトの音声ルート ポリシーのルートがユーザーの音声ポリシーのルートより優先されます。このルールは、ユーザーが一時的に別のサイトに移動する場合に便利です。このような特別なケースでは、ユーザーは常に自分のいる場所のゲートウェイを使用します。「Lync ユーザー 3」が「サイト 2」にいる場合、その発信はすべて「サイト 2 のゲートウェイ」を通ってルーティングされますが、このユーザーがサイト 1 に移動すると、サイト 1 にいる間に発信した通話はすべて「サイト 1 のゲートウェイ」を通ってルーティングされます。

次の表に、Lync ユーザー 1 が次のネットワーク サイトから通話を発信した場合のユーザー エクスペリエンスを示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>ネットワーク サイト 1</th>
<th>ネットワーク サイト 2</th>
<th>不明なネットワーク サイト、または場所に基づくルーティングが有効になっていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>発信の承認</p></td>
<td><p>Lync ユーザー 1 の音声ポリシー</p></td>
<td><p>Lync ユーザー 1 の音声ポリシー</p></td>
<td><p>Lync ユーザー 1 の音声ポリシー</p></td>
</tr>
<tr class="even">
<td><p>発信のルーティング</p></td>
<td><p>サイト 1 の音声ルート ポリシー</p></td>
<td><p>サイト 2 の音声ルート ポリシー</p></td>
<td><p>ユーザーの音声ポリシー、および場所に基づくルーティングが有効になっていないシステム宛てのみ</p></td>
</tr>
</tbody>
</table>


## 通話と着信の転送

通話または着信を転送する場合、場所に基づくルーティングが通話のルーティングに影響します。

次の表に、Lync ユーザー 1 が PSTN 通話または着信を別の Lync ユーザーに転送する状況を示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ユーザーが通話または着信の転送を開始</th>
<th>Lync ユーザー 2</th>
<th>Lync ユーザー 4</th>
<th>場所に基づくルーティングが有効になっていないネットワーク サイトの Lync ユーザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー 1</p></td>
<td><p>通話または着信を転送できます。</p></td>
<td><p>通話または着信を転送できません。</p></td>
<td><p>通話または着信を転送できません。</p></td>
</tr>
</tbody>
</table>

  
次の表に、転送先の Lync ユーザー (Lync ユーザー 2、Lync ユーザー 4 など) の場所に応じて、場所に基づくルーティングが通話の PSTN エンドポイントへのルーティングにどのように影響するかを示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通話または着信の転送先のエンドポイント</th>
<th>Lync ユーザー 2</th>
<th>Lync ユーザー 4</th>
<th>場所に基づくルーティングが有効になっていないネットワーク サイトの Lync ユーザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>通話または着信の転送は、サイト 1 の音声ルート ポリシーでルーティングされ、サイト 1 のゲートウェイを通って出ていきます。</p></td>
<td><p>通話または着信の転送は、サイト 2 の音声ルート ポリシーでルーティングされ、サイト 2 のゲートウェイを通って出ていきます。</p></td>
<td><p>通話または着信の転送は、Lync ユーザーの音声ポリシーでルーティングされ、場所に基づくルーティングが有効になっていないゲートウェイがあれば、そこを通って出ていきます。</p></td>
</tr>
</tbody>
</table>


## 同時呼び出し

このサンプル トポロジに場所に基づくルーティングを構成すると、次のような影響があります。

次の表に、場所に基づくルーティングで異なる Lync ユーザー (Lync ユーザー 2、Lync ユーザー 4 など) への同時呼び出しができるかどうかを示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>PSTN 着信の対象</th>
<th>Lync ユーザー 2</th>
<th>Lync ユーザー 4</th>
<th>場所に基づくルーティングが有効になっていないネットワーク サイトの Lync ユーザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー 1</p></td>
<td><p>同時呼び出しができます。</p></td>
<td><p>同時呼び出しができません。</p></td>
<td><p>同時呼び出しができません。</p></td>
</tr>
</tbody>
</table>

  
次の表に、場所に基づくルーティングで異なる Lync ユーザー (Lync ユーザー 2、Lync ユーザー 4 など) から PSTN エンドポイントへの同時呼び出しができるかどうかを示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同時呼び出しのターゲット ユーザー</th>
<th>Lync ユーザー 2</th>
<th>Lync ユーザー 4</th>
<th>場所に基づくルーティングが有効になっていないネットワーク サイトの Lync ユーザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー 1 の携帯電話 (PSTN エンドポイント)</p></td>
<td><p>通話は、ネットワーク サイト 1 の音声ルート ポリシーでルーティングされ、サイト 1 のゲートウェイを通って出ていきます。</p></td>
<td><p>通話は、ネットワーク サイト 2 の音声ルート ポリシーでルーティングされ、サイト 2 のゲートウェイを通って出ていきます。</p></td>
<td><p>通話は、発信元の音声ポリシーでルーティングされ、場所に基づくルーティングが有効になっていない PSTN ゲートウェイを通って出ていきます。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### その他のリソース

[Lync Server 2013 での場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)

