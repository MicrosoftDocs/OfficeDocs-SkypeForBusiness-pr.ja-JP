---
title: 'Lync Server 2013: Subnet テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Subnet table
ms:assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398582(v=OCS.15)
ms:contentKeyID: 48184544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cdf1ded3a63d790db78476b91a458d07921200a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="subnet-table-in-lync-server-2013"></a><span data-ttu-id="eedad-102">Lync Server 2013 のサブネットテーブル</span><span class="sxs-lookup"><span data-stu-id="eedad-102">Subnet table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eedad-103">_**トピックの最終更新日:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="eedad-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="eedad-p101">Subnet テーブルは、サポート テーブルです。それぞれのレコードは、ネットワーク構成の設定で定義された 1 つのサブネットを表します。</span><span class="sxs-lookup"><span data-stu-id="eedad-p101">The Subnet table is a supporting table. Each record represents one subnet defined in network configuration setting.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eedad-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="eedad-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="eedad-107"><strong>データ型</strong></span><span class="sxs-lookup"><span data-stu-id="eedad-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="eedad-108"><strong>キー/インデックス</strong></span><span class="sxs-lookup"><span data-stu-id="eedad-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="eedad-109"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="eedad-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eedad-110"><strong>SubnetIP</strong></span><span class="sxs-lookup"><span data-stu-id="eedad-110"><strong>SubnetIP</strong></span></span></p></td>
<td><p><span data-ttu-id="eedad-111">int</span><span class="sxs-lookup"><span data-stu-id="eedad-111">int</span></span></p></td>
<td><p><span data-ttu-id="eedad-112">主/プライマリ、外部</span><span class="sxs-lookup"><span data-stu-id="eedad-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="eedad-113">サブネット IP の整数表現。</span><span class="sxs-lookup"><span data-stu-id="eedad-113">Integer representation for the subnet IP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedad-114"><strong>マスク</strong></span><span class="sxs-lookup"><span data-stu-id="eedad-114"><strong>SubnetMask</strong></span></span></p></td>
<td><p><span data-ttu-id="eedad-115">int</span><span class="sxs-lookup"><span data-stu-id="eedad-115">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedad-116">サブネット マスク。</span><span class="sxs-lookup"><span data-stu-id="eedad-116">Subnet mask.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eedad-117"><strong>UserSiteKey</strong></span><span class="sxs-lookup"><span data-stu-id="eedad-117"><strong>UserSiteKey</strong></span></span></p></td>
<td><p><span data-ttu-id="eedad-118">int</span><span class="sxs-lookup"><span data-stu-id="eedad-118">int</span></span></p></td>
<td><p><span data-ttu-id="eedad-119">外部</span><span class="sxs-lookup"><span data-stu-id="eedad-119">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eedad-120"><a href="lync-server-2013-usersite-table.md">Lync Server 2013 の Usersite テーブル</a>から参照されます。</span><span class="sxs-lookup"><span data-stu-id="eedad-120">Referenced from the <a href="lync-server-2013-usersite-table.md">UserSite table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eedad-121"><strong>サブネットの説明</strong></span><span class="sxs-lookup"><span data-stu-id="eedad-121"><strong>SubnetDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="eedad-122">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="eedad-122">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eedad-123">サブネットの説明。</span><span class="sxs-lookup"><span data-stu-id="eedad-123">The description for the subnet.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

