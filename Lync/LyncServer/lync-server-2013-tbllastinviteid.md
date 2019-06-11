---
title: 'Lync Server 2013: tblLastInviteId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be882798a620933af28c7e6697a388ef01817e5a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="83e7a-102">Lync Server 2013 の tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="83e7a-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83e7a-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="83e7a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="83e7a-104">tblLastInviteId には、各ユーザーに対して生成された (tblPrincipalInvites テーブルで使用された) 最後の招待 ID が含まれます。</span><span class="sxs-lookup"><span data-stu-id="83e7a-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="83e7a-105">行</span><span class="sxs-lookup"><span data-stu-id="83e7a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83e7a-106">列</span><span class="sxs-lookup"><span data-stu-id="83e7a-106">Column</span></span></th>
<th><span data-ttu-id="83e7a-107">型</span><span class="sxs-lookup"><span data-stu-id="83e7a-107">Type</span></span></th>
<th><span data-ttu-id="83e7a-108">説明</span><span class="sxs-lookup"><span data-stu-id="83e7a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83e7a-109">prinID</span><span class="sxs-lookup"><span data-stu-id="83e7a-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="83e7a-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="83e7a-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="83e7a-111">プリンシパル ID。</span><span class="sxs-lookup"><span data-stu-id="83e7a-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e7a-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="83e7a-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="83e7a-113">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="83e7a-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="83e7a-114">最後に使用した招待の ID。</span><span class="sxs-lookup"><span data-stu-id="83e7a-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="83e7a-115">機能</span><span class="sxs-lookup"><span data-stu-id="83e7a-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83e7a-116">列</span><span class="sxs-lookup"><span data-stu-id="83e7a-116">Column</span></span></th>
<th><span data-ttu-id="83e7a-117">説明</span><span class="sxs-lookup"><span data-stu-id="83e7a-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83e7a-118">prinID</span><span class="sxs-lookup"><span data-stu-id="83e7a-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="83e7a-119">主キー。</span><span class="sxs-lookup"><span data-stu-id="83e7a-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83e7a-120">prinID</span><span class="sxs-lookup"><span data-stu-id="83e7a-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="83e7a-121">TblPrincipal Id テーブルで参照される外部キー。</span><span class="sxs-lookup"><span data-stu-id="83e7a-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="83e7a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="83e7a-122">See Also</span></span>


[<span data-ttu-id="83e7a-123">Lync Server 2013 の tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="83e7a-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

