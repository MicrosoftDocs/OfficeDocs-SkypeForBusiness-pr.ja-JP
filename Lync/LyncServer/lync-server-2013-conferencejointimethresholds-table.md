---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds テーブル'
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
ms.openlocfilehash: 7d8dcf3d8b5f74abe6e145d7ac25e43411ca085c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502314"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="7d0d3-102">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</span><span class="sxs-lookup"><span data-stu-id="7d0d3-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d0d3-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7d0d3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7d0d3-p101">ConferenceJoinTimeThresholds テーブルには、電話会議参加時間要約レポートによって使用される分類境界が含まれます。電話会議参加時間要約レポートは、ユーザーが問題なく電話会議に参加する目的で必要な時間を集計します。これらの時間値は、平均と、以下のカテゴリの 1 つの両方で報告されます。</span><span class="sxs-lookup"><span data-stu-id="7d0d3-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="7d0d3-106">2 秒未満。</span><span class="sxs-lookup"><span data-stu-id="7d0d3-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="7d0d3-107">2 ～ 5 秒の間。</span><span class="sxs-lookup"><span data-stu-id="7d0d3-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="7d0d3-108">5 ～ 10 秒の間。</span><span class="sxs-lookup"><span data-stu-id="7d0d3-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="7d0d3-109">10 秒以上。</span><span class="sxs-lookup"><span data-stu-id="7d0d3-109">More than 10 seconds.</span></span>

<span data-ttu-id="7d0d3-110">ConferenceJoinTimeThresholds テーブルには、2 秒、5 秒、および 10 秒の分類値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d0d3-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="7d0d3-111">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7d0d3-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d0d3-112">Column</span><span class="sxs-lookup"><span data-stu-id="7d0d3-112">Column</span></span></th>
<th><span data-ttu-id="7d0d3-113">データ型</span><span class="sxs-lookup"><span data-stu-id="7d0d3-113">Data Type</span></span></th>
<th><span data-ttu-id="7d0d3-114">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="7d0d3-114">Key/Index</span></span></th>
<th><span data-ttu-id="7d0d3-115">詳細</span><span class="sxs-lookup"><span data-stu-id="7d0d3-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d0d3-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="7d0d3-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="7d0d3-117">int</span><span class="sxs-lookup"><span data-stu-id="7d0d3-117">int</span></span></p></td>
<td><p><span data-ttu-id="7d0d3-118">Primary</span><span class="sxs-lookup"><span data-stu-id="7d0d3-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="7d0d3-119">分類の一意識別子。</span><span class="sxs-lookup"><span data-stu-id="7d0d3-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d0d3-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="7d0d3-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="7d0d3-121">int</span><span class="sxs-lookup"><span data-stu-id="7d0d3-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7d0d3-p102">分類の上限。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d0d3-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="7d0d3-124">pbm-2</span><span class="sxs-lookup"><span data-stu-id="7d0d3-124">2</span></span></p></li>
<li><p><span data-ttu-id="7d0d3-125">5 </span><span class="sxs-lookup"><span data-stu-id="7d0d3-125">5</span></span></p></li>
<li><p><span data-ttu-id="7d0d3-126">10  </span><span class="sxs-lookup"><span data-stu-id="7d0d3-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

