---
title: 'Lync Server 2013: tblComplianceFanout'
description: 'Lync Server 2013: tblComplianceFanout。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cb94fff579c504598f027c8c68c7dde00a5a516
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568573"
---
# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="da14a-103">Lync Server 2013 の tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="da14a-103">tblComplianceFanout in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da14a-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="da14a-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="da14a-105">tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="da14a-105">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="da14a-106">段組み</span><span class="sxs-lookup"><span data-stu-id="da14a-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da14a-107">Column</span><span class="sxs-lookup"><span data-stu-id="da14a-107">Column</span></span></th>
<th><span data-ttu-id="da14a-108">種類</span><span class="sxs-lookup"><span data-stu-id="da14a-108">Type</span></span></th>
<th><span data-ttu-id="da14a-109">説明</span><span class="sxs-lookup"><span data-stu-id="da14a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da14a-110">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="da14a-110">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="da14a-111">int</span><span class="sxs-lookup"><span data-stu-id="da14a-111">int</span></span></p></td>
<td><p><span data-ttu-id="da14a-112">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="da14a-112">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da14a-113">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="da14a-113">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="da14a-114">int</span><span class="sxs-lookup"><span data-stu-id="da14a-114">int</span></span></p></td>
<td><p><span data-ttu-id="da14a-115">サーバー id (tblServerIdentity テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="da14a-115">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="da14a-116">キー</span><span class="sxs-lookup"><span data-stu-id="da14a-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da14a-117">列</span><span class="sxs-lookup"><span data-stu-id="da14a-117">Column</span></span></th>
<th><span data-ttu-id="da14a-118">説明</span><span class="sxs-lookup"><span data-stu-id="da14a-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da14a-119">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="da14a-119">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="da14a-120">TblComplianceData の参照が含まれている外部キー。</span><span class="sxs-lookup"><span data-stu-id="da14a-120">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

