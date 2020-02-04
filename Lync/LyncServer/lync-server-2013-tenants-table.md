---
title: 'Lync Server 2013: Tenants テーブル'
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
ms.openlocfilehash: de776adeb8c280c5216b35cc8236a0834c14aa13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="a4eb0-102">Lync Server 2013 の Tenants テーブル</span><span class="sxs-lookup"><span data-stu-id="a4eb0-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4eb0-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a4eb0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a4eb0-104">テナントの表は、さまざまなテナントの一覧を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="a4eb0-104">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="a4eb0-105">テーブル内の各レコードは、1つのテナントを表します。</span><span class="sxs-lookup"><span data-stu-id="a4eb0-105">Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a4eb0-106">オンプレミスの展開では、CDR はビルトインのテナント ID を使用して、パブリック IM 接続、フェデレーション、匿名など、さまざまな認証の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="a4eb0-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



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
<th><span data-ttu-id="a4eb0-107">列</span><span class="sxs-lookup"><span data-stu-id="a4eb0-107">Column</span></span></th>
<th><span data-ttu-id="a4eb0-108">データ型</span><span class="sxs-lookup"><span data-stu-id="a4eb0-108">Data Type</span></span></th>
<th><span data-ttu-id="a4eb0-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="a4eb0-109">Key/Index</span></span></th>
<th><span data-ttu-id="a4eb0-110">詳細</span><span class="sxs-lookup"><span data-stu-id="a4eb0-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4eb0-111"><strong>テナント</strong></span><span class="sxs-lookup"><span data-stu-id="a4eb0-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="a4eb0-112">int</span><span class="sxs-lookup"><span data-stu-id="a4eb0-112">int</span></span></p></td>
<td><p><span data-ttu-id="a4eb0-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a4eb0-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a4eb0-114">このテナント ID を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="a4eb0-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4eb0-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="a4eb0-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a4eb0-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a4eb0-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a4eb0-117">許可される値:</span><span class="sxs-lookup"><span data-stu-id="a4eb0-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a4eb0-118">00000000-0000-0000-0000-000000000000 – Enterprise</span><span class="sxs-lookup"><span data-stu-id="a4eb0-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="a4eb0-119">00000000-0000-0000-0000-000000000001 –フェデレーション</span><span class="sxs-lookup"><span data-stu-id="a4eb0-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="a4eb0-120">00000000-0000-0000-0000-000000000002 –匿名</span><span class="sxs-lookup"><span data-stu-id="a4eb0-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="a4eb0-121">00000000-0000-0000-0000-000000000003 –パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="a4eb0-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

