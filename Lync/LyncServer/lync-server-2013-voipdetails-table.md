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
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a>Lync Server 2013 の VoipDetails テーブル

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

各レコードは、少なくとも1人のユーザーが VoIP ユーザーである 1 2 パーティーの通話を表します。


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
<td><p><strong>セッション Id</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>セッション要求の時刻。 セッションを一意に識別するために<strong>Sessionidseq</strong>と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>セッションを識別する ID 番号。 セッションを一意に識別するために<strong>Sessionidtime</strong>と組み合わせて使用されます。 詳細については、「 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 のダイアログテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fromnumber Id</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>発信者の<strong>PhoneId</strong> 。 詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 で電話の表</a>」を参照してください。 Not NULL と<strong>Fromgatewayid</strong>が null でない場合は、発信者は PSTN ユーザーです。</p></td>
</tr>
<tr class="even">
<td><p><strong>Connected番号 Id</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話受信者の<strong>PhoneId</strong> 。 詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 で電話の表</a>」を参照してください。 Not NULL と<strong>Togatewayid</strong>が null でない場合は、通話レシーバーは PSTN ユーザーでした。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話が発信される仲介サーバー。 詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers の表</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>仲介サーバーが呼び出されます。 詳細については、「 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 の Mediationservers の表</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>ゲートウェイ通話の発信元です。 詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話の発信先のゲートウェイ。 詳細については、「 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 のゲートウェイテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>ユーザーが URI を持っている場合に、通話を切断したユーザーの URI。 詳細については、「 <a href="lync-server-2013-users-table.md">Lync Server 2013 のユーザーテーブル</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>外部</p></td>
<td><p>通話を切断した電話の ID が電話から切断されました。 詳細については、「 <a href="lync-server-2013-phones-table.md">Lync Server 2013 で電話の表</a>」を参照してください。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

