---
title: 'Lync Server 2013: tblComplianceState'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 051f9929c7728db4b1e6e55b061098211bbc11ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="d6e7d-102">Lync Server 2013 の tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="d6e7d-102">tblComplianceState in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6e7d-103">_**トピックの最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="d6e7d-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="d6e7d-104">tblComplianceState には、プール全体のコンプライアンス状態情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d6e7d-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="d6e7d-105">Columns</span><span class="sxs-lookup"><span data-stu-id="d6e7d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6e7d-106">列</span><span class="sxs-lookup"><span data-stu-id="d6e7d-106">Column</span></span></th>
<th><span data-ttu-id="d6e7d-107">種類</span><span class="sxs-lookup"><span data-stu-id="d6e7d-107">Type</span></span></th>
<th><span data-ttu-id="d6e7d-108">説明</span><span class="sxs-lookup"><span data-stu-id="d6e7d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6e7d-109">Lastprocesseデの Tryid</span><span class="sxs-lookup"><span data-stu-id="d6e7d-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="d6e7d-110">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="d6e7d-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="d6e7d-111">最後に処理されたコンプライアンスイベントの ID。</span><span class="sxs-lookup"><span data-stu-id="d6e7d-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6e7d-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="d6e7d-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="d6e7d-113">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="d6e7d-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d6e7d-114">データベースの排他ロックを保持しているコンプライアンスサーバーの ID。存在しない場合は-1。</span><span class="sxs-lookup"><span data-stu-id="d6e7d-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6e7d-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="d6e7d-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="d6e7d-116">datetime2 (null 以外)</span><span class="sxs-lookup"><span data-stu-id="d6e7d-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="d6e7d-117">ロックの有効期限の時刻 (activeServerID が-1 でない場合)。</span><span class="sxs-lookup"><span data-stu-id="d6e7d-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

