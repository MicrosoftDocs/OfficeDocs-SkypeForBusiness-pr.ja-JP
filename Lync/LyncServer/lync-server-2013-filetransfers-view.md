---
title: 'Lync Server 2013: FileTransfers ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4469140f7f92c563a594c883d02f3add1e65c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="939ba-102">Lync Server 2013 の FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="939ba-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="939ba-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="939ba-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="939ba-104">FileTransfer ビューには、ピアツーピアファイル転送セッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="939ba-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="939ba-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="939ba-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="939ba-106">FileTransfers ビューには、 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の Sessiondetails ビュー</A>のすべての列に加えて、以下の列も含まれています。</span><span class="sxs-lookup"><span data-stu-id="939ba-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="939ba-107">列</span><span class="sxs-lookup"><span data-stu-id="939ba-107">Column</span></span></th>
<th><span data-ttu-id="939ba-108">データ型</span><span class="sxs-lookup"><span data-stu-id="939ba-108">Data Type</span></span></th>
<th><span data-ttu-id="939ba-109">詳細</span><span class="sxs-lookup"><span data-stu-id="939ba-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="939ba-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="939ba-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="939ba-111">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="939ba-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="939ba-112">転送されたファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="939ba-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939ba-113"><strong>クッキー</strong></span><span class="sxs-lookup"><span data-stu-id="939ba-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="939ba-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="939ba-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="939ba-115">すべてのフォローアップメッセージをこのメールに関連付けられているものとして識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="939ba-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939ba-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="939ba-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="939ba-117">長さ</span><span class="sxs-lookup"><span data-stu-id="939ba-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="939ba-118">同じファイル名を含むファイル転送を区別する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="939ba-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939ba-119"><strong>受諾</strong></span><span class="sxs-lookup"><span data-stu-id="939ba-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="939ba-120">bit</span><span class="sxs-lookup"><span data-stu-id="939ba-120">bit</span></span></p></td>
<td><p><span data-ttu-id="939ba-121">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="939ba-122">TRUE の場合は、拒否とキャンセルは NULL になります。</span><span class="sxs-lookup"><span data-stu-id="939ba-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939ba-123"><strong>拒否</strong></span><span class="sxs-lookup"><span data-stu-id="939ba-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="939ba-124">bit</span><span class="sxs-lookup"><span data-stu-id="939ba-124">bit</span></span></p></td>
<td><p><span data-ttu-id="939ba-125">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="939ba-126">TRUE の場合は、Accept と Cancel は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="939ba-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939ba-127"><strong>キャンセル</strong></span><span class="sxs-lookup"><span data-stu-id="939ba-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="939ba-128">bit</span><span class="sxs-lookup"><span data-stu-id="939ba-128">bit</span></span></p></td>
<td><p><span data-ttu-id="939ba-129">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="939ba-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="939ba-130">TRUE の場合は、Accept と Reject は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="939ba-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

