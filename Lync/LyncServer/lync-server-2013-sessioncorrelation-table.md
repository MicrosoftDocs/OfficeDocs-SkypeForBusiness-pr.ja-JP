---
title: 'Lync Server 2013: SessionCorrelation テーブル'
description: 'Lync Server 2013: SessionCorrelation テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814b7e8539d89f87e7df60ceb03e70800553fb55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579663"
---
# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="f0962-103">Lync Server 2013 の SessionCorrelation テーブル</span><span class="sxs-lookup"><span data-stu-id="f0962-103">SessionCorrelation table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0962-104">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f0962-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f0962-105">SessionCorrelation テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="f0962-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="f0962-106">各レコードは、複数のセッションを相互に関連付けるために使用される1つの CorrelationID を表します。</span><span class="sxs-lookup"><span data-stu-id="f0962-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0962-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="f0962-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f0962-108"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="f0962-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f0962-109"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="f0962-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f0962-110"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="f0962-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0962-111"><strong>チェックサム</strong></span><span class="sxs-lookup"><span data-stu-id="f0962-111"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="f0962-112">int</span><span class="sxs-lookup"><span data-stu-id="f0962-112">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0962-113"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="f0962-113"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f0962-114">int</span><span class="sxs-lookup"><span data-stu-id="f0962-114">int</span></span></p></td>
<td><p><span data-ttu-id="f0962-115">Primary</span><span class="sxs-lookup"><span data-stu-id="f0962-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0962-116">この音声ビデオ会議サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="f0962-116">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0962-117"><strong>CorrelationID</strong></span><span class="sxs-lookup"><span data-stu-id="f0962-117"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="f0962-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f0962-118">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f0962-119">一意</span><span class="sxs-lookup"><span data-stu-id="f0962-119">Unique</span></span></p></td>
<td><p><span data-ttu-id="f0962-120">関連付けられているセッションは、同じ関連付け ID を持ちます。</span><span class="sxs-lookup"><span data-stu-id="f0962-120">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0962-121"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f0962-121"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f0962-122">日付型</span><span class="sxs-lookup"><span data-stu-id="f0962-122">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0962-123">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="f0962-123">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

