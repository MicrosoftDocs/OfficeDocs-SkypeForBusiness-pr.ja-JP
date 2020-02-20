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
ms.openlocfilehash: 9cded0c566e5bbef0703227b71699f02b73145cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="f525a-102">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</span><span class="sxs-lookup"><span data-stu-id="f525a-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f525a-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f525a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f525a-p101">ConferenceJoinTimeThresholds テーブルには、電話会議参加時間要約レポートによって使用される分類境界が含まれます。電話会議参加時間要約レポートは、ユーザーが問題なく電話会議に参加する目的で必要な時間を集計します。これらの時間値は、平均と、以下のカテゴリの 1 つの両方で報告されます。</span><span class="sxs-lookup"><span data-stu-id="f525a-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="f525a-106">2 秒未満。</span><span class="sxs-lookup"><span data-stu-id="f525a-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="f525a-107">2 ～ 5 秒の間。</span><span class="sxs-lookup"><span data-stu-id="f525a-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="f525a-108">5 ～ 10 秒の間。</span><span class="sxs-lookup"><span data-stu-id="f525a-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="f525a-109">10 秒以上。</span><span class="sxs-lookup"><span data-stu-id="f525a-109">More than 10 seconds.</span></span>

<span data-ttu-id="f525a-110">ConferenceJoinTimeThresholds テーブルには、2 秒、5 秒、および 10 秒の分類値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f525a-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="f525a-111">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f525a-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f525a-112">列</span><span class="sxs-lookup"><span data-stu-id="f525a-112">Column</span></span></th>
<th><span data-ttu-id="f525a-113">データ型</span><span class="sxs-lookup"><span data-stu-id="f525a-113">Data Type</span></span></th>
<th><span data-ttu-id="f525a-114">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="f525a-114">Key/Index</span></span></th>
<th><span data-ttu-id="f525a-115">詳細</span><span class="sxs-lookup"><span data-stu-id="f525a-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f525a-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="f525a-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="f525a-117">int</span><span class="sxs-lookup"><span data-stu-id="f525a-117">int</span></span></p></td>
<td><p><span data-ttu-id="f525a-118">Primary</span><span class="sxs-lookup"><span data-stu-id="f525a-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="f525a-119">分類の一意識別子。</span><span class="sxs-lookup"><span data-stu-id="f525a-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f525a-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="f525a-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="f525a-121">int</span><span class="sxs-lookup"><span data-stu-id="f525a-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f525a-p102">分類の上限。有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f525a-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="f525a-124">pbm-2</span><span class="sxs-lookup"><span data-stu-id="f525a-124">2</span></span></p></li>
<li><p><span data-ttu-id="f525a-125">5</span><span class="sxs-lookup"><span data-stu-id="f525a-125">5</span></span></p></li>
<li><p><span data-ttu-id="f525a-126">10 </span><span class="sxs-lookup"><span data-stu-id="f525a-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

