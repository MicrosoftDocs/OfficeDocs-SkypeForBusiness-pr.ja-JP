---
title: 'Lync Server 2013: tblSiopWhiteList'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fff11d98d35b288436922477025ea9cf49e924cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="e5790-102">Lync Server 2013 の tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="e5790-102">tblSiopWhiteList in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5790-103">_**最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="e5790-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="e5790-104">tblSiopWhiteList は、ノードに関連付けることができる登録済みアドインの一覧です。</span><span class="sxs-lookup"><span data-stu-id="e5790-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="e5790-105">行</span><span class="sxs-lookup"><span data-stu-id="e5790-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5790-106">列</span><span class="sxs-lookup"><span data-stu-id="e5790-106">Column</span></span></th>
<th><span data-ttu-id="e5790-107">型</span><span class="sxs-lookup"><span data-stu-id="e5790-107">Type</span></span></th>
<th><span data-ttu-id="e5790-108">説明</span><span class="sxs-lookup"><span data-stu-id="e5790-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5790-109">siopID</span><span class="sxs-lookup"><span data-stu-id="e5790-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="e5790-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="e5790-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="e5790-111">アドインの GUID です。</span><span class="sxs-lookup"><span data-stu-id="e5790-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5790-112">siopName</span><span class="sxs-lookup"><span data-stu-id="e5790-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="e5790-113">nvarchar (50)、null ではない</span><span class="sxs-lookup"><span data-stu-id="e5790-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="e5790-114">アドインの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="e5790-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5790-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="e5790-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="e5790-116">nvarchar (255)、null ではない</span><span class="sxs-lookup"><span data-stu-id="e5790-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="e5790-117">アドインの URL。</span><span class="sxs-lookup"><span data-stu-id="e5790-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e5790-118">キー</span><span class="sxs-lookup"><span data-stu-id="e5790-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5790-119">列</span><span class="sxs-lookup"><span data-stu-id="e5790-119">Column</span></span></th>
<th><span data-ttu-id="e5790-120">説明</span><span class="sxs-lookup"><span data-stu-id="e5790-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5790-121">siopID</span><span class="sxs-lookup"><span data-stu-id="e5790-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="e5790-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="e5790-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

