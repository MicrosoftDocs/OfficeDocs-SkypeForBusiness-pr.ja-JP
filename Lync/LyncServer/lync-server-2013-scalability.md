---
title: Lync Server 2013 の拡張性
description: Lync Server 2013 の拡張性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28cd5820755ffd1eb863ed6f2369b5756a7ae3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543793"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="9366b-103">Lync Server 2013 を使用したスケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="9366b-103">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9366b-104">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="9366b-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="9366b-105">Lync Server は、Enterprise Edition と Standard Edition という2つのエディションで提供されています。</span><span class="sxs-lookup"><span data-stu-id="9366b-105">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="9366b-106">これらのエディションでは、基本的に対象とする組織の規模が異なります。</span><span class="sxs-lookup"><span data-stu-id="9366b-106">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="9366b-107">以下の表で示すとおり、両方のエディションとも、すべてのワークロードで高可用性と障害復旧以外のすべての機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="9366b-107">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9366b-108">機能</span><span class="sxs-lookup"><span data-stu-id="9366b-108">Feature</span></span></th>
<th><span data-ttu-id="9366b-109">Enterprise Edition でのサポートの有無</span><span class="sxs-lookup"><span data-stu-id="9366b-109">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="9366b-110">Standard Edition でのサポートの有無</span><span class="sxs-lookup"><span data-stu-id="9366b-110">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9366b-111">インスタント メッセージング (IM) およびプレゼンス</span><span class="sxs-lookup"><span data-stu-id="9366b-111">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="9366b-112">はい</span><span class="sxs-lookup"><span data-stu-id="9366b-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="9366b-113">必要</span><span class="sxs-lookup"><span data-stu-id="9366b-113">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366b-114">会議</span><span class="sxs-lookup"><span data-stu-id="9366b-114">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="9366b-115">はい</span><span class="sxs-lookup"><span data-stu-id="9366b-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="9366b-116">必要</span><span class="sxs-lookup"><span data-stu-id="9366b-116">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366b-117">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="9366b-117">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="9366b-118">はい</span><span class="sxs-lookup"><span data-stu-id="9366b-118">Yes</span></span></p></td>
<td><p><span data-ttu-id="9366b-119">必要</span><span class="sxs-lookup"><span data-stu-id="9366b-119">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366b-120">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="9366b-120">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="9366b-121">はい</span><span class="sxs-lookup"><span data-stu-id="9366b-121">Yes</span></span></p></td>
<td><p><span data-ttu-id="9366b-122">必要</span><span class="sxs-lookup"><span data-stu-id="9366b-122">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366b-123">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="9366b-123">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="9366b-124">はい</span><span class="sxs-lookup"><span data-stu-id="9366b-124">Yes</span></span></p></td>
<td><p><span data-ttu-id="9366b-125">必要</span><span class="sxs-lookup"><span data-stu-id="9366b-125">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9366b-126">仮想化</span><span class="sxs-lookup"><span data-stu-id="9366b-126">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="9366b-127">はい</span><span class="sxs-lookup"><span data-stu-id="9366b-127">Yes</span></span></p></td>
<td><p><span data-ttu-id="9366b-128">必要</span><span class="sxs-lookup"><span data-stu-id="9366b-128">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9366b-129">高可用性、フェールオーバー、および障害復旧</span><span class="sxs-lookup"><span data-stu-id="9366b-129">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="9366b-130">必要</span><span class="sxs-lookup"><span data-stu-id="9366b-130">Yes</span></span></p></td>
<td><p><span data-ttu-id="9366b-131">なし</span><span class="sxs-lookup"><span data-stu-id="9366b-131">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

