---
title: 'Lync Server 2013: テナントテーブル'
description: 'Lync Server 2013: テナントテーブル。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96025dfd9fb42a6083f7f3daca98e243f01a8516
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568533"
---
# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="26a77-103">Lync Server 2013 のテナントテーブル</span><span class="sxs-lookup"><span data-stu-id="26a77-103">Tenants table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26a77-104">_**トピックの最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="26a77-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="26a77-p101">Tenants テーブルは、各種テナントの一覧を格納しているサポート テーブルです。テーブル内の各レコードが 1 つのテナントを表します。</span><span class="sxs-lookup"><span data-stu-id="26a77-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26a77-107">内部設置型展開では、CDR は組み込みのテナント ID を使用して、パブリック IM 接続、フェデレーション、匿名など、さまざまな認証の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="26a77-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26a77-108">Column</span><span class="sxs-lookup"><span data-stu-id="26a77-108">Column</span></span></th>
<th><span data-ttu-id="26a77-109">データ型</span><span class="sxs-lookup"><span data-stu-id="26a77-109">Data Type</span></span></th>
<th><span data-ttu-id="26a77-110">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="26a77-110">Key/Index</span></span></th>
<th><span data-ttu-id="26a77-111">詳細</span><span class="sxs-lookup"><span data-stu-id="26a77-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26a77-112"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="26a77-112"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="26a77-113">int</span><span class="sxs-lookup"><span data-stu-id="26a77-113">int</span></span></p></td>
<td><p><span data-ttu-id="26a77-114">Primary</span><span class="sxs-lookup"><span data-stu-id="26a77-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="26a77-115">このテナント ID を識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="26a77-115">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26a77-116"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="26a77-116"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="26a77-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="26a77-117">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="26a77-118">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="26a77-118">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="26a77-119">00000000-0000-0000-0000-000000000000 – エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="26a77-119">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="26a77-120">00000000-0000-0000-0000-000000000001 – フェデレーション</span><span class="sxs-lookup"><span data-stu-id="26a77-120">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="26a77-121">00000000-0000-0000-0000-000000000002 – 匿名</span><span class="sxs-lookup"><span data-stu-id="26a77-121">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="26a77-122">00000000-0000-0000-0000-000000000003 – パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="26a77-122">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

