---
title: 'Lync Server 2013: Tenants テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7da863aa2b713f874aba00f5a4f481f45fb79b3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="a0e08-102">Lync Server 2013 の Tenants テーブル</span><span class="sxs-lookup"><span data-stu-id="a0e08-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0e08-103">_**最終更新日:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a0e08-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a0e08-104">テナントの表は、さまざまなテナントの一覧を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="a0e08-104">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="a0e08-105">テーブル内の各レコードは、1つのテナントを表します。</span><span class="sxs-lookup"><span data-stu-id="a0e08-105">Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0e08-106">オンプレミスの展開では、CDR はビルトインのテナント ID を使用して、パブリック IM 接続、フェデレーション、匿名など、さまざまな認証の種類を示します。</span><span class="sxs-lookup"><span data-stu-id="a0e08-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



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
<th><span data-ttu-id="a0e08-107">列</span><span class="sxs-lookup"><span data-stu-id="a0e08-107">Column</span></span></th>
<th><span data-ttu-id="a0e08-108">データ型</span><span class="sxs-lookup"><span data-stu-id="a0e08-108">Data Type</span></span></th>
<th><span data-ttu-id="a0e08-109">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="a0e08-109">Key/Index</span></span></th>
<th><span data-ttu-id="a0e08-110">詳細</span><span class="sxs-lookup"><span data-stu-id="a0e08-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0e08-111"><strong>テナント</strong></span><span class="sxs-lookup"><span data-stu-id="a0e08-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="a0e08-112">int</span><span class="sxs-lookup"><span data-stu-id="a0e08-112">int</span></span></p></td>
<td><p><span data-ttu-id="a0e08-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a0e08-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a0e08-114">このテナント ID を識別する一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="a0e08-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0e08-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="a0e08-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a0e08-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a0e08-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a0e08-117">許可される値:</span><span class="sxs-lookup"><span data-stu-id="a0e08-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a0e08-118">00000000-0000-0000-0000-000000000000 – Enterprise</span><span class="sxs-lookup"><span data-stu-id="a0e08-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="a0e08-119">00000000-0000-0000-0000-000000000001 –フェデレーション</span><span class="sxs-lookup"><span data-stu-id="a0e08-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="a0e08-120">00000000-0000-0000-0000-000000000002 –匿名</span><span class="sxs-lookup"><span data-stu-id="a0e08-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="a0e08-121">00000000-0000-0000-0000-000000000003 –パブリック IM 接続</span><span class="sxs-lookup"><span data-stu-id="a0e08-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

