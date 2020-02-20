---
title: 'Lync Server 2013: 会議の場所に基づくルーティングの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 863cd213fb28d3adeedc04a5d46e4310ea4cd83b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の場所に基づくルーティングの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-19_

場所に基づくルーティング会議アプリケーションは、PSTN 有料電話のバイパスを防止するメカニズムを Lync 会議に提供します。 アプリケーションはアクティブな会議を監視し、参加している Lync ユーザーの場所に基づいて、場所に基づくルーティング制限を適用します。

場所に基づくルーティング会議アプリケーションは、次の条件が満たされた場合に、Lync 会議に対して場所に基づくルーティングを適用するかどうかを決定します。

  - 会議の開催者は、場所に基づくルーティングが有効になっています。 場所に基づくルーティングの制限は、場所に基づくルーティングが有効になっているユーザーによって開催される電話会議にのみ適用されます。

  - 少なくとも1つの会議参加者が PSTN エンドポイントです。 場所に基づくルーティング制限は、PSTN エンドポイントを含む電話会議に対してのみ適用されます。

  - PSTN に電話会議をブリッジするために使用される PSTN ゲートウェイが配置されているネットワークサイト、および開催者と参加者が接続しているネットワークサイトがあります。

場所に基づくルーティング会議アプリケーションによって、Lync ユーザーと PSTN エンドポイントを異なるネットワークサイトから同じ電話会議に参加させることができなくなります。 会議の開催者が場所に基づいたルーティングを有効にしている場合、会議アプリケーションは次の制限を適用します。

  - Lync 会議に参加できるエンドポイントは、既に会議に参加しているエンドポイントに依存します。この制限は、参加したエンドポイントの退室と新しいエンドポイントが会議に参加したときに調整されます。 開催者と参加者が、同じネットワークサイトから Lync 会議に参加している場合、PSTN エンドポイント、同じネットワークサイトの別の参加者、別のネットワークサイトからの別の参加者、または不明なネットワークサイトからの参加者が許可されている場合申し込み.

  - 開催者と参加者が、異なるまたは不明なネットワークサイトから会議に参加している場合、pstn エンドポイントは、場所に基づくルーティングが有効になっている SIP トランクからの ingresses による会議への参加を許可されません。

  - 開催者と参加者が全員同じネットワークサイトから参加していて、PSTN から同じ会議に参加している参加者がいる場合、別のネットワークサイトの Lync エンドポイントは会議に参加できません。

これらの会議の場所に基づくルーティング制限を次の表にまとめます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>任意の時点での会議のユーザー</p></td>
<td><p>会議への参加が許可されたユーザー</p></td>
<td><p>ユーザーが会議に参加することは許可されていません</p></td>
</tr>
<tr class="even">
<td><p>単一のネットワークサイトからの Lync VoIP クライアントユーザー</p></td>
<td><p>同じネットワークサイトからの Lync VoIP クライアントユーザー</p>
<p>別のネットワークサイトからの Lync VoIP クライアントユーザー</p>
<p>不明なネットワークサイトからの Lync VoIP クライアントユーザー</p>
<p>フェデレーション Lync VoIP クライアントユーザー</p>
<p>PSTN エンドポイントから参加しているユーザー</p></td>
<td><p>なし</p></td>
</tr>
<tr class="odd">
<td><p>不明なネットワークサイトからの Lync VoIP クライアントユーザー</p></td>
<td><p>任意のサイトの Lync VoIP クライアントユーザー</p>
<p>不明なサイトからの Lync VoIP クライアントユーザー</p>
<p>フェデレーション Lync VoIP クライアントユーザー</p></td>
<td><p>PSTN エンドポイント経由で参加するユーザー</p></td>
</tr>
<tr class="even">
<td><p>異なるネットワークサイトからの Lync VoIP クライアントユーザー</p></td>
<td><p>任意のネットワークサイトからの Lync VoIP クライアントユーザー</p>
<p>不明なネットワークサイトからの Lync VoIP クライアントユーザー</p>
<p>フェデレーション Lync VoIP クライアントユーザー</p></td>
<td><p>PSTN エンドポイント経由で参加するユーザー</p></td>
</tr>
<tr class="odd">
<td><p>単一のネットワークサイトからの Lync VoIP クライアントユーザーと PSTN エンドポイントから参加しているユーザー</p></td>
<td><p>同じネットワークサイトからの Lync VoIP クライアントユーザー</p></td>
<td><p>別のネットワークサイトからの Lync VoIP クライアントユーザー</p>
<p>不明なネットワークサイトからの Lync VoIP クライアントユーザー</p>
<p>フェデレーション Lync VoIP クライアントユーザー</p></td>
</tr>
</tbody>
</table>


場所に基づくルーティング会議アプリケーションのその他の特徴は次のとおりです。

  - ユーザーが会議に参加することを許可されていない場所に基づいたルーティング制限により、会議へのユーザー呼び出しが拒否され、その通話が完了していないか、終了したことが Lync クライアントから報告されます。

  - 場所に基づくルーティングが有効になっていないトランクを介してエンドポイントが参加している場合、場所に基づいたルーティング強制を使用して会議に参加する PSTN エンドポイントは、その状態にかかわらず、会議への参加を制限されません。

  - PSTN への呼び出しを出口しない SIP トランクを介して Mediadditionalserver に接続されている PBX システムは、SIP トランクが定義されているのと同じネットワークサイトにある Lync ユーザーと同じ強制を持つことになります。 たとえば、PSTN エンドポイントは、PBX ユーザーと Lync ユーザーが同じネットワークサイトに配置されている場合に、そのユーザーとの電話会議に参加できます。そうしないと、PBX ユーザーが Lync ユーザーとは別のネットワークサイトにある場合、PSTN エンドポイントは会議への参加を許可されません。

</div>

<span> </span>

</div>

</div>

</div>

