---
title: 'Lync Server 2013: 常設チャット サーバーのコンプライアンス テーブルのリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c4f6e9622e839e2f1fd719b8e2d7ba95286247e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Lync Server 2013 の常設チャット サーバーのコンプライアンス テーブルのリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

常設チャットのコンプライアンスデータベーススキーマは、次の表で構成されています。

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>常設チャットサーバーのコンプライアンステーブルの一覧


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>テーブル</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 の tblComplianceData</a></p></td>
<td><p>構成済みのアダプターによってまだ処理されていないコンプライアンスイベントが含まれています。</p>
<p>この表には、チャットメッセージやファイルのダウンロードなどの常設チャット関連イベントが含まれています。 (参加者のイベントは、tblComplianceParticipant テーブルによって追跡されます)。</p>
<p>(この表のイベントを処理したサーバーは、tblComplianceFanout テーブルに一覧表示されます)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 内の tblComplianceFanout</a></p></td>
<td><p>コンプライアンスイベントを処理したサーバーが含まれます。 この表は、tblComplianceData テーブルと密接に結び付いています。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 内の tblComplianceParticipant</a></p></td>
<td><p>チャットサービスとサーバーごとに現在の参加者が含まれます。 これは、常設チャットサービスから受信した参加イベントとパートコンプライアンスイベントに基づいて維持されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 の tblComplianceState</a></p></td>
<td><p>プール全体のコンプライアンスの状態に関する情報が含まれています。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

