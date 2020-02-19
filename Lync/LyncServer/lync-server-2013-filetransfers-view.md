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
ms.openlocfilehash: 8b1704c3496d8c5971af7830462d17fc48042e57
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="4da4a-102">Lync Server 2013 の FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="4da4a-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4da4a-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4da4a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4da4a-104">FileTransfer view は、ピアツーピアのファイル転送セッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="4da4a-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="4da4a-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="4da4a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4da4a-106">FileTransfers ビューには、以下の列に加えて、 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の Sessiondetails ビュー</A>のすべての列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4da4a-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4da4a-107">列</span><span class="sxs-lookup"><span data-stu-id="4da4a-107">Column</span></span></th>
<th><span data-ttu-id="4da4a-108">データ型</span><span class="sxs-lookup"><span data-stu-id="4da4a-108">Data Type</span></span></th>
<th><span data-ttu-id="4da4a-109">詳細</span><span class="sxs-lookup"><span data-stu-id="4da4a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4da4a-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="4da4a-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="4da4a-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4da4a-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4da4a-112">送信されたファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="4da4a-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4da4a-113"><strong>クッキー</strong></span><span class="sxs-lookup"><span data-stu-id="4da4a-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="4da4a-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="4da4a-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4da4a-115">すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</span><span class="sxs-lookup"><span data-stu-id="4da4a-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4da4a-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="4da4a-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="4da4a-117">識別子</span><span class="sxs-lookup"><span data-stu-id="4da4a-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="4da4a-118">同じファイル名が使用されているファイル送信を区別するための一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="4da4a-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4da4a-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="4da4a-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="4da4a-120">若干</span><span class="sxs-lookup"><span data-stu-id="4da4a-120">bit</span></span></p></td>
<td><p><span data-ttu-id="4da4a-p102">TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="4da4a-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4da4a-123"><strong>拒否する</strong></span><span class="sxs-lookup"><span data-stu-id="4da4a-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="4da4a-124">若干</span><span class="sxs-lookup"><span data-stu-id="4da4a-124">bit</span></span></p></td>
<td><p><span data-ttu-id="4da4a-p103">TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="4da4a-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4da4a-127"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="4da4a-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="4da4a-128">若干</span><span class="sxs-lookup"><span data-stu-id="4da4a-128">bit</span></span></p></td>
<td><p><span data-ttu-id="4da4a-p104">TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="4da4a-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

