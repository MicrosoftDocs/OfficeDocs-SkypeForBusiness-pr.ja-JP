---
title: 'Lync Server 2013: VoipDetails テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4aac4ae26de4c80f7ed1396e647701a0b49a1c4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42119240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a>Lync Server 2013 の VoipDetails テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

それぞれのレコードは、少なくとも 1 人のユーザーが VoIP ユーザーであるような 1 回の 2 者間通話を表します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>データ型</th>
<th>キー/インデックス</th>
<th>詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>日付型</p></td>
<td><p>Primary</p></td>
<td><p>セッション要求の時刻。 セッションを一意に識別するために <strong>SessionIdSeq</strong> と併用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessionidseq と</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>セッションを識別するための ID 番号。 セッションを一意に識別するために <strong>SessionIdTime</strong> と併用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fromnumber Id</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者の <strong>PhoneId</strong>。 詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a>」を参照してください。 この値と <strong>FromGatewayId</strong> がどちらも NULL でない場合、発信者は PSTN ユーザーです。</p></td>
</tr>
<tr class="even">
<td><p><strong>Connectednumber Id</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の受信者の <strong>PhoneId</strong>。 詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a>」を参照してください。 この値と <strong>ToGatewayId</strong> がどちらも NULL でない場合、通話の受信者は PSTN ユーザーです。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の発信元の仲介サーバー。 詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の発信先の仲介サーバー。 詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers</a> 」の表を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の発信元のゲートウェイ。 詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の発信先のゲートウェイ。 詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイ表</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を切断したユーザーの URI (ユーザーが URI を持つ場合)。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザー</a> 」の表を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>別の電話から切断された通話を切断した電話の ID。 詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 の電話表</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

