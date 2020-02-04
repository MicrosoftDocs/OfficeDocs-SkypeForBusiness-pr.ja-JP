---
title: 'Lync Server 2013: IMReportSummary テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7a6be73d31892b5a0d5a3a5b10ad136f92afbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="a3134-102">Lync Server 2013 の IMReportSummary テーブル</span><span class="sxs-lookup"><span data-stu-id="a3134-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3134-103">_**最終更新日:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="a3134-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="a3134-104">Imreportの概要表は、組織内で開催されたインスタントメッセージセッションに関する全体的なレポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="a3134-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="a3134-105">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a3134-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3134-106">列</span><span class="sxs-lookup"><span data-stu-id="a3134-106">Column</span></span></th>
<th><span data-ttu-id="a3134-107">データ型</span><span class="sxs-lookup"><span data-stu-id="a3134-107">Data Type</span></span></th>
<th><span data-ttu-id="a3134-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="a3134-108">Key/Index</span></span></th>
<th><span data-ttu-id="a3134-109">詳細</span><span class="sxs-lookup"><span data-stu-id="a3134-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3134-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="a3134-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a3134-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a3134-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a3134-112">Primary</span><span class="sxs-lookup"><span data-stu-id="a3134-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a3134-113">インスタントメッセージングセッションが開始された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="a3134-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3134-114"><strong>期間</strong></span><span class="sxs-lookup"><span data-stu-id="a3134-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="a3134-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="a3134-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="a3134-116">Primary</span><span class="sxs-lookup"><span data-stu-id="a3134-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3134-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="a3134-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="a3134-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="a3134-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="a3134-119">Primary</span><span class="sxs-lookup"><span data-stu-id="a3134-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="a3134-120">セッションをホストしているプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="a3134-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3134-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="a3134-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="a3134-122">int</span><span class="sxs-lookup"><span data-stu-id="a3134-122">int</span></span></p></td>
<td><p><span data-ttu-id="a3134-123">Primary</span><span class="sxs-lookup"><span data-stu-id="a3134-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="a3134-124">通話の優先度 (緊急または不急など)</span><span class="sxs-lookup"><span data-stu-id="a3134-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="a3134-125">優先度の情報は、 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の callpriorities テーブル</a>に格納されています。</span><span class="sxs-lookup"><span data-stu-id="a3134-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3134-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="a3134-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a3134-127">bigint</span><span class="sxs-lookup"><span data-stu-id="a3134-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3134-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="a3134-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a3134-129">bigint</span><span class="sxs-lookup"><span data-stu-id="a3134-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a3134-130">セッション中に交換されたインスタントメッセージの合計数です。</span><span class="sxs-lookup"><span data-stu-id="a3134-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

