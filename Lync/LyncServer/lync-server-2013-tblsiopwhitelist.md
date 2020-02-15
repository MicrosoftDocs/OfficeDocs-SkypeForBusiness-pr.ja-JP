---
title: 'Lync Server 2013: tblSiopWhiteList'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86ffecf185ab0c32c45e910d1821a33cbcabaea3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="cb065-102">Lync Server 2013 の tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="cb065-102">tblSiopWhiteList in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb065-103">_**トピックの最終更新日:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="cb065-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="cb065-104">tblSiopWhiteList は、ノードと関連付けることができる登録済みアドインの一覧です。</span><span class="sxs-lookup"><span data-stu-id="cb065-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="cb065-105">Columns</span><span class="sxs-lookup"><span data-stu-id="cb065-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb065-106">列</span><span class="sxs-lookup"><span data-stu-id="cb065-106">Column</span></span></th>
<th><span data-ttu-id="cb065-107">種類</span><span class="sxs-lookup"><span data-stu-id="cb065-107">Type</span></span></th>
<th><span data-ttu-id="cb065-108">説明</span><span class="sxs-lookup"><span data-stu-id="cb065-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb065-109">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="cb065-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="cb065-110">NULL でない GUID</span><span class="sxs-lookup"><span data-stu-id="cb065-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="cb065-111">アドインの GUID。</span><span class="sxs-lookup"><span data-stu-id="cb065-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb065-112">siopName</span><span class="sxs-lookup"><span data-stu-id="cb065-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="cb065-113">NULL でない nvarchar (50)</span><span class="sxs-lookup"><span data-stu-id="cb065-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="cb065-114">アドインの表示名。</span><span class="sxs-lookup"><span data-stu-id="cb065-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb065-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="cb065-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="cb065-116">NULL でない nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="cb065-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="cb065-117">アドインの URL。</span><span class="sxs-lookup"><span data-stu-id="cb065-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="cb065-118">キー</span><span class="sxs-lookup"><span data-stu-id="cb065-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb065-119">列</span><span class="sxs-lookup"><span data-stu-id="cb065-119">Column</span></span></th>
<th><span data-ttu-id="cb065-120">説明</span><span class="sxs-lookup"><span data-stu-id="cb065-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb065-121">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="cb065-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="cb065-122">主キー。</span><span class="sxs-lookup"><span data-stu-id="cb065-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

