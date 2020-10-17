---
title: 'Lync Server 2013: tblLastChatId'
description: 'Lync Server 2013: tblLastChatId。'
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
ms.openlocfilehash: 69e80a735e70c8a03441038f5e58eb93e0af1f82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547603"
---
# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="764d8-103">Lync Server 2013 の tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="764d8-103">tblLastChatId in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="764d8-104">_**トピックの最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="764d8-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="764d8-105">tblLastChatId には、各ユーザーに対して生成された (および tblChat テーブルで使用された) 最後のチャット ID が格納されます。</span><span class="sxs-lookup"><span data-stu-id="764d8-105">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="764d8-106">段組み</span><span class="sxs-lookup"><span data-stu-id="764d8-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="764d8-107">Column</span><span class="sxs-lookup"><span data-stu-id="764d8-107">Column</span></span></th>
<th><span data-ttu-id="764d8-108">種類</span><span class="sxs-lookup"><span data-stu-id="764d8-108">Type</span></span></th>
<th><span data-ttu-id="764d8-109">説明</span><span class="sxs-lookup"><span data-stu-id="764d8-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="764d8-110">nodeID</span><span class="sxs-lookup"><span data-stu-id="764d8-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="764d8-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="764d8-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="764d8-112">ノード ID (チャット ルーム種類のみ)。</span><span class="sxs-lookup"><span data-stu-id="764d8-112">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="764d8-113">lastChatID</span><span class="sxs-lookup"><span data-stu-id="764d8-113">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="764d8-114">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="764d8-114">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="764d8-115">最後に使用されたチャット ID。</span><span class="sxs-lookup"><span data-stu-id="764d8-115">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="764d8-116">Keys</span><span class="sxs-lookup"><span data-stu-id="764d8-116">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="764d8-117">列</span><span class="sxs-lookup"><span data-stu-id="764d8-117">Column</span></span></th>
<th><span data-ttu-id="764d8-118">説明</span><span class="sxs-lookup"><span data-stu-id="764d8-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="764d8-119">&lt;nodeID、lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="764d8-119">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="764d8-120">主キー (処理には nodeID のみで十分)。</span><span class="sxs-lookup"><span data-stu-id="764d8-120">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="764d8-121">nodeID</span><span class="sxs-lookup"><span data-stu-id="764d8-121">nodeID</span></span></p></td>
<td><p><span data-ttu-id="764d8-122">tblNode.nodeID テーブル内の参照による外部キー。</span><span class="sxs-lookup"><span data-stu-id="764d8-122">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="764d8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="764d8-123">See Also</span></span>


[<span data-ttu-id="764d8-124">Lync Server 2013 の tblChat</span><span class="sxs-lookup"><span data-stu-id="764d8-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

