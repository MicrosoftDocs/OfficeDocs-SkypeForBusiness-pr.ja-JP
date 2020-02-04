---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="dd092-102">Lync Server 2013 の tblRoleType</span><span class="sxs-lookup"><span data-stu-id="dd092-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd092-103">_**最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="dd092-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="dd092-104">tblRoleType は、役割の種類とそれに関連付けられたアクセス許可セットを含む静的参照テーブルです。</span><span class="sxs-lookup"><span data-stu-id="dd092-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="dd092-105">行</span><span class="sxs-lookup"><span data-stu-id="dd092-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd092-106">列</span><span class="sxs-lookup"><span data-stu-id="dd092-106">Column</span></span></th>
<th><span data-ttu-id="dd092-107">型</span><span class="sxs-lookup"><span data-stu-id="dd092-107">Type</span></span></th>
<th><span data-ttu-id="dd092-108">説明</span><span class="sxs-lookup"><span data-stu-id="dd092-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd092-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="dd092-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="dd092-110">int (null ではない)</span><span class="sxs-lookup"><span data-stu-id="dd092-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="dd092-111">役割の種類 ID。</span><span class="sxs-lookup"><span data-stu-id="dd092-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd092-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="dd092-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="dd092-113">nvarchar (256)、null ではない</span><span class="sxs-lookup"><span data-stu-id="dd092-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="dd092-114">役割の種類の説明。</span><span class="sxs-lookup"><span data-stu-id="dd092-114">Role type description.</span></span> <span data-ttu-id="dd092-115">次の4つの役割を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd092-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="dd092-116">メンバー: チャットルームのメンバー</span><span class="sxs-lookup"><span data-stu-id="dd092-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="dd092-117">管理職: チャットルームマネージャー</span><span class="sxs-lookup"><span data-stu-id="dd092-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="dd092-118">読み上げ: 聴衆チャットルームの発表者</span><span class="sxs-lookup"><span data-stu-id="dd092-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="dd092-119">作成者: チャットルームを作成できる</span><span class="sxs-lookup"><span data-stu-id="dd092-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd092-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="dd092-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="dd092-121">bigint (null ではない)</span><span class="sxs-lookup"><span data-stu-id="dd092-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="dd092-122">ロールの権限セット。</span><span class="sxs-lookup"><span data-stu-id="dd092-122">Permission set for the role.</span></span> <span data-ttu-id="dd092-123">使用されるビットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dd092-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="dd092-124">2: 役割がノードを管理できる場合は True。</span><span class="sxs-lookup"><span data-stu-id="dd092-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="dd092-125">4: 役割で子ノードを作成できる場合は True です。</span><span class="sxs-lookup"><span data-stu-id="dd092-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="dd092-126">7: 役割がチャットルーム (または、カテゴリの子チャットルーム) に参加できる場合は True。</span><span class="sxs-lookup"><span data-stu-id="dd092-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="dd092-127">8: 役割がチャットルーム (または、カテゴリの子チャットルーム) でチャットできる場合は True。</span><span class="sxs-lookup"><span data-stu-id="dd092-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="dd092-128">10: 役割がチャットルームに参加していないときでもチャット履歴を読むことができる場合は True。</span><span class="sxs-lookup"><span data-stu-id="dd092-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="dd092-129">11: 役割がチャットルームを表示できる場合は True です。</span><span class="sxs-lookup"><span data-stu-id="dd092-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="dd092-130">(これは、スコープや可視性などの要因によってさらに改良されています)。</span><span class="sxs-lookup"><span data-stu-id="dd092-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="dd092-131">12: この役割が聴衆チャットルームでチャットできる場合は True です。</span><span class="sxs-lookup"><span data-stu-id="dd092-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="dd092-132">13: ノードを表示したときに、役割が可視性規則を無視できる場合は True です。</span><span class="sxs-lookup"><span data-stu-id="dd092-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="dd092-133">キー</span><span class="sxs-lookup"><span data-stu-id="dd092-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd092-134">列</span><span class="sxs-lookup"><span data-stu-id="dd092-134">Column</span></span></th>
<th><span data-ttu-id="dd092-135">説明</span><span class="sxs-lookup"><span data-stu-id="dd092-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd092-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="dd092-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="dd092-137">主キー。</span><span class="sxs-lookup"><span data-stu-id="dd092-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

