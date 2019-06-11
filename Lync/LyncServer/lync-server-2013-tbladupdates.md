---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f171d8346442f915cd71fb48d51bba80bcfa32ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="84252-102">Lync Server 2013 の tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="84252-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84252-103">_**最終更新日:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="84252-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="84252-104">tblADUpdates には、以降の Active Directory 同期手順でまだ処理されていない Active Directory ドメインサービスの変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="84252-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="84252-105">行</span><span class="sxs-lookup"><span data-stu-id="84252-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84252-106">列</span><span class="sxs-lookup"><span data-stu-id="84252-106">Column</span></span></th>
<th><span data-ttu-id="84252-107">型</span><span class="sxs-lookup"><span data-stu-id="84252-107">Type</span></span></th>
<th><span data-ttu-id="84252-108">説明</span><span class="sxs-lookup"><span data-stu-id="84252-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84252-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="84252-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="84252-110">GUID、null ではない</span><span class="sxs-lookup"><span data-stu-id="84252-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="84252-111">変更されたオブジェクトのプリンシパル GUID。</span><span class="sxs-lookup"><span data-stu-id="84252-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84252-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="84252-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="84252-113">nvarchar (384)、null ではない</span><span class="sxs-lookup"><span data-stu-id="84252-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="84252-114">オブジェクトの識別名。</span><span class="sxs-lookup"><span data-stu-id="84252-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84252-115">Prin属性が変更されました</span><span class="sxs-lookup"><span data-stu-id="84252-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="84252-116">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="84252-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="84252-117">オブジェクトの少なくとも1つの属性が変更された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="84252-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84252-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="84252-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="84252-119">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="84252-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="84252-120">メンバーシップが変更された場合は True です。</span><span class="sxs-lookup"><span data-stu-id="84252-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84252-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="84252-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="84252-122">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="84252-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="84252-123">使用されません。</span><span class="sxs-lookup"><span data-stu-id="84252-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84252-124">プリントが削除されました</span><span class="sxs-lookup"><span data-stu-id="84252-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="84252-125">ビット、null ではない</span><span class="sxs-lookup"><span data-stu-id="84252-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="84252-126">オブジェクトが削除された場合は True。</span><span class="sxs-lookup"><span data-stu-id="84252-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84252-127">最終更新日</span><span class="sxs-lookup"><span data-stu-id="84252-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="84252-128">datetime。 null ではありません</span><span class="sxs-lookup"><span data-stu-id="84252-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="84252-129">行が挿入された時刻のタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="84252-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

