---
title: 'Lync Server 2013: 応答グループの処理能力の計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="d970b-102">Lync Server 2013 の応答グループの処理能力の計画</span><span class="sxs-lookup"><span data-stu-id="d970b-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d970b-103">_**最終更新日:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="d970b-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="d970b-104">次の表では、キャパシティ計画の要件の基礎として使用できる応答グループのユーザーモデルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d970b-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d970b-p101">次の表の数字は、すべての応答グループのオーディオ ファイルに、16 kHz、モノ、16 ビットの WAVE (.wav) ファイルを使用することを前提としています。Windows Media Audio (.wma) ファイルなどの他のファイル形式を使用した場合は、数字が変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d970b-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d970b-107">障害復旧のキャパシティ計画時には、ペアになっているプールの各プールで、両方のプールに含まれるすべての応答グループのワークロードを処理する必要があることを念頭においてください。</span><span class="sxs-lookup"><span data-stu-id="d970b-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="d970b-108">応答グループのユーザー モデル</span><span class="sxs-lookup"><span data-stu-id="d970b-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d970b-109">指標</span><span class="sxs-lookup"><span data-stu-id="d970b-109">Metric</span></span></th>
<th><span data-ttu-id="d970b-110">Enterprise Edition プール (8 台のフロントエンドサーバーを含む)</span><span class="sxs-lookup"><span data-stu-id="d970b-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="d970b-111">Standard Edition サーバーごと</span><span class="sxs-lookup"><span data-stu-id="d970b-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d970b-112">1 秒あたりの着信</span><span class="sxs-lookup"><span data-stu-id="d970b-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="d970b-113">16</span><span class="sxs-lookup"><span data-stu-id="d970b-113">16</span></span></p></td>
<td><p><span data-ttu-id="d970b-114">2</span><span class="sxs-lookup"><span data-stu-id="d970b-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d970b-115">IVR または MoH に接続した同時通話</span><span class="sxs-lookup"><span data-stu-id="d970b-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="d970b-116">480</span><span class="sxs-lookup"><span data-stu-id="d970b-116">480</span></span></p></td>
<td><p><span data-ttu-id="d970b-117">60</span><span class="sxs-lookup"><span data-stu-id="d970b-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d970b-118">匿名の同時セッション (IM なし)</span><span class="sxs-lookup"><span data-stu-id="d970b-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="d970b-119">224</span><span class="sxs-lookup"><span data-stu-id="d970b-119">224</span></span></p></td>
<td><p><span data-ttu-id="d970b-120">日</span><span class="sxs-lookup"><span data-stu-id="d970b-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d970b-121">匿名の同時セッション (IM あり)</span><span class="sxs-lookup"><span data-stu-id="d970b-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="d970b-122">64</span><span class="sxs-lookup"><span data-stu-id="d970b-122">64</span></span></p></td>
<td><p><span data-ttu-id="d970b-123">個</span><span class="sxs-lookup"><span data-stu-id="d970b-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d970b-124">アクティブ エージェント (公式および非公式)</span><span class="sxs-lookup"><span data-stu-id="d970b-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="d970b-125">1200</span><span class="sxs-lookup"><span data-stu-id="d970b-125">1200</span></span></p></td>
<td><p><span data-ttu-id="d970b-126">1200</span><span class="sxs-lookup"><span data-stu-id="d970b-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d970b-127">ハント グループ数</span><span class="sxs-lookup"><span data-stu-id="d970b-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="d970b-128">400</span><span class="sxs-lookup"><span data-stu-id="d970b-128">400</span></span></p></td>
<td><p><span data-ttu-id="d970b-129">400</span><span class="sxs-lookup"><span data-stu-id="d970b-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d970b-130">IVR グループ数 (音声認識を使用)</span><span class="sxs-lookup"><span data-stu-id="d970b-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="d970b-131">200</span><span class="sxs-lookup"><span data-stu-id="d970b-131">200</span></span></p></td>
<td><p><span data-ttu-id="d970b-132">200</span><span class="sxs-lookup"><span data-stu-id="d970b-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

