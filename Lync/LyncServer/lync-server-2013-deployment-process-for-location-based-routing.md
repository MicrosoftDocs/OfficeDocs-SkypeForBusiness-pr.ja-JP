---
title: 'Lync Server 2013: Location-Based ルーティングの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9d2dfa15dce07fa66678932d8d765ec7308ba75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526924"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 での Location-Based ルーティングの展開プロセス

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-09_

ここでは、Location-Based ルーティングの構成に関連するプロセスの概要について説明します。 Location-Based ルーティングを構成する前に、エンタープライズ Voip を使用して Lync Server Enterprise Edition または Standard Edition を展開する必要があります。 Location-Based ルーティングで必要なコンポーネントは、エンタープライズ Voip を展開するときに既にインストールされ、有効にされています。

### <a name="location-based-routing-deployment-process"></a>Location-Based ルーティングの展開プロセス

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
<th>手順</th>
<th>必要なグループおよび役割</th>
<th>展開のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>エンタープライズ VoIP の展開</p></td>
<td><ul>
<li><p>トランクを構成する</p></li>
<li><p>音声ポリシーを作成する</p></li>
<li><p>音声ルートを定義する</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>エンタープライズ Voip の展開</p></td>
</tr>
<tr class="even">
<td><p>エンタープライズ Voip の展開を確認する</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>ネットワーク地域、サイト、およびサブネットを構成する</p></td>
<td><ul>
<li><p>ネットワーク地域を作成する</p></li>
<li><p>ネットワークサイトを作成する</p></li>
<li><p>サブネットとネットワークサイトの関連付け</p></li>
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
<td><p>Location-Based ルーティングを構成する</p></td>
<td><ul>
<li><p>音声ルーティングポリシーを作成する</p></li>
<li><p>トランクごとに個別のトランク構成を定義する</p></li>
<li><p>音声ポリシーを変更する</p></li>
<li><p>Location-Based ルーティング構成を有効にする</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>サンプルの展開

Location-Based ルーティングによって有効になるメカニズムについては、次の展開を使用して説明します。

![e1bd2230-44 da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44 da-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>着信 PSTN 通話

管理者は、Location-Based ルーティングのために "サイト1ゲートウェイ" への呼び出しをルーティングするように定義されたトランクを有効にし、"サイト1ゲートウェイ" をサイト1に関連付けることができます。 有効にした場合、"Site 1 Gateway" を経由してルーティングされる通話は、サイト1にあるユーザーにのみルーティングされます。 サイト2などの「サイト1ゲートウェイ」トランクを介してルーティングされたすべての通話は、PSTN の有料電話を回避するためにブロックされます。

"サイト1ゲートウェイ" 経由のすべての着信 PSTN 通話は、サイト1にあるエンドポイントへのルーティングのみが許可されます。 たとえば、"Lync user 1" がサイト2に転送されると、"サイト1ゲートウェイ" 経由のすべての着信 PSTN 通話は、サイト2にある "Lync user 1" エンドポイントにルーティングされません。 "Lync user 1" が、ユーザーの場所を特定できない不明なネットワークサイトに移動する場合は、同じルーティングルールが適用されます。

次の表では、このコンテキストでの "Lync user 1" のユーザー環境の概要を示します。


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
<th>ネットワークサイト1にある Lync ユーザー1エンドポイント</th>
<th>ネットワークサイト2にある Lync ユーザー1エンドポイント</th>
<th>不明なネットワークサイトにある Lync ユーザー1エンドポイント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー1への PSTN 通話の着信</p></td>
<td><p>呼び出しは、この場所のエンドポイントにルーティングされます。</p></td>
<td><p>呼び出しは、この場所のエンドポイントにルーティングされません。</p></td>
<td><p>呼び出しは、この場所のエンドポイントにルーティングされません。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>PSTN 通話の発信

音声ルートは、ユーザーに直接割り当てられた音声ポリシーと、ネットワークサイトに割り当てられた音声ルーティングポリシーの両方で参照されます。 両方のポリシーには、呼び出しを異なる方法でルーティングするために使用できるルートへの参照が含まれています。 たとえば、一部のユーザーの音声ポリシーでは、"site 2 Gateway" を経由してすべての発信呼び出しに対してルートを定義する一方で、ネットワークサイト1に配置されているすべてのユーザーに対して音声ルーティングポリシーを定義できます。 これらのユーザーはネットワークサイト1に配置されていますが、それらの発信通話は "サイト1ゲートウェイ" を経由してルーティングされます。

ユーザーが Location-Based ルーティング用に構成されたネットワークサイトに配置されている場合、ネットワークサイトの音声ルーティングポリシールートはユーザーの音声ポリシールートを上書きします。 このルールは、別のサイトに一時的に移動するユーザーに特に役立ちます。 この特定のケースでは、ユーザーは自分の場所に対してローカルなゲートウェイを常に使用します。"Lync user 3" が "Site 2" に配置されている場合は、自分のすべての発信通話が "サイト2ゲートウェイ" 経由でルーティングされますが、サイト1に移動すると、サイト1のユーザーの発信通話はすべて "サイト1ゲートウェイ" を経由してルーティングされます。

次の表は、Lync ユーザー1が次のネットワークサイトから発信呼び出しを行うユーザーの利便性を示しています。


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
<th>ネットワークサイト1</th>
<th>ネットワークサイト2</th>
<th>不明なネットワークサイト、または Location-Based ルーティングに対して有効になっていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>発信呼び出しの承認</p></td>
<td><p>Lync ユーザー1音声ポリシー</p></td>
<td><p>Lync ユーザー1音声ポリシー</p></td>
<td><p>Lync ユーザー1音声ポリシー</p></td>
</tr>
<tr class="even">
<td><p>発信通話のルーティング</p></td>
<td><p>サイト1音声ルーティングポリシー</p></td>
<td><p>サイト2音声ルーティングポリシー</p></td>
<td><p>ユーザーの音声ポリシーおよび Location-Based ルーティングが有効になっていないシステムのみ</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>着信の転送と転送

呼び出しが転送または転送される場合、呼び出しのルーティングは Location-Based ルーティングによって影響を受けます。

次の表は、Lync ユーザー1が別の Lync ユーザーに PSTN 通話を転送または転送することを示しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>着信転送または転送を開始するユーザー</th>
<th>Lync ユーザー2</th>
<th>Lync ユーザー4</th>
<th>ネットワークサイトの Lync ユーザーが Location-Based ルーティングに対して有効になっていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー1</p></td>
<td><p>着信/転送が許可されている</p></td>
<td><p>着信/転送は許可されていません</p></td>
<td><p>着信/転送は許可されていません</p></td>
</tr>
</tbody>
</table>

  
次の表は、転送される Lync ユーザーの場所 (Lync ユーザー2、Lync user 4 など) に基づいて、Location-Based ルーティングが PSTN エンドポイントにどのようにルーティングされるかを示しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>通話が転送または転送されるエンドポイント</th>
<th>Lync ユーザー2</th>
<th>Lync ユーザー4</th>
<th>ネットワークサイトの Lync ユーザーが Location-Based ルーティングに対して有効になっていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>着信転送または転送は、サイト1ゲートウェイ経由でのサイト1音声ルーティングポリシーおよび出口を経由してルーティングされます。</p></td>
<td><p>着信転送または転送は、サイト2の音声ルーティングポリシーおよび出口を介してルーティングされます。</p></td>
<td><p>通話の転送または転送は、Lync ユーザーの音声ポリシーを経由してルーティングされ、場所に基づくルーティングが有効になっていないゲートウェイ経由の出口</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>同時呼び出し

サンプルトポロジで場所ベースのルーティングを構成すると、次の操作が実行されます。

次の表は Location-Based ルーティングが異なる Lync ユーザー (Lync ユーザー2、Lync ユーザー4など) に対して同時呼び出しを許可するかどうかを示しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>着信 PSTN 通話のターゲット</th>
<th>Lync ユーザー2</th>
<th>Lync ユーザー4</th>
<th>ネットワークサイトの Lync ユーザーが Location-Based ルーティングに対して有効になっていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー1</p></td>
<td><p>同時呼び出しを許可する</p></td>
<td><p>同時呼び出しは許可されていません</p></td>
<td><p>同時呼び出しは許可されていません</p></td>
</tr>
</tbody>
</table>

  
次の表に、Location-Based ルーティングで、異なる Lync ユーザー (Lync ユーザー2、Lync user 4 など) から PSTN エンドポイントへの同時呼び出しを許可するかどうかを示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同時呼び出しのターゲット</th>
<th>Lync ユーザー2</th>
<th>Lync ユーザー4</th>
<th>ネットワークサイトの Lync ユーザーが Location-Based ルーティングに対して有効になっていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー1携帯電話 (PSTN エンドポイント)</p></td>
<td><p>通話は、ネットワークサイト1の音声ルーティングポリシーと、サイト1ゲートウェイ経由で送信されます。</p></td>
<td><p>通話は、ネットワークサイト2の音声ルーティングポリシーと、サイト2ゲートウェイ経由で送信されます。</p></td>
<td><p>発信者の音声ポリシーを経由してルーティングし、PSTN ゲートウェイを経由してルーティングする通話は Location-Based ルーティングに対して有効ではない</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での Location-Based ルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

