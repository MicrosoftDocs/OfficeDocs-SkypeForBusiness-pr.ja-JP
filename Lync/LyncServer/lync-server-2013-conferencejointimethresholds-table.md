---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds テーブル'
description: 'Lync Server 2013: ConferenceJoinTimeThresholds テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e38c8b99f444e16309882b6a8885d166fdceb9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561673"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="2441e-103">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</span><span class="sxs-lookup"><span data-stu-id="2441e-103">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2441e-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2441e-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2441e-p101">ConferenceJoinTimeThresholds テーブルには、電話会議参加時間要約レポートによって使用される分類境界が含まれます。電話会議参加時間要約レポートは、ユーザーが問題なく電話会議に参加する目的で必要な時間を集計します。これらの時間値は、平均と、以下のカテゴリの 1 つの両方で報告されます。</span><span class="sxs-lookup"><span data-stu-id="2441e-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="2441e-107">2 秒未満。</span><span class="sxs-lookup"><span data-stu-id="2441e-107">Less than 2 seconds.</span></span>

  - <span data-ttu-id="2441e-108">2 ～ 5 秒の間。</span><span class="sxs-lookup"><span data-stu-id="2441e-108">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="2441e-109">5 ～ 10 秒の間。</span><span class="sxs-lookup"><span data-stu-id="2441e-109">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="2441e-110">10 秒以上。</span><span class="sxs-lookup"><span data-stu-id="2441e-110">More than 10 seconds.</span></span>

<span data-ttu-id="2441e-111">ConferenceJoinTimeThresholds テーブルには、2 秒、5 秒、および 10 秒の分類値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2441e-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="2441e-112">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="2441e-112">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2441e-113">Column</span><span class="sxs-lookup"><span data-stu-id="2441e-113">Column</span></span></th>
<th><span data-ttu-id="2441e-114">データ型</span><span class="sxs-lookup"><span data-stu-id="2441e-114">Data Type</span></span></th>
<th><span data-ttu-id="2441e-115">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="2441e-115">Key/Index</span></span></th>
<th><span data-ttu-id="2441e-116">詳細</span><span class="sxs-lookup"><span data-stu-id="2441e-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2441e-117"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="2441e-117"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="2441e-118">int</span><span class="sxs-lookup"><span data-stu-id="2441e-118">int</span></span></p></td>
<td><p><span data-ttu-id="2441e-119">Primary</span><span class="sxs-lookup"><span data-stu-id="2441e-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="2441e-120">分類の一意識別子。</span><span class="sxs-lookup"><span data-stu-id="2441e-120">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2441e-121"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="2441e-121"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="2441e-122">int</span><span class="sxs-lookup"><span data-stu-id="2441e-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2441e-p102">分類の上限。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2441e-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="2441e-125">pbm-2</span><span class="sxs-lookup"><span data-stu-id="2441e-125">2</span></span></p></li>
<li><p><span data-ttu-id="2441e-126">5 </span><span class="sxs-lookup"><span data-stu-id="2441e-126">5</span></span></p></li>
<li><p><span data-ttu-id="2441e-127">10  </span><span class="sxs-lookup"><span data-stu-id="2441e-127">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

