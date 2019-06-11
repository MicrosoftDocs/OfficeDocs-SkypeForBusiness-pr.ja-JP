---
title: 'Lync Server 2013: tblComplianceFanout'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6edae4c6e37f5abb6714e7c6863c80b7a6e7756b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848600"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="5214b-102">Lync Server 2013 内の tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="5214b-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5214b-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5214b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5214b-104">tblComplianceFanout には、コンプライアンスイベントを処理したすべてのサーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5214b-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="5214b-105">行</span><span class="sxs-lookup"><span data-stu-id="5214b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5214b-106">列</span><span class="sxs-lookup"><span data-stu-id="5214b-106">Column</span></span></th>
<th><span data-ttu-id="5214b-107">型</span><span class="sxs-lookup"><span data-stu-id="5214b-107">Type</span></span></th>
<th><span data-ttu-id="5214b-108">説明</span><span class="sxs-lookup"><span data-stu-id="5214b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5214b-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="5214b-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="5214b-110">int</span><span class="sxs-lookup"><span data-stu-id="5214b-110">int</span></span></p></td>
<td><p><span data-ttu-id="5214b-111">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="5214b-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5214b-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="5214b-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="5214b-113">int</span><span class="sxs-lookup"><span data-stu-id="5214b-113">int</span></span></p></td>
<td><p><span data-ttu-id="5214b-114">サーバー id (serverID テーブルに対応する tblServerIdentity)。</span><span class="sxs-lookup"><span data-stu-id="5214b-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5214b-115">キー</span><span class="sxs-lookup"><span data-stu-id="5214b-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5214b-116">列</span><span class="sxs-lookup"><span data-stu-id="5214b-116">Column</span></span></th>
<th><span data-ttu-id="5214b-117">説明</span><span class="sxs-lookup"><span data-stu-id="5214b-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5214b-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="5214b-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="5214b-119">TblComplianceData Pleventid テーブルで参照する外部キー。</span><span class="sxs-lookup"><span data-stu-id="5214b-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

