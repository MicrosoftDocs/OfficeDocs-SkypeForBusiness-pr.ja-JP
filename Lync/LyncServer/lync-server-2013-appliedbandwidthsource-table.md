---
title: 'Lync Server 2013: AppliedBandwidthSource テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f4c7d78353a60ad4c3bf9a7ff3efb363bd01c82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="afb6a-102">Lync Server 2013 の AppliedBandwidthSource テーブル</span><span class="sxs-lookup"><span data-stu-id="afb6a-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afb6a-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="afb6a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="afb6a-104">AppliedBandwidthSource テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="afb6a-104">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="afb6a-105">各レコードは1つのソースを表します。</span><span class="sxs-lookup"><span data-stu-id="afb6a-105">Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afb6a-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="afb6a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="afb6a-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="afb6a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="afb6a-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="afb6a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="afb6a-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="afb6a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afb6a-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="afb6a-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="afb6a-111">int</span><span class="sxs-lookup"><span data-stu-id="afb6a-111">int</span></span></p></td>
<td><p><span data-ttu-id="afb6a-112">Primary</span><span class="sxs-lookup"><span data-stu-id="afb6a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="afb6a-113">ソースを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="afb6a-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afb6a-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="afb6a-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="afb6a-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="afb6a-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="afb6a-116">一意</span><span class="sxs-lookup"><span data-stu-id="afb6a-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="afb6a-117">これは、適用される帯域幅の上限のソースです。</span><span class="sxs-lookup"><span data-stu-id="afb6a-117">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="afb6a-118">帯域幅の制限の対象となる場所 (たとえば、"Policy Server"、"TURN Server"、"モダリティ" など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="afb6a-118">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

