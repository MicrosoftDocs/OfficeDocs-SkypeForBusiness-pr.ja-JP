---
title: 'Lync Server 2013: DeRegisterType テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97d25ded1a281df0774644cd0d69f5e12d9c85a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="ba7c9-102">Lync Server 2013 の DeRegisterType テーブル</span><span class="sxs-lookup"><span data-stu-id="ba7c9-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba7c9-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ba7c9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ba7c9-104">DeRegisterType テーブルは、可能なユーザーのレジスタ型 ("クライアントで開始された"、"登録の期限切れ"、または "クライアントが応答を停止しました" など) の一覧を格納する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="ba7c9-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba7c9-105">列</span><span class="sxs-lookup"><span data-stu-id="ba7c9-105">Column</span></span></th>
<th><span data-ttu-id="ba7c9-106">データ型</span><span class="sxs-lookup"><span data-stu-id="ba7c9-106">Data Type</span></span></th>
<th><span data-ttu-id="ba7c9-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="ba7c9-107">Key/Index</span></span></th>
<th><span data-ttu-id="ba7c9-108">詳細</span><span class="sxs-lookup"><span data-stu-id="ba7c9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba7c9-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ba7c9-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ba7c9-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="ba7c9-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ba7c9-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ba7c9-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba7c9-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="ba7c9-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="ba7c9-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ba7c9-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ba7c9-114">許可される値:</span><span class="sxs-lookup"><span data-stu-id="ba7c9-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba7c9-115">0--不明</span><span class="sxs-lookup"><span data-stu-id="ba7c9-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="ba7c9-116">1--クライアントが開始した登録解除</span><span class="sxs-lookup"><span data-stu-id="ba7c9-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="ba7c9-117">2--登録が期限切れになりました</span><span class="sxs-lookup"><span data-stu-id="ba7c9-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="ba7c9-118">3–クライアントがクラッシュした</span><span class="sxs-lookup"><span data-stu-id="ba7c9-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="ba7c9-119">4--ユーザー属性が変更されました</span><span class="sxs-lookup"><span data-stu-id="ba7c9-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="ba7c9-120">5-優先レジストラーが変更されました</span><span class="sxs-lookup"><span data-stu-id="ba7c9-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="ba7c9-121">6--サバイバルモードでのレガシークライアント</span><span class="sxs-lookup"><span data-stu-id="ba7c9-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

