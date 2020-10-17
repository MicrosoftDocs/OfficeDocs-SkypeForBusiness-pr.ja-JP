---
title: 'Lync Server 2013: DeRegisterType テーブル'
description: 'Lync Server 2013: DeRegisterType テーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DeRegisterType table
ms:assetid: 09148118-6209-4fd7-a494-99118689a245
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398142(v=OCS.15)
ms:contentKeyID: 48183346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afad63c2abeba3e91565e07dac75d0ac6c96ca3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555353"
---
# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="82478-103">Lync Server 2013 の DeRegisterType テーブル</span><span class="sxs-lookup"><span data-stu-id="82478-103">DeRegisterType table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82478-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="82478-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="82478-105">DeRegisterType テーブルは、使用できるユーザー登録解除の種類 ("クライアント開始済み"、"登録期限切れ"、"クライアント停止済み" など) の一覧を格納する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="82478-105">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82478-106">Column</span><span class="sxs-lookup"><span data-stu-id="82478-106">Column</span></span></th>
<th><span data-ttu-id="82478-107">データ型</span><span class="sxs-lookup"><span data-stu-id="82478-107">Data Type</span></span></th>
<th><span data-ttu-id="82478-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="82478-108">Key/Index</span></span></th>
<th><span data-ttu-id="82478-109">詳細</span><span class="sxs-lookup"><span data-stu-id="82478-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82478-110"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="82478-110"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="82478-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="82478-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="82478-112">Primary</span><span class="sxs-lookup"><span data-stu-id="82478-112">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82478-113"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="82478-113"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="82478-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82478-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="82478-115">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82478-115">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="82478-116">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="82478-116">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="82478-117">1 -- クライアントが登録解除を開始済み</span><span class="sxs-lookup"><span data-stu-id="82478-117">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="82478-118">2 -- 登録期限切れ</span><span class="sxs-lookup"><span data-stu-id="82478-118">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="82478-119">3 – クライアントのクラッシュ</span><span class="sxs-lookup"><span data-stu-id="82478-119">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="82478-120">4 -- ユーザー属性変更</span><span class="sxs-lookup"><span data-stu-id="82478-120">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="82478-121">5 - 優先レジストラー変更</span><span class="sxs-lookup"><span data-stu-id="82478-121">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="82478-122">6 -- サバイバル モードのレガシ クライアント</span><span class="sxs-lookup"><span data-stu-id="82478-122">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

