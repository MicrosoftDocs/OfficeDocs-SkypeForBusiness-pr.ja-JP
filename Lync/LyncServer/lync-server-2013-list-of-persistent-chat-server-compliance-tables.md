---
title: 'Lync Server 2013: 常設チャットサーバーのコンプライアンステーブルのリスト'
description: 'Lync Server 2013: 常設チャットサーバーのコンプライアンステーブルのリスト'
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
ms.openlocfilehash: 47cb28a0ca4180327c2adc48d80e9e41171a7bfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550073"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="df01f-103">Lync Server 2013 の常設チャットサーバーのコンプライアンステーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="df01f-103">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df01f-104">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="df01f-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="df01f-105">常設チャットコンプライアンスデータベーススキーマは、次の表で構成されています。</span><span class="sxs-lookup"><span data-stu-id="df01f-105">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="df01f-106">常設チャット サーバーのコンプライアンス テーブルのリスト</span><span class="sxs-lookup"><span data-stu-id="df01f-106">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df01f-107">Table</span><span class="sxs-lookup"><span data-stu-id="df01f-107">Table</span></span></th>
<th><span data-ttu-id="df01f-108">説明</span><span class="sxs-lookup"><span data-stu-id="df01f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df01f-109"><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013 の tblComplianceData</a></span><span class="sxs-lookup"><span data-stu-id="df01f-109"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df01f-110">構成済みのアダプターによってまだ処理されていないコンプライアンス イベントが格納されます。</span><span class="sxs-lookup"><span data-stu-id="df01f-110">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="df01f-111">この表には、チャットメッセージやファイルダウンロードなどの常設チャット関連イベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df01f-111">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="df01f-112">(参加者のイベントは、tblComplianceParticipant テーブルによって追跡されます。)</span><span class="sxs-lookup"><span data-stu-id="df01f-112">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="df01f-113">(このテーブルのイベントを処理したサーバーは、tblComplianceFanout テーブルに含まれます)</span><span class="sxs-lookup"><span data-stu-id="df01f-113">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df01f-114"><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013 の tblComplianceFanout</a></span><span class="sxs-lookup"><span data-stu-id="df01f-114"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df01f-115">コンプライアンス イベントを処理したサーバーが格納されます。</span><span class="sxs-lookup"><span data-stu-id="df01f-115">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="df01f-116">このテーブルは tblComplianceData テーブルと緊密に結び付けられています。</span><span class="sxs-lookup"><span data-stu-id="df01f-116">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df01f-117"><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013 の tblComplianceParticipant</a></span><span class="sxs-lookup"><span data-stu-id="df01f-117"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df01f-118">チャット サービス別およびサーバー別に現在の参加者が格納されます。</span><span class="sxs-lookup"><span data-stu-id="df01f-118">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="df01f-119">常設チャットサービスから受信した参加およびパーツのコンプライアンスイベントに基づいて維持されます。</span><span class="sxs-lookup"><span data-stu-id="df01f-119">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df01f-120"><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013 の tblComplianceState</a></span><span class="sxs-lookup"><span data-stu-id="df01f-120"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df01f-121">プール全体のコンプライアンス状態情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="df01f-121">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

