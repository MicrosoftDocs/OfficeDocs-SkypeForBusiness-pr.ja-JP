---
title: Lync Server 2013 の拡張性
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
ms.openlocfilehash: 3bd340d46855f01e8ff43dc9f66b527e5df1967c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="77baf-102">Lync Server 2013 を使用したスケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="77baf-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77baf-103">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="77baf-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="77baf-104">Lync Server は、Enterprise Edition と Standard Edition という2つのエディションで提供されています。</span><span class="sxs-lookup"><span data-stu-id="77baf-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="77baf-105">これらのエディションでは、基本的に対象とする組織の規模が異なります。</span><span class="sxs-lookup"><span data-stu-id="77baf-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="77baf-106">以下の表で示すとおり、両方のエディションとも、すべてのワークロードで高可用性と障害復旧以外のすべての機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="77baf-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77baf-107">機能</span><span class="sxs-lookup"><span data-stu-id="77baf-107">Feature</span></span></th>
<th><span data-ttu-id="77baf-108">Enterprise Edition でのサポートの有無</span><span class="sxs-lookup"><span data-stu-id="77baf-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="77baf-109">Standard Edition でのサポートの有無</span><span class="sxs-lookup"><span data-stu-id="77baf-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77baf-110">インスタント メッセージング (IM) およびプレゼンス</span><span class="sxs-lookup"><span data-stu-id="77baf-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="77baf-111">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="77baf-112">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77baf-113">会議</span><span class="sxs-lookup"><span data-stu-id="77baf-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="77baf-114">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="77baf-115">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77baf-116">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="77baf-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="77baf-117">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="77baf-118">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77baf-119">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="77baf-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="77baf-120">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="77baf-121">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77baf-122">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="77baf-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="77baf-123">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="77baf-124">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77baf-125">仮想化</span><span class="sxs-lookup"><span data-stu-id="77baf-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="77baf-126">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="77baf-127">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77baf-128">高可用性、フェールオーバー、および障害復旧</span><span class="sxs-lookup"><span data-stu-id="77baf-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="77baf-129">はい</span><span class="sxs-lookup"><span data-stu-id="77baf-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="77baf-130">なし</span><span class="sxs-lookup"><span data-stu-id="77baf-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

