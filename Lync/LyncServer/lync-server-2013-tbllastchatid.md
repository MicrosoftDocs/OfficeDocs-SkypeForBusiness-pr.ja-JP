---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 542b9f2006572edab4c9ca0adb29836174bc7aa7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="d458e-102">Lync Server 2013 の tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="d458e-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d458e-103">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d458e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d458e-104">tblLastChatId には、各ユーザーに対して生成された (および tblChat テーブルで使用された) 最後のチャット ID が格納されます。</span><span class="sxs-lookup"><span data-stu-id="d458e-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="d458e-105">Columns</span><span class="sxs-lookup"><span data-stu-id="d458e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d458e-106">列</span><span class="sxs-lookup"><span data-stu-id="d458e-106">Column</span></span></th>
<th><span data-ttu-id="d458e-107">種類</span><span class="sxs-lookup"><span data-stu-id="d458e-107">Type</span></span></th>
<th><span data-ttu-id="d458e-108">説明</span><span class="sxs-lookup"><span data-stu-id="d458e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d458e-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="d458e-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d458e-110">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="d458e-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d458e-111">ノード ID (チャット ルーム種類のみ)。</span><span class="sxs-lookup"><span data-stu-id="d458e-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d458e-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="d458e-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="d458e-113">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="d458e-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="d458e-114">最後に使用されたチャット ID。</span><span class="sxs-lookup"><span data-stu-id="d458e-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d458e-115">Keys</span><span class="sxs-lookup"><span data-stu-id="d458e-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d458e-116">列</span><span class="sxs-lookup"><span data-stu-id="d458e-116">Column</span></span></th>
<th><span data-ttu-id="d458e-117">説明</span><span class="sxs-lookup"><span data-stu-id="d458e-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d458e-118">&lt;nodeID、lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="d458e-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d458e-119">主キー (処理には nodeID のみで十分)。</span><span class="sxs-lookup"><span data-stu-id="d458e-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d458e-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="d458e-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="d458e-121">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="d458e-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="d458e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d458e-122">See Also</span></span>


[<span data-ttu-id="d458e-123">Lync Server 2013 の tblChat</span><span class="sxs-lookup"><span data-stu-id="d458e-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

