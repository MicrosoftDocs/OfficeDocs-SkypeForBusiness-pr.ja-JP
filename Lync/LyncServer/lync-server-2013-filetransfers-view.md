---
title: 'Lync Server 2013: FileTransfers ビュー'
description: 'Lync Server 2013: FileTransfers ビュー。'
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
ms.openlocfilehash: dd2b084274a4d5daa093f2269617214f703ac03e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552623"
---
# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="af8af-103">Lync Server 2013 の FileTransfers ビュー</span><span class="sxs-lookup"><span data-stu-id="af8af-103">FileTransfers view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af8af-104">_**トピックの最終更新日:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="af8af-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="af8af-105">FileTransfer view は、ピアツーピアのファイル転送セッションに関する情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="af8af-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="af8af-106">このビューは Microsoft Lync Server 2013 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="af8af-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af8af-107">FileTransfers ビューには、以下の列に加えて、 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 の Sessiondetails ビュー</A> のすべての列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="af8af-107">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af8af-108">Column</span><span class="sxs-lookup"><span data-stu-id="af8af-108">Column</span></span></th>
<th><span data-ttu-id="af8af-109">データ型</span><span class="sxs-lookup"><span data-stu-id="af8af-109">Data Type</span></span></th>
<th><span data-ttu-id="af8af-110">詳細</span><span class="sxs-lookup"><span data-stu-id="af8af-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af8af-111"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="af8af-111"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="af8af-112">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="af8af-112">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="af8af-113">送信されたファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="af8af-113">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af8af-114"><strong>クッキー</strong></span><span class="sxs-lookup"><span data-stu-id="af8af-114"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="af8af-115">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="af8af-115">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="af8af-116">すべてのフォローアップ メッセージをこれに関連付けられたものとして識別するために使用します。</span><span class="sxs-lookup"><span data-stu-id="af8af-116">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af8af-117"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="af8af-117"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="af8af-118">識別子</span><span class="sxs-lookup"><span data-stu-id="af8af-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="af8af-119">同じファイル名が使用されているファイル送信を区別するための一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="af8af-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af8af-120"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="af8af-120"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="af8af-121">若干</span><span class="sxs-lookup"><span data-stu-id="af8af-121">bit</span></span></p></td>
<td><p><span data-ttu-id="af8af-p102">TRUE または NULL。TRUE の場合は、Reject と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="af8af-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af8af-124"><strong>拒否する</strong></span><span class="sxs-lookup"><span data-stu-id="af8af-124"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="af8af-125">若干</span><span class="sxs-lookup"><span data-stu-id="af8af-125">bit</span></span></p></td>
<td><p><span data-ttu-id="af8af-p103">TRUE または NULL。TRUE の場合は、Accept と Cancel が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="af8af-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af8af-128"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="af8af-128"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="af8af-129">若干</span><span class="sxs-lookup"><span data-stu-id="af8af-129">bit</span></span></p></td>
<td><p><span data-ttu-id="af8af-p104">TRUE または NULL。TRUE の場合は、Accept と Reject が NULL になります。</span><span class="sxs-lookup"><span data-stu-id="af8af-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

