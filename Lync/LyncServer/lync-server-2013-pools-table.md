---
title: 'Lync Server 2013: プールテーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Pools table
ms:assetid: e0632b8d-e23a-4365-8a7a-6ca0957a46a9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398991(v=OCS.15)
ms:contentKeyID: 48185680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 207836c1ead0a6c5b74975cb3cc26484eb3181d0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pools-table-in-lync-server-2013"></a><span data-ttu-id="a8fbb-102">Lync Server 2013 のプールテーブル</span><span class="sxs-lookup"><span data-stu-id="a8fbb-102">Pools table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8fbb-103">_**トピックの最終更新日:** 2010-11-09_</span><span class="sxs-lookup"><span data-stu-id="a8fbb-103">_**Topic Last Modified:** 2010-11-09_</span></span>

<span data-ttu-id="a8fbb-104">プールテーブルは、さまざまなプールに関する情報を格納するサポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="a8fbb-104">The Pools table is a supporting table that stores information about the various pool.</span></span> <span data-ttu-id="a8fbb-105">このテーブル内の各レコードは、1 つのプールを表しています。</span><span class="sxs-lookup"><span data-stu-id="a8fbb-105">Each record in the table represents one pool.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8fbb-106">列</span><span class="sxs-lookup"><span data-stu-id="a8fbb-106">Column</span></span></th>
<th><span data-ttu-id="a8fbb-107">データ型</span><span class="sxs-lookup"><span data-stu-id="a8fbb-107">Data Type</span></span></th>
<th><span data-ttu-id="a8fbb-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="a8fbb-108">Key/Index</span></span></th>
<th><span data-ttu-id="a8fbb-109">詳細</span><span class="sxs-lookup"><span data-stu-id="a8fbb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8fbb-110"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="a8fbb-110"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="a8fbb-111">int</span><span class="sxs-lookup"><span data-stu-id="a8fbb-111">int</span></span></p></td>
<td><p><span data-ttu-id="a8fbb-112">Primary</span><span class="sxs-lookup"><span data-stu-id="a8fbb-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a8fbb-113">このプールを示す一意の番号です。</span><span class="sxs-lookup"><span data-stu-id="a8fbb-113">Unique number identifying this pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8fbb-114"><strong>PoolFQDN</strong></span><span class="sxs-lookup"><span data-stu-id="a8fbb-114"><strong>PoolFQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="a8fbb-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a8fbb-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a8fbb-116">プールの FQDN です。</span><span class="sxs-lookup"><span data-stu-id="a8fbb-116">Pool FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

