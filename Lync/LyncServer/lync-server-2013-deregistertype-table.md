---
title: 'Lync Server 2013: DeRegisterType テーブル'
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
ms.openlocfilehash: 8c9198d0551375803e0b83b2ce62d44b0d3a266c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deregistertype-table-in-lync-server-2013"></a><span data-ttu-id="bc307-102">Lync Server 2013 の DeRegisterType テーブル</span><span class="sxs-lookup"><span data-stu-id="bc307-102">DeRegisterType table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc307-103">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bc307-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bc307-104">DeRegisterType テーブルは、使用できるユーザー登録解除の種類 ("クライアント開始済み"、"登録期限切れ"、"クライアント停止済み" など) の一覧を格納する静的テーブルです。</span><span class="sxs-lookup"><span data-stu-id="bc307-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as ‘client initiated’, ‘registration expired’, or ‘client stopped responding.’</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc307-105">列</span><span class="sxs-lookup"><span data-stu-id="bc307-105">Column</span></span></th>
<th><span data-ttu-id="bc307-106">データ型</span><span class="sxs-lookup"><span data-stu-id="bc307-106">Data Type</span></span></th>
<th><span data-ttu-id="bc307-107">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="bc307-107">Key/Index</span></span></th>
<th><span data-ttu-id="bc307-108">詳細</span><span class="sxs-lookup"><span data-stu-id="bc307-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc307-109"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="bc307-109"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="bc307-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="bc307-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="bc307-111">Primary</span><span class="sxs-lookup"><span data-stu-id="bc307-111">Primary</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc307-112"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="bc307-112"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="bc307-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bc307-113">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bc307-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bc307-114">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc307-115">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="bc307-115">0 -- Unknown</span></span></p></li>
<li><p><span data-ttu-id="bc307-116">1 -- クライアントが登録解除を開始済み</span><span class="sxs-lookup"><span data-stu-id="bc307-116">1 -- Client Initiated Deregistration</span></span></p></li>
<li><p><span data-ttu-id="bc307-117">2 -- 登録期限切れ</span><span class="sxs-lookup"><span data-stu-id="bc307-117">2 -- Registration Expired</span></span></p></li>
<li><p><span data-ttu-id="bc307-118">3 – クライアントのクラッシュ</span><span class="sxs-lookup"><span data-stu-id="bc307-118">3 – Client crashed</span></span></p></li>
<li><p><span data-ttu-id="bc307-119">4 -- ユーザー属性変更</span><span class="sxs-lookup"><span data-stu-id="bc307-119">4 -- User Attributes Changed</span></span></p></li>
<li><p><span data-ttu-id="bc307-120">5 - 優先レジストラー変更</span><span class="sxs-lookup"><span data-stu-id="bc307-120">5 – Preferred Registrar Changed</span></span></p></li>
<li><p><span data-ttu-id="bc307-121">6 -- サバイバル モードのレガシ クライアント</span><span class="sxs-lookup"><span data-stu-id="bc307-121">6 -- Legacy Client In Survival Mode</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

