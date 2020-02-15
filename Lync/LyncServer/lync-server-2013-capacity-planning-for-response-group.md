---
title: 'Lync Server 2013: 応答グループの処理能力の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e5724978347b50db2790e4d5798aace8489acbb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="cd4d4-102">Lync Server 2013 の応答グループの処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="cd4d4-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd4d4-103">_**トピックの最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="cd4d4-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="cd4d4-104">次の表では、容量計画の要件の基礎として使用できる応答グループのユーザーモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cd4d4-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd4d4-105">次の表に示す数値は、すべての応答グループのオーディオファイルに 16 kHz、モノ、16ビットの Wave (.wav) ファイルを使用することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="cd4d4-105">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="cd4d4-106">Windows Media Audio (.wma) など、他のファイル形式を使用する場合は、数字が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd4d4-106">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cd4d4-107">障害復旧の処理能力を計画する場合は、ペアになっているプールの各プールで、両方のプールのすべての応答グループのワークロードを処理できる必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cd4d4-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="cd4d4-108">応答グループのユーザーモデル</span><span class="sxs-lookup"><span data-stu-id="cd4d4-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd4d4-109">測定基準</span><span class="sxs-lookup"><span data-stu-id="cd4d4-109">Metric</span></span></th>
<th><span data-ttu-id="cd4d4-110">Enterprise Edition プールごと (8 台のフロントエンドサーバー)</span><span class="sxs-lookup"><span data-stu-id="cd4d4-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="cd4d4-111">Standard Edition サーバーごと</span><span class="sxs-lookup"><span data-stu-id="cd4d4-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd4d4-112">1秒あたりの着信</span><span class="sxs-lookup"><span data-stu-id="cd4d4-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-113">16 </span><span class="sxs-lookup"><span data-stu-id="cd4d4-113">16</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-114">2 </span><span class="sxs-lookup"><span data-stu-id="cd4d4-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd4d4-115">IVR または MoH に接続された同時通話</span><span class="sxs-lookup"><span data-stu-id="cd4d4-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-116">480</span><span class="sxs-lookup"><span data-stu-id="cd4d4-116">480</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-117">60</span><span class="sxs-lookup"><span data-stu-id="cd4d4-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd4d4-118">匿名の同時セッション (IM なし)</span><span class="sxs-lookup"><span data-stu-id="cd4d4-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-119">224</span><span class="sxs-lookup"><span data-stu-id="cd4d4-119">224</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-120">個</span><span class="sxs-lookup"><span data-stu-id="cd4d4-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd4d4-121">匿名の同時セッション (IM を使用)</span><span class="sxs-lookup"><span data-stu-id="cd4d4-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-122">64</span><span class="sxs-lookup"><span data-stu-id="cd4d4-122">64</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-123">8 </span><span class="sxs-lookup"><span data-stu-id="cd4d4-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd4d4-124">アクティブなエージェント (公式および非公式)</span><span class="sxs-lookup"><span data-stu-id="cd4d4-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-125">1200</span><span class="sxs-lookup"><span data-stu-id="cd4d4-125">1200</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-126">1200</span><span class="sxs-lookup"><span data-stu-id="cd4d4-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd4d4-127">ハントグループの数</span><span class="sxs-lookup"><span data-stu-id="cd4d4-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-128">400</span><span class="sxs-lookup"><span data-stu-id="cd4d4-128">400</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-129">400</span><span class="sxs-lookup"><span data-stu-id="cd4d4-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd4d4-130">IVR グループ数 (音声認識を使用)</span><span class="sxs-lookup"><span data-stu-id="cd4d4-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-131">200</span><span class="sxs-lookup"><span data-stu-id="cd4d4-131">200</span></span></p></td>
<td><p><span data-ttu-id="cd4d4-132">200</span><span class="sxs-lookup"><span data-stu-id="cd4d4-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

