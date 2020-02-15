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
ms.openlocfilehash: 287fc0ceff26a5940d717b4efa1ef2c525acb0f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a><span data-ttu-id="97726-102">Lync Server 2013 の IMReportSummary テーブル</span><span class="sxs-lookup"><span data-stu-id="97726-102">IMReportSummary table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97726-103">_**トピックの最終更新日:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="97726-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="97726-104">IMReportSummaryTable は、組織内で確立されているインスタント メッセージング セッションについての概要レポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="97726-104">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="97726-105">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="97726-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97726-106">列</span><span class="sxs-lookup"><span data-stu-id="97726-106">Column</span></span></th>
<th><span data-ttu-id="97726-107">データ型</span><span class="sxs-lookup"><span data-stu-id="97726-107">Data Type</span></span></th>
<th><span data-ttu-id="97726-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="97726-108">Key/Index</span></span></th>
<th><span data-ttu-id="97726-109">詳細</span><span class="sxs-lookup"><span data-stu-id="97726-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97726-110"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="97726-110"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="97726-111">日付型</span><span class="sxs-lookup"><span data-stu-id="97726-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="97726-112">Primary</span><span class="sxs-lookup"><span data-stu-id="97726-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="97726-113">インスタント メッセージング セッションが開始された日時。</span><span class="sxs-lookup"><span data-stu-id="97726-113">Date and time that the instant messaging session began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97726-114"><strong>TimePeriod</strong></span><span class="sxs-lookup"><span data-stu-id="97726-114"><strong>TimePeriod</strong></span></span></p></td>
<td><p><span data-ttu-id="97726-115">char (1)</span><span class="sxs-lookup"><span data-stu-id="97726-115">char(1)</span></span></p></td>
<td><p><span data-ttu-id="97726-116">Primary</span><span class="sxs-lookup"><span data-stu-id="97726-116">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97726-117"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="97726-117"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="97726-118">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="97726-118">nvarchar(257)</span></span></p></td>
<td><p><span data-ttu-id="97726-119">Primary</span><span class="sxs-lookup"><span data-stu-id="97726-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="97726-120">セッションをホストするプールの完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="97726-120">Fully qualified domain name of the pool hosting the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97726-121"><strong>AuthType</strong></span><span class="sxs-lookup"><span data-stu-id="97726-121"><strong>AuthType</strong></span></span></p></td>
<td><p><span data-ttu-id="97726-122">int</span><span class="sxs-lookup"><span data-stu-id="97726-122">int</span></span></p></td>
<td><p><span data-ttu-id="97726-123">Primary</span><span class="sxs-lookup"><span data-stu-id="97726-123">Primary</span></span></p></td>
<td><p><span data-ttu-id="97726-124">通話の優先度 (緊急、非緊急など)。</span><span class="sxs-lookup"><span data-stu-id="97726-124">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="97726-125">優先度の情報は、 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 の呼び出し優先度テーブル</a>に格納されます。</span><span class="sxs-lookup"><span data-stu-id="97726-125">Priority information is stored in the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97726-126"><strong>SessionCount</strong></span><span class="sxs-lookup"><span data-stu-id="97726-126"><strong>SessionCount</strong></span></span></p></td>
<td><p><span data-ttu-id="97726-127">bigint</span><span class="sxs-lookup"><span data-stu-id="97726-127">bigint</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97726-128"><strong>MsgCount</strong></span><span class="sxs-lookup"><span data-stu-id="97726-128"><strong>MsgCount</strong></span></span></p></td>
<td><p><span data-ttu-id="97726-129">bigint</span><span class="sxs-lookup"><span data-stu-id="97726-129">bigint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="97726-130">セッション中に交換されたインスタント メッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="97726-130">Total number of instant messages exchanged during the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

