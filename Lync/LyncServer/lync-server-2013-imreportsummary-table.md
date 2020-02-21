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
ms.openlocfilehash: 5d13401f38677d75bc40cbb4c1bd56f2fbb7fbb4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="09b6b-102">Lync Server 2013 の IMReportSummary テーブル</span><span class="sxs-lookup"><span data-stu-id="09b6b-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09b6b-103">_**トピックの最終更新日:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="09b6b-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="09b6b-104">IMReportSummaryTable は、組織内で確立されているインスタント メッセージング セッションについての概要レポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="09b6b-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="09b6b-105">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="09b6b-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09b6b-106">列</span><span class="sxs-lookup"><span data-stu-id="09b6b-106">Column</span></span></th>
<th><span data-ttu-id="09b6b-107">データ型</span><span class="sxs-lookup"><span data-stu-id="09b6b-107">Data Type</span></span></th>
<th><span data-ttu-id="09b6b-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="09b6b-108">Key/Index</span></span></th>
<th><span data-ttu-id="09b6b-109">詳細</span><span class="sxs-lookup"><span data-stu-id="09b6b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09b6b-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="09b6b-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="09b6b-111">日付型</span><span class="sxs-lookup"><span data-stu-id="09b6b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="09b6b-112">Primary</span><span class="sxs-lookup"><span data-stu-id="09b6b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="09b6b-113">インスタント メッセージング セッションが開始された日時。</span><span class="sxs-lookup"><span data-stu-id="09b6b-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b6b-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="09b6b-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="09b6b-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="09b6b-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="09b6b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="09b6b-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b6b-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="09b6b-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="09b6b-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="09b6b-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="09b6b-119">Primary</span><span class="sxs-lookup"><span data-stu-id="09b6b-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="09b6b-120">セッションをホストするプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="09b6b-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b6b-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="09b6b-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="09b6b-122">int</span><span class="sxs-lookup"><span data-stu-id="09b6b-122">int</span></span></p></td>
<td><p><span data-ttu-id="09b6b-123">Primary</span><span class="sxs-lookup"><span data-stu-id="09b6b-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="09b6b-124">通話の優先度 (緊急、非緊急など)。</span><span class="sxs-lookup"><span data-stu-id="09b6b-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="09b6b-125">優先度の情報は、 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の呼び出し優先度テーブル</a>に格納されます。</span><span class="sxs-lookup"><span data-stu-id="09b6b-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09b6b-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="09b6b-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="09b6b-127">bigint</span><span class="sxs-lookup"><span data-stu-id="09b6b-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09b6b-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="09b6b-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="09b6b-129">bigint</span><span class="sxs-lookup"><span data-stu-id="09b6b-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="09b6b-130">セッション中に交換されたインスタント メッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="09b6b-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

