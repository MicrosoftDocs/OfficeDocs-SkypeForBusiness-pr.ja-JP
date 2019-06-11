---
title: 'Lync Server 2013: 常設チャット サーバーのコンプライアンス テーブルのリスト'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d3df9a0bfd5fa4b8b4acdda15ed86940c2572a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="a6e2e-102">Lync Server 2013 の常設チャット サーバーのコンプライアンス テーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="a6e2e-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6e2e-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a6e2e-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a6e2e-104">常設チャットのコンプライアンスデータベーススキーマは、次の表で構成されています。</span><span class="sxs-lookup"><span data-stu-id="a6e2e-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="a6e2e-105">常設チャットサーバーのコンプライアンステーブルの一覧</span><span class="sxs-lookup"><span data-stu-id="a6e2e-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a6e2e-106">テーブル</span><span class="sxs-lookup"><span data-stu-id="a6e2e-106">Table</span></span></th>
<th><span data-ttu-id="a6e2e-107">説明</span><span class="sxs-lookup"><span data-stu-id="a6e2e-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a6e2e-108"><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 の tblComplianceData</a></span><span class="sxs-lookup"><span data-stu-id="a6e2e-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a6e2e-109">構成済みのアダプターによってまだ処理されていないコンプライアンスイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6e2e-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="a6e2e-110">この表には、チャットメッセージやファイルのダウンロードなどの常設チャット関連イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6e2e-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="a6e2e-111">(参加者のイベントは、tblComplianceParticipant テーブルによって追跡されます)。</span><span class="sxs-lookup"><span data-stu-id="a6e2e-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="a6e2e-112">(この表のイベントを処理したサーバーは、tblComplianceFanout テーブルに一覧表示されます)。</span><span class="sxs-lookup"><span data-stu-id="a6e2e-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e2e-113"><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 内の tblComplianceFanout</a></span><span class="sxs-lookup"><span data-stu-id="a6e2e-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a6e2e-114">コンプライアンスイベントを処理したサーバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6e2e-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="a6e2e-115">この表は、tblComplianceData テーブルと密接に結び付いています。</span><span class="sxs-lookup"><span data-stu-id="a6e2e-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a6e2e-116"><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 内の tblComplianceParticipant</a></span><span class="sxs-lookup"><span data-stu-id="a6e2e-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a6e2e-117">チャットサービスとサーバーごとに現在の参加者が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6e2e-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="a6e2e-118">これは、常設チャットサービスから受信した参加イベントとパートコンプライアンスイベントに基づいて維持されます。</span><span class="sxs-lookup"><span data-stu-id="a6e2e-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a6e2e-119"><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 の tblComplianceState</a></span><span class="sxs-lookup"><span data-stu-id="a6e2e-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a6e2e-120">プール全体のコンプライアンスの状態に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6e2e-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

