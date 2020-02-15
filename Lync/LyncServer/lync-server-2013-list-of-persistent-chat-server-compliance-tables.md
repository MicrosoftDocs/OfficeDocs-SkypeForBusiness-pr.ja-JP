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
ms.openlocfilehash: fab78f554c94e11c808eeb28929d6b4511c3a695
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="4d681-102">Lync Server 2013 の常設チャットサーバーのコンプライアンステーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="4d681-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d681-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="4d681-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="4d681-104">常設チャットコンプライアンスデータベーススキーマは、次の表で構成されています。</span><span class="sxs-lookup"><span data-stu-id="4d681-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="4d681-105">常設チャット サーバーのコンプライアンス テーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="4d681-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d681-106">Table</span><span class="sxs-lookup"><span data-stu-id="4d681-106">Table</span></span></th>
<th><span data-ttu-id="4d681-107">説明</span><span class="sxs-lookup"><span data-stu-id="4d681-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d681-108"><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 の tblComplianceData</a></span><span class="sxs-lookup"><span data-stu-id="4d681-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4d681-109">構成済みのアダプターによってまだ処理されていないコンプライアンス イベントが格納されます。</span><span class="sxs-lookup"><span data-stu-id="4d681-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="4d681-110">この表には、チャットメッセージやファイルダウンロードなどの常設チャット関連イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4d681-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="4d681-111">(参加者のイベントは、tblComplianceParticipant テーブルによって追跡されます。)</span><span class="sxs-lookup"><span data-stu-id="4d681-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="4d681-112">(このテーブルのイベントを処理したサーバーは、tblComplianceFanout テーブルに含まれます)</span><span class="sxs-lookup"><span data-stu-id="4d681-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d681-113"><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 の tblComplianceFanout</a></span><span class="sxs-lookup"><span data-stu-id="4d681-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4d681-114">コンプライアンス イベントを処理したサーバーが格納されます。</span><span class="sxs-lookup"><span data-stu-id="4d681-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="4d681-115">このテーブルは tblComplianceData テーブルと緊密に結び付けられています。</span><span class="sxs-lookup"><span data-stu-id="4d681-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d681-116"><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 の tblComplianceParticipant</a></span><span class="sxs-lookup"><span data-stu-id="4d681-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4d681-117">チャット サービス別およびサーバー別に現在の参加者が格納されます。</span><span class="sxs-lookup"><span data-stu-id="4d681-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="4d681-118">常設チャットサービスから受信した参加およびパーツのコンプライアンスイベントに基づいて維持されます。</span><span class="sxs-lookup"><span data-stu-id="4d681-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d681-119"><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 の tblComplianceState</a></span><span class="sxs-lookup"><span data-stu-id="4d681-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4d681-120">プール全体のコンプライアンス状態情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d681-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

