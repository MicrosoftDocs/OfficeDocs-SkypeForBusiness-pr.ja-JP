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
ms.openlocfilehash: baf29af4b9d1f2b026271b84cb54436e8f4b233f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="7ecca-102">Lync Server 2013 の ConferenceJoinTimeThresholds テーブル</span><span class="sxs-lookup"><span data-stu-id="7ecca-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ecca-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7ecca-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7ecca-104">ConferenceJoinTimeThresholds テーブルには、電話会議の参加時間のサマリーレポートで使用される分類境界が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ecca-104">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="7ecca-105">[会議参加時間のサマリー] レポートは、ユーザーが会議に参加するのに必要な時間の概要を示します。これらの時間値は、平均として、または次のいずれかのカテゴリに報告されます。</span><span class="sxs-lookup"><span data-stu-id="7ecca-105">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="7ecca-106">2秒未満。</span><span class="sxs-lookup"><span data-stu-id="7ecca-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="7ecca-107">2秒と5秒の間。</span><span class="sxs-lookup"><span data-stu-id="7ecca-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="7ecca-108">5 ~ 10 秒の間。</span><span class="sxs-lookup"><span data-stu-id="7ecca-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="7ecca-109">10秒以上</span><span class="sxs-lookup"><span data-stu-id="7ecca-109">More than 10 seconds.</span></span>

<span data-ttu-id="7ecca-110">ConferenceJoinTimeThresholds テーブルには、2秒、5秒、10秒の分類値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ecca-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="7ecca-111">この表は、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7ecca-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7ecca-112">列</span><span class="sxs-lookup"><span data-stu-id="7ecca-112">Column</span></span></th>
<th><span data-ttu-id="7ecca-113">データ型</span><span class="sxs-lookup"><span data-stu-id="7ecca-113">Data Type</span></span></th>
<th><span data-ttu-id="7ecca-114">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="7ecca-114">Key/Index</span></span></th>
<th><span data-ttu-id="7ecca-115">詳細</span><span class="sxs-lookup"><span data-stu-id="7ecca-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7ecca-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="7ecca-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="7ecca-117">int</span><span class="sxs-lookup"><span data-stu-id="7ecca-117">int</span></span></p></td>
<td><p><span data-ttu-id="7ecca-118">Primary</span><span class="sxs-lookup"><span data-stu-id="7ecca-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="7ecca-119">分類の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="7ecca-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7ecca-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="7ecca-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="7ecca-121">int</span><span class="sxs-lookup"><span data-stu-id="7ecca-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7ecca-122">分類の上限。</span><span class="sxs-lookup"><span data-stu-id="7ecca-122">Upper limit for the classification.</span></span> <span data-ttu-id="7ecca-123">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7ecca-123">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="7ecca-124">両面</span><span class="sxs-lookup"><span data-stu-id="7ecca-124">2</span></span></p></li>
<li><p><span data-ttu-id="7ecca-125">5</span><span class="sxs-lookup"><span data-stu-id="7ecca-125">5</span></span></p></li>
<li><p><span data-ttu-id="7ecca-126">常用</span><span class="sxs-lookup"><span data-stu-id="7ecca-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

