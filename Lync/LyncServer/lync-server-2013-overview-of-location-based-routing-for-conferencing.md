---
title: 'Lync Server 2013: 会議の Location-Based ルーティングの概要'
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
ms.openlocfilehash: 9dd3508221babdd9c503e21d5662a1bbe60d4ce0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520954"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の Location-Based ルーティングの概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-19_

Location-Based ルーティング会議アプリケーションは、PSTN 通話のバイパスを防止するメカニズムを Lync 会議に提供します。 アプリケーションはアクティブな会議を監視し、参加している Lync ユーザーの場所に基づいて Location-Based ルーティング制限を適用します。

Location-Based ルーティング会議アプリケーションは、次の条件が満たされた場合に Lync 会議に対して Location-Based ルーティングを適用するかどうかを決定します。

  - Location-Based ルーティングに対して会議の開催者が有効になります。 Location-Based ルーティング制限は、Location-Based ルーティングが有効になっているユーザーによって開催される電話会議にのみ適用されます。

  - 少なくとも1つの会議参加者が PSTN エンドポイントです。 Location-Based ルーティング制限は、PSTN エンドポイントを含む電話会議に対してのみ適用されます。

  - PSTN に電話会議をブリッジするために使用される PSTN ゲートウェイが配置されているネットワークサイト、および開催者と参加者が接続しているネットワークサイトがあります。

Location-Based ルーティング会議アプリケーションによって、Lync ユーザーと PSTN エンドポイントが異なるネットワークサイトから同じ電話会議に参加することができなくなります。 会議の開催者が Location-Based ルーティングに対して有効になっている場合、会議アプリケーションは次の制限を適用します。

  - Lync 会議に参加できるエンドポイントは、既に会議に参加しているエンドポイントに依存します。この制限は、参加したエンドポイントの退室と新しいエンドポイントが会議に参加したときに調整されます。 開催者と参加者が、同じネットワークサイトから Lync 会議に参加している場合、PSTN エンドポイント、同じネットワークサイトの別の参加者、別のネットワークサイトからの別の参加者、または不明なネットワークサイトからの参加者が参加できるようになります。

  - 開催者と参加者が、異なるまたは不明なネットワークサイトから会議に参加している場合は、pstn エンドポイントは Location-Based ルーティングに対して SIP トランクからの ingresses によって有効になっていると、会議に参加することができません。

  - 開催者と参加者が全員同じネットワークサイトから参加していて、PSTN から同じ会議に参加している参加者がいる場合、別のネットワークサイトの Lync エンドポイントは会議に参加できません。

これらの会議 Location-Based ルーティング制限を次の表にまとめます。


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


Location-Based ルーティング会議アプリケーションのその他の特徴は次のとおりです。

  - ユーザーが Location-Based ルーティング制限を使用して電話会議に参加することを許可されていない場合、会議へのユーザー呼び出しは拒否され、その通話が完了していないか、または終了したことが Lync クライアントから報告されます。

  - Location-Based ルーティング強制を使用して電話会議に参加する PSTN エンドポイントは、そのエンドポイントが Location-Based ルーティングに対して有効になっていないトランクを介して参加した場合、その状態にかかわらず、会議への参加を制限されません。

  - PSTN への呼び出しを出口しない SIP トランクを介して Mediadditionalserver に接続されている PBX システムは、SIP トランクが定義されているのと同じネットワークサイトにある Lync ユーザーと同じ強制を持つことになります。 たとえば、PSTN エンドポイントは、PBX ユーザーと Lync ユーザーが同じネットワークサイトに配置されている場合に、そのユーザーとの電話会議に参加できます。そうしないと、PBX ユーザーが Lync ユーザーとは別のネットワークサイトにある場合、PSTN エンドポイントは会議への参加を許可されません。

</div>

<span> </span>

</div>

</div>

</div>

