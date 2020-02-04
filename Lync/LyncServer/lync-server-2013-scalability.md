---
title: Lync Server 2013 のスケーラビリティ
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
ms.openlocfilehash: e6ff4828bdfddbfca7734836fdfdbe24f0b90c4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="50b6d-102">Lync Server 2013 のスケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="50b6d-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50b6d-103">_**最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="50b6d-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="50b6d-104">Lync Server は、Enterprise Edition と Standard Edition の2つのエディションで提供されています。</span><span class="sxs-lookup"><span data-stu-id="50b6d-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="50b6d-105">さまざまなエディションは、主にさまざまな規模の組織向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="50b6d-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="50b6d-106">次の表に示すように、両方のエディションでは、高可用性と障害回復を除き、すべてのワークロードのすべての機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50b6d-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50b6d-107">機能</span><span class="sxs-lookup"><span data-stu-id="50b6d-107">Feature</span></span></th>
<th><span data-ttu-id="50b6d-108">Enterprise Edition でサポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="50b6d-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="50b6d-109">Standard Edition でサポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="50b6d-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50b6d-110">インスタントメッセージング (IM) とプレゼンス</span><span class="sxs-lookup"><span data-stu-id="50b6d-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="50b6d-111">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="50b6d-112">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50b6d-113">会議</span><span class="sxs-lookup"><span data-stu-id="50b6d-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="50b6d-114">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="50b6d-115">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50b6d-116">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="50b6d-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="50b6d-117">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="50b6d-118">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50b6d-119">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="50b6d-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="50b6d-120">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="50b6d-121">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50b6d-122">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="50b6d-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="50b6d-123">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="50b6d-124">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50b6d-125">仮想化</span><span class="sxs-lookup"><span data-stu-id="50b6d-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="50b6d-126">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="50b6d-127">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50b6d-128">高可用性、フェールオーバー、および障害回復</span><span class="sxs-lookup"><span data-stu-id="50b6d-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="50b6d-129">はい</span><span class="sxs-lookup"><span data-stu-id="50b6d-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="50b6d-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="50b6d-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

