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
ms.openlocfilehash: 61824b09d1c36aec876ef81762205c81c7f1300d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="42141-102">Lync Server 2013 の tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="42141-102">tblComplianceState in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42141-103">_**最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="42141-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="42141-104">tblComplianceState には、プール全体のコンプライアンスの状態に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="42141-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="42141-105">行</span><span class="sxs-lookup"><span data-stu-id="42141-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42141-106">列</span><span class="sxs-lookup"><span data-stu-id="42141-106">Column</span></span></th>
<th><span data-ttu-id="42141-107">型</span><span class="sxs-lookup"><span data-stu-id="42141-107">Type</span></span></th>
<th><span data-ttu-id="42141-108">説明</span><span class="sxs-lookup"><span data-stu-id="42141-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42141-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="42141-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="42141-110">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="42141-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="42141-111">最新の処理済みのコンプライアンスイベントの ID です。</span><span class="sxs-lookup"><span data-stu-id="42141-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42141-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="42141-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="42141-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="42141-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="42141-114">データベースの排他ロックを保持しているコンプライアンスサーバーの ID。または、なしの場合は-1。</span><span class="sxs-lookup"><span data-stu-id="42141-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42141-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="42141-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="42141-116">datetime2、null ではない</span><span class="sxs-lookup"><span data-stu-id="42141-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="42141-117">有効期限をロックします (activeServerID が-1 でない場合)。</span><span class="sxs-lookup"><span data-stu-id="42141-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

