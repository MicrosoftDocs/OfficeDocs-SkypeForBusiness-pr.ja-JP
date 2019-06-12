---
title: 'Lync Server 2013: tblLastChatId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddc89952b544a71c469538cf11f65658e19e38d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a><span data-ttu-id="48694-102">Lync Server 2013 の tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="48694-102">tblLastChatId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48694-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="48694-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="48694-104">tblLastChatId には、各ユーザーに対して生成された (tblChat テーブルで使用された) 最後のチャット ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="48694-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="48694-105">行</span><span class="sxs-lookup"><span data-stu-id="48694-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48694-106">列</span><span class="sxs-lookup"><span data-stu-id="48694-106">Column</span></span></th>
<th><span data-ttu-id="48694-107">型</span><span class="sxs-lookup"><span data-stu-id="48694-107">Type</span></span></th>
<th><span data-ttu-id="48694-108">説明</span><span class="sxs-lookup"><span data-stu-id="48694-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48694-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="48694-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="48694-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="48694-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="48694-111">ノード ID (チャットルームの種類のみ)。</span><span class="sxs-lookup"><span data-stu-id="48694-111">Node ID (chat room-type only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48694-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="48694-112">lastChatID</span></span></p></td>
<td><p><span data-ttu-id="48694-113">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="48694-113">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="48694-114">最後に使用されたチャット ID。</span><span class="sxs-lookup"><span data-stu-id="48694-114">Last used chat ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="48694-115">機能</span><span class="sxs-lookup"><span data-stu-id="48694-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48694-116">列</span><span class="sxs-lookup"><span data-stu-id="48694-116">Column</span></span></th>
<th><span data-ttu-id="48694-117">説明</span><span class="sxs-lookup"><span data-stu-id="48694-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48694-118">&lt;nodeID、lastChatID&gt;</span><span class="sxs-lookup"><span data-stu-id="48694-118">&lt;nodeID, lastChatID&gt;</span></span></p></td>
<td><p><span data-ttu-id="48694-119">主キー (nodeID だけが処理に十分な場合)。</span><span class="sxs-lookup"><span data-stu-id="48694-119">Primary key (just nodeID is sufficient for processing).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48694-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="48694-120">nodeID</span></span></p></td>
<td><p><span data-ttu-id="48694-121">TblNode テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="48694-121">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="48694-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="48694-122">See Also</span></span>


[<span data-ttu-id="48694-123">Lync Server 2013 の tblChat</span><span class="sxs-lookup"><span data-stu-id="48694-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

