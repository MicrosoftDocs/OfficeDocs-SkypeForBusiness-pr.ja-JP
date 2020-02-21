---
title: 'Lync Server 2013: 常設チャットサーバーのコンプライアンステーブルのリスト'
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
ms.openlocfilehash: 322b700b807f8654e96572a3c040ddd7fe0d1e5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Lync Server 2013 の常設チャットサーバーのコンプライアンステーブルのリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

常設チャットコンプライアンスデータベーススキーマは、次の表で構成されています。

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>常設チャット サーバーのコンプライアンス テーブルのリスト


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 の tblComplianceData</a></p></td>
<td><p>構成済みのアダプターによってまだ処理されていないコンプライアンス イベントが格納されます。</p>
<p>この表には、チャットメッセージやファイルダウンロードなどの常設チャット関連イベントが含まれています。 (参加者のイベントは、tblComplianceParticipant テーブルによって追跡されます。)</p>
<p>(このテーブルのイベントを処理したサーバーは、tblComplianceFanout テーブルに含まれます)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 の tblComplianceFanout</a></p></td>
<td><p>コンプライアンス イベントを処理したサーバーが格納されます。 このテーブルは tblComplianceData テーブルと緊密に結び付けられています。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 の tblComplianceParticipant</a></p></td>
<td><p>チャット サービス別およびサーバー別に現在の参加者が格納されます。 常設チャットサービスから受信した参加およびパーツのコンプライアンスイベントに基づいて維持されます。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 の tblComplianceState</a></p></td>
<td><p>プール全体のコンプライアンス状態情報が含まれます。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

