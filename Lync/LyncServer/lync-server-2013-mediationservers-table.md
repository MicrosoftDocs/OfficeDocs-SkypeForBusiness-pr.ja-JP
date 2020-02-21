---
title: 'Lync Server 2013: MediationServers テーブル'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediationServers table
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48184929
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e932163610b88a51352c1f97e2d0b8d9c773d2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediationservers-table-in-lync-server-2013"></a><span data-ttu-id="82cd1-102">Lync Server 2013 の MediationServers テーブル</span><span class="sxs-lookup"><span data-stu-id="82cd1-102">MediationServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82cd1-103">_**トピックの最終更新日:** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="82cd1-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="82cd1-104">MediationServers テーブルは、サポートテーブルです。</span><span class="sxs-lookup"><span data-stu-id="82cd1-104">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="82cd1-105">各レコードには、データベース内のレコードを持つ呼び出しに関係する1つの仲介サーバーに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="82cd1-105">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82cd1-106">列</span><span class="sxs-lookup"><span data-stu-id="82cd1-106">Column</span></span></th>
<th><span data-ttu-id="82cd1-107">データ型</span><span class="sxs-lookup"><span data-stu-id="82cd1-107">Data Type</span></span></th>
<th><span data-ttu-id="82cd1-108">キー/インデックス</span><span class="sxs-lookup"><span data-stu-id="82cd1-108">Key/Index</span></span></th>
<th><span data-ttu-id="82cd1-109">詳細</span><span class="sxs-lookup"><span data-stu-id="82cd1-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82cd1-110"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="82cd1-110"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="82cd1-111">int</span><span class="sxs-lookup"><span data-stu-id="82cd1-111">int</span></span></p></td>
<td><p><span data-ttu-id="82cd1-112">Primary</span><span class="sxs-lookup"><span data-stu-id="82cd1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="82cd1-113">この仲介サーバーを識別する一意の番号。</span><span class="sxs-lookup"><span data-stu-id="82cd1-113">Unique number identifying this Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82cd1-114"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="82cd1-114"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="82cd1-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82cd1-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="82cd1-116">仲介サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="82cd1-116">Mediation Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

