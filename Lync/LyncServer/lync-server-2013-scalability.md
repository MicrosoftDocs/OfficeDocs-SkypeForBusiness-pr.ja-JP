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
ms.openlocfilehash: d2b26f8f7b7b254a8576a08e9b24fdeb2da633b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510964"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="b2f9f-102">Lync Server 2013 を使用したスケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="b2f9f-102">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2f9f-103">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="b2f9f-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="b2f9f-104">Lync Server は、Enterprise Edition と Standard Edition という2つのエディションで提供されています。</span><span class="sxs-lookup"><span data-stu-id="b2f9f-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="b2f9f-105">これらのエディションでは、基本的に対象とする組織の規模が異なります。</span><span class="sxs-lookup"><span data-stu-id="b2f9f-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="b2f9f-106">以下の表で示すとおり、両方のエディションとも、すべてのワークロードで高可用性と障害復旧以外のすべての機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="b2f9f-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2f9f-107">機能</span><span class="sxs-lookup"><span data-stu-id="b2f9f-107">Feature</span></span></th>
<th><span data-ttu-id="b2f9f-108">Enterprise Edition でのサポートの有無</span><span class="sxs-lookup"><span data-stu-id="b2f9f-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="b2f9f-109">Standard Edition でのサポートの有無</span><span class="sxs-lookup"><span data-stu-id="b2f9f-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2f9f-110">インスタント メッセージング (IM) およびプレゼンス</span><span class="sxs-lookup"><span data-stu-id="b2f9f-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-111">はい</span><span class="sxs-lookup"><span data-stu-id="b2f9f-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-112">必要</span><span class="sxs-lookup"><span data-stu-id="b2f9f-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2f9f-113">会議</span><span class="sxs-lookup"><span data-stu-id="b2f9f-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-114">はい</span><span class="sxs-lookup"><span data-stu-id="b2f9f-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-115">必要</span><span class="sxs-lookup"><span data-stu-id="b2f9f-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2f9f-116">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="b2f9f-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-117">はい</span><span class="sxs-lookup"><span data-stu-id="b2f9f-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-118">必要</span><span class="sxs-lookup"><span data-stu-id="b2f9f-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2f9f-119">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="b2f9f-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-120">はい</span><span class="sxs-lookup"><span data-stu-id="b2f9f-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-121">必要</span><span class="sxs-lookup"><span data-stu-id="b2f9f-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2f9f-122">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="b2f9f-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-123">はい</span><span class="sxs-lookup"><span data-stu-id="b2f9f-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-124">必要</span><span class="sxs-lookup"><span data-stu-id="b2f9f-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2f9f-125">仮想化</span><span class="sxs-lookup"><span data-stu-id="b2f9f-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-126">はい</span><span class="sxs-lookup"><span data-stu-id="b2f9f-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-127">必要</span><span class="sxs-lookup"><span data-stu-id="b2f9f-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2f9f-128">高可用性、フェールオーバー、および障害復旧</span><span class="sxs-lookup"><span data-stu-id="b2f9f-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-129">必要</span><span class="sxs-lookup"><span data-stu-id="b2f9f-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="b2f9f-130">なし</span><span class="sxs-lookup"><span data-stu-id="b2f9f-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

