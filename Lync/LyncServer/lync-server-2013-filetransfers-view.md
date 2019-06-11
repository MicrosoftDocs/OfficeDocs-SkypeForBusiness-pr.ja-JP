---
title: 'Lync Server 2013: FileTransfers ビュー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="cf57e-102">Lync Server 2013 の FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="cf57e-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf57e-103">_**最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cf57e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cf57e-104">FileTransfer ビューには、ピアツーピアファイル転送セッションに関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="cf57e-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="cf57e-105">このビューは、Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="cf57e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf57e-106">FileTransfers ビューには、 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の Sessiondetails ビュー</A>のすべての列に加えて、以下の列も含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf57e-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf57e-107">列</span><span class="sxs-lookup"><span data-stu-id="cf57e-107">Column</span></span></th>
<th><span data-ttu-id="cf57e-108">データ型</span><span class="sxs-lookup"><span data-stu-id="cf57e-108">Data Type</span></span></th>
<th><span data-ttu-id="cf57e-109">詳細</span><span class="sxs-lookup"><span data-stu-id="cf57e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf57e-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="cf57e-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="cf57e-111">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cf57e-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cf57e-112">転送されたファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="cf57e-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf57e-113"><strong>クッキー</strong></span><span class="sxs-lookup"><span data-stu-id="cf57e-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="cf57e-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="cf57e-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="cf57e-115">すべてのフォローアップメッセージをこのメールに関連付けられているものとして識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf57e-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf57e-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="cf57e-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="cf57e-117">長さ</span><span class="sxs-lookup"><span data-stu-id="cf57e-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="cf57e-118">同じファイル名を含むファイル転送を区別する一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="cf57e-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf57e-119"><strong>受諾</strong></span><span class="sxs-lookup"><span data-stu-id="cf57e-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="cf57e-120">bit</span><span class="sxs-lookup"><span data-stu-id="cf57e-120">bit</span></span></p></td>
<td><p><span data-ttu-id="cf57e-121">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf57e-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="cf57e-122">TRUE の場合は、拒否とキャンセルは NULL になります。</span><span class="sxs-lookup"><span data-stu-id="cf57e-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf57e-123"><strong>拒否</strong></span><span class="sxs-lookup"><span data-stu-id="cf57e-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="cf57e-124">bit</span><span class="sxs-lookup"><span data-stu-id="cf57e-124">bit</span></span></p></td>
<td><p><span data-ttu-id="cf57e-125">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf57e-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="cf57e-126">TRUE の場合は、Accept と Cancel は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="cf57e-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf57e-127"><strong>キャンセル</strong></span><span class="sxs-lookup"><span data-stu-id="cf57e-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="cf57e-128">bit</span><span class="sxs-lookup"><span data-stu-id="cf57e-128">bit</span></span></p></td>
<td><p><span data-ttu-id="cf57e-129">TRUE または NULL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf57e-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="cf57e-130">TRUE の場合は、Accept と Reject は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="cf57e-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

