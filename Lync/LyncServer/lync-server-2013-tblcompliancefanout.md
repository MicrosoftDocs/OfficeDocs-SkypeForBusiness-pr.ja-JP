---
title: 'Lync Server 2013: tblComplianceFanout'
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
ms.openlocfilehash: 283918b723d92aa138f1e8572665e4ef4920abdc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="34daf-102">Lync Server 2013 の tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="34daf-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34daf-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="34daf-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="34daf-104">tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34daf-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="34daf-105">Columns</span><span class="sxs-lookup"><span data-stu-id="34daf-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34daf-106">列</span><span class="sxs-lookup"><span data-stu-id="34daf-106">Column</span></span></th>
<th><span data-ttu-id="34daf-107">種類</span><span class="sxs-lookup"><span data-stu-id="34daf-107">Type</span></span></th>
<th><span data-ttu-id="34daf-108">説明</span><span class="sxs-lookup"><span data-stu-id="34daf-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34daf-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="34daf-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="34daf-110">int</span><span class="sxs-lookup"><span data-stu-id="34daf-110">int</span></span></p></td>
<td><p><span data-ttu-id="34daf-111">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="34daf-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34daf-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="34daf-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="34daf-113">int</span><span class="sxs-lookup"><span data-stu-id="34daf-113">int</span></span></p></td>
<td><p><span data-ttu-id="34daf-114">サーバー id (tblServerIdentity テーブルに対応)。</span><span class="sxs-lookup"><span data-stu-id="34daf-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="34daf-115">キー</span><span class="sxs-lookup"><span data-stu-id="34daf-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34daf-116">列</span><span class="sxs-lookup"><span data-stu-id="34daf-116">Column</span></span></th>
<th><span data-ttu-id="34daf-117">説明</span><span class="sxs-lookup"><span data-stu-id="34daf-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34daf-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="34daf-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="34daf-119">TblComplianceData の参照が含まれている外部キー。</span><span class="sxs-lookup"><span data-stu-id="34daf-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

