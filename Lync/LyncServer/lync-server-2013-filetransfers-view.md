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
ms.openlocfilehash: 95cc6790766d68ee478cf1b80326c974f7c15f1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="6ddf3-102">Lync Server 2013 の FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="6ddf3-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ddf3-103">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="6ddf3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="6ddf3-104">FileTransfer view は、ピアツーピアのファイル転送セッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="6ddf3-105">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ddf3-106">FileTransfers ビューには、以下の列に加えて、 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の Sessiondetails ビュー</A>のすべての列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ddf3-107">列</span><span class="sxs-lookup"><span data-stu-id="6ddf3-107">Column</span></span></th>
<th><span data-ttu-id="6ddf3-108">データ型</span><span class="sxs-lookup"><span data-stu-id="6ddf3-108">Data Type</span></span></th>
<th><span data-ttu-id="6ddf3-109">詳細</span><span class="sxs-lookup"><span data-stu-id="6ddf3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ddf3-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="6ddf3-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddf3-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6ddf3-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6ddf3-112">送信されたファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ddf3-113"><strong>クッキー</strong></span><span class="sxs-lookup"><span data-stu-id="6ddf3-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddf3-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="6ddf3-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="6ddf3-115">すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ddf3-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="6ddf3-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddf3-117">識別子</span><span class="sxs-lookup"><span data-stu-id="6ddf3-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="6ddf3-118">同じファイル名が使用されているファイル送信を区別するための一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ddf3-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="6ddf3-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddf3-120">若干</span><span class="sxs-lookup"><span data-stu-id="6ddf3-120">bit</span></span></p></td>
<td><p><span data-ttu-id="6ddf3-p102">TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ddf3-123"><strong>拒否する</strong></span><span class="sxs-lookup"><span data-stu-id="6ddf3-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddf3-124">若干</span><span class="sxs-lookup"><span data-stu-id="6ddf3-124">bit</span></span></p></td>
<td><p><span data-ttu-id="6ddf3-p103">TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ddf3-127"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="6ddf3-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="6ddf3-128">若干</span><span class="sxs-lookup"><span data-stu-id="6ddf3-128">bit</span></span></p></td>
<td><p><span data-ttu-id="6ddf3-p104">TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="6ddf3-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

