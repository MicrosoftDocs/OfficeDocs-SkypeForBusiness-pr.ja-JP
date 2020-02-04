---
title: 'Lync Server 2013: 場所に基づくルーティングの展開プロセス'
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
ms.openlocfilehash: 02e09106bc9d96fbfab2935aec07f3c472f49d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 の場所に基づくルーティングの展開プロセス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-09_

このトピックでは、位置情報に基づくルーティングの構成に関連するプロセスの概要を示します。 位置情報に基づくルーティングを構成する前に、Lync Server Enterprise Edition または Standard Edition をエンタープライズ Voip に展開する必要があります。 エンタープライズ Voip を展開すると、位置情報に基づくルーティングに必要なコンポーネントが既にインストールされ、有効になります。

### <a name="location-based-routing-deployment-process"></a>位置情報に基づくルーティングの展開プロセス

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>段階</th>
<th>ステップ</th>
<th>必要なグループおよび役割</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>エンタープライズ VoIP の展開</p></td>
<td><ul>
<li><p>Trunks を構成する</p></li>
<li><p>音声ポリシーを作成する</p></li>
<li><p>ボイスルートの定義</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>エンタープライズボイスの展開</p></td>
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
<td><p>ネットワークのリージョン、サイト、サブネットを構成する</p></td>
<td><ul>
<li><p>ネットワークの領域を作成する</p></li>
<li><p>ネットワークサイトを作成する</p></li>
<li><p>サブネットとネットワークサイトを関連付ける</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>ネットワークの領域、サイト、サブネットについて<br />
ネットワーク領域を作成または変更する<br />
ネットワークサイトを作成または変更する<br />
サブネットとネットワークサイトを関連付ける</p></td>
</tr>
<tr class="even">
<td><p>位置に基づくルーティングを構成する</p></td>
<td><ul>
<li><p>ボイスルーティングポリシーを作成する</p></li>
<li><p>トランクごとに個別のトランク構成を定義する</p></li>
<li><p>ボイスポリシーの変更</p></li>
<li><p>位置に基づくルーティング構成を有効にする</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>展開の例

次の展開は、位置情報に基づくルーティングによって有効になるメカニズムの詳細を示すために使用されます。

![4784 e1bd2230-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "4784 e1bd2230-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>着信 PSTN 通話

管理者は、場所に基づくルーティングのために "サイト1ゲートウェイ" への通話をルーティングするように定義されたトランクを有効にし、"サイト1ゲートウェイ" をサイト1に関連付けることができます。 有効にすると、"サイト1ゲートウェイ" 経由でルーティングされた通話は、サイト1にあるユーザーにのみルーティングされます。 サイト2などのサイト内のユーザーに送信される "サイト1ゲートウェイ" トランク経由でルーティングされたすべての通話は、PSTN の有料電話のバイパスを防ぐためにブロックされます。

"サイト1ゲートウェイ" 経由でのすべての着信 PSTN 通話は、サイト1にあるエンドポイントにのみルーティングできます。 たとえば、"Lync user 1" がサイト2に転送されると、"サイト1ゲートウェイ" を経由するすべての着信 PSTN 通話は、サイト2にある "Lync user 1" エンドポイントにルーティングされません。 "Lync user 1" は、ユーザーの位置情報を特定できない不明のネットワークサイトに移動する場合に、同じルーティングルールが適用されます。

次の表は、このコンテキストでの "Lync user 1" のユーザーエクスペリエンスをまとめたものです。


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
<th>不明のネットワークサイトにある Lync ユーザー1エンドポイント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー1への着信 PSTN 通話</p></td>
<td><p>通話はこの場所のエンドポイントにルーティングされます</p></td>
<td><p>通話はこの場所のエンドポイントにはルーティングされません</p></td>
<td><p>通話はこの場所のエンドポイントにはルーティングされません</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>発信 PSTN 通話

音声ルートは、ユーザーに直接割り当てられている音声ポリシーと、ネットワークサイトに割り当てられているボイスルーティングポリシーの両方で参照されます。 どちらのポリシーにもルートへの参照が含まれており、異なる方法で通話をルーティングするために使うことができます。 たとえば、管理者は、特定のユーザーのボイスポリシーで "サイト2ゲートウェイ" を使ってすべての発信通話のルートを定義しながら、ネットワークサイト1のすべてのユーザーに対してボイスルーティングポリシーを定義できます。 これらのユーザーはネットワークサイト1に配置されていますが、発信通話は "サイト1ゲートウェイ" を介してルーティングされます。

場所に基づくルーティング用に構成されたネットワークサイトにユーザーがいる場合、ネットワークサイトのボイスルーティングポリシーのルートは、ユーザーのボイスポリシールートを上書きします。 この規則は、別のサイトに一時的に移動するユーザーに特に便利です。 この例では、ユーザーは自分の位置に対してローカルなゲートウェイを常に使用します。"Lync user 3" を "サイト 2" に配置している場合、すべての送信通話は "サイト2ゲートウェイ" 経由でルーティングされますが、サイト1に移動すると、サイト1のユーザーが送信したすべての発信通話は、"サイト1ゲートウェイ" 経由でルーティングされます。

次の表は、Lync ユーザー1が次のネットワークサイトから発信通話を発信した場合のユーザーエクスペリエンスを示しています。


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
<th>不明のネットワークサイト、または場所に基づくルーティングでは無効</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>発信の承認</p></td>
<td><p>Lync ユーザー1のボイスポリシー</p></td>
<td><p>Lync ユーザー1のボイスポリシー</p></td>
<td><p>Lync ユーザー1のボイスポリシー</p></td>
</tr>
<tr class="even">
<td><p>発信通話のルーティング</p></td>
<td><p>サイト1ボイスルーティングポリシー</p></td>
<td><p>サイト2ボイスルーティングポリシー</p></td>
<td><p>ユーザーのボイスポリシーと、位置情報に基づくルーティングで有効になっていないシステムのみ</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>着信の転送と転送

通話が転送または転送されると、通話のルーティングが位置情報に基づくルーティングの影響を受けます。

次の表は、Lync ユーザー1が、別の Lync ユーザーに PSTN 通話を転送または転送する方法を示しています。


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
<th>ネットワークサイトの Lync ユーザーが位置情報に基づくルーティングを有効にしていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー1</p></td>
<td><p>通話または着信を転送できます。</p></td>
<td><p>通話または着信を転送できません。</p></td>
<td><p>通話または着信を転送できません。</p></td>
</tr>
</tbody>
</table>

  
次の表は、場所に基づくルーティングが、転送される Lync ユーザー (Lync ユーザー2、Lync ユーザー4など) の場所に基づいて通話が PSTN エンドポイントにどのようにルーティングされるかを示しています。


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
<th>ネットワークサイトの Lync ユーザーが位置情報に基づくルーティングを有効にしていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN エンドポイント</p></td>
<td><p>着信の転送または転送は、サイト1のゲートウェイ経由でサイト1のボイスルーティングポリシーと出口を経由してルーティングされます</p></td>
<td><p>着信の転送または転送は、サイト2ゲートウェイ経由でサイト2のボイスルーティングポリシーと出口を経由してルーティングされる</p></td>
<td><p>着信の転送または転送は、Lync ユーザーの音声ポリシーを通じてルーティングされ、位置情報に基づくルーティングのためにゲートウェイ経由で送信が有効になっていない (使用可能な場合)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>同時呼び出し

サンプルトポロジで位置情報に基づくルーティングを構成すると、次の操作が強制されます。

次の表は、場所に基づくルーティングで、さまざまな Lync ユーザー (Lync ユーザー2、Lync ユーザー4など) の同時呼び出しを許可するかどうかを示しています。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>着信 PSTN 通話ターゲット</th>
<th>Lync ユーザー2</th>
<th>Lync ユーザー4</th>
<th>ネットワークサイトの Lync ユーザーが位置情報に基づくルーティングを有効にしていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー1</p></td>
<td><p>同時呼び出しが許可されている</p></td>
<td><p>同時呼び出しが許可されていない</p></td>
<td><p>同時呼び出しが許可されていない</p></td>
</tr>
</tbody>
</table>

  
次の表は、場所ベースのルーティングで、異なる Lync ユーザーから PSTN エンドポイントへの同時呼び出しを許可するかどうか (Lync ユーザー2、Lync ユーザー4など) を示しています。


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
<th>Lync ユーザー2</th>
<th>Lync ユーザー4</th>
<th>ネットワークサイトの Lync ユーザーが位置情報に基づくルーティングを有効にしていない</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync ユーザー1携帯電話 (PSTN エンドポイント)</p></td>
<td><p>ネットワークサイト1のボイスルーティングポリシーと出口によるルーティング (サイト1ゲートウェイ経由)</p></td>
<td><p>サイト2ゲートウェイ経由でのネットワークサイト2のボイスルーティングポリシーと出口による通話</p></td>
<td><p>発信者の音声ポリシーを通してルーティングし、位置情報に基づくルーティングのために PSTN ゲートウェイ経由で着信する</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での場所に基づくルーティングの計画](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

