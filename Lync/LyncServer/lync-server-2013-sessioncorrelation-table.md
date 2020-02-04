---
title: 'Lync Server 2013: SessionCorrelation テーブル'
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
ms.openlocfilehash: 6fe8deda7486d699073bf271953e382ac7b7c508
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="19519-102">Lync Server 2013 の SessionCorrelation テーブル</span><span class="sxs-lookup"><span data-stu-id="19519-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19519-103">_**最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="19519-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="19519-104">セッション相関関係テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="19519-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="19519-105">各レコードは、複数のセッションを関連付けるために使用される1つの CorrelationID を表します。</span><span class="sxs-lookup"><span data-stu-id="19519-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19519-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="19519-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="19519-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="19519-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="19519-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="19519-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="19519-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="19519-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19519-110"><strong>サム</strong></span><span class="sxs-lookup"><span data-stu-id="19519-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="19519-111">int</span><span class="sxs-lookup"><span data-stu-id="19519-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19519-112"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="19519-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="19519-113">int</span><span class="sxs-lookup"><span data-stu-id="19519-113">int</span></span></p></td>
<td><p><span data-ttu-id="19519-114">Primary</span><span class="sxs-lookup"><span data-stu-id="19519-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="19519-115">この A/V 会議サーバーを識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="19519-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19519-116"><strong>CorrelationID</strong></span><span class="sxs-lookup"><span data-stu-id="19519-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="19519-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="19519-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="19519-118">一意</span><span class="sxs-lookup"><span data-stu-id="19519-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="19519-119">関連付けられているセッションは、関連付け ID が同じになります。</span><span class="sxs-lookup"><span data-stu-id="19519-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19519-120"><strong>Nextupdatupdat</strong></span><span class="sxs-lookup"><span data-stu-id="19519-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="19519-121">datetime</span><span class="sxs-lookup"><span data-stu-id="19519-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="19519-122">内部使用のみ。</span><span class="sxs-lookup"><span data-stu-id="19519-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

