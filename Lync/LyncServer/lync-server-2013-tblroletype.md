---
title: 'Lync Server 2013: tblRoleType'
description: 'Lync Server 2013: tblRoleType。'
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
ms.openlocfilehash: f458259acaee7821d5f6a7339b993c70fe65f595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568543"
---
# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="67e6b-103">Lync Server 2013 の tblRoleType</span><span class="sxs-lookup"><span data-stu-id="67e6b-103">tblRoleType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67e6b-104">_**トピックの最終更新日:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="67e6b-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="67e6b-105">tblRoleType は静的な検索テーブルであり、役割の種類とそれに関連付けられたアクセス許可のセットが格納されています。</span><span class="sxs-lookup"><span data-stu-id="67e6b-105">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="67e6b-106">段組み</span><span class="sxs-lookup"><span data-stu-id="67e6b-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67e6b-107">Column</span><span class="sxs-lookup"><span data-stu-id="67e6b-107">Column</span></span></th>
<th><span data-ttu-id="67e6b-108">種類</span><span class="sxs-lookup"><span data-stu-id="67e6b-108">Type</span></span></th>
<th><span data-ttu-id="67e6b-109">説明</span><span class="sxs-lookup"><span data-stu-id="67e6b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67e6b-110">Tblroletype.rtypeid</span><span class="sxs-lookup"><span data-stu-id="67e6b-110">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="67e6b-111">NULL でない int</span><span class="sxs-lookup"><span data-stu-id="67e6b-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="67e6b-112">役割の種類の ID。</span><span class="sxs-lookup"><span data-stu-id="67e6b-112">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67e6b-113">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="67e6b-113">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="67e6b-114">NULL でない nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="67e6b-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="67e6b-p101">役割の種類の説明。使用できる役割は次の 4 つです。</span><span class="sxs-lookup"><span data-stu-id="67e6b-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="67e6b-117">メンバー: チャット ルームのメンバー</span><span class="sxs-lookup"><span data-stu-id="67e6b-117">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="67e6b-118">マネージャー: チャット ルームのマネージャー</span><span class="sxs-lookup"><span data-stu-id="67e6b-118">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="67e6b-119">承認されたメンバー: 大会議室のチャット ルームの発表者</span><span class="sxs-lookup"><span data-stu-id="67e6b-119">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="67e6b-120">作成者: チャット ルームの作成者</span><span class="sxs-lookup"><span data-stu-id="67e6b-120">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67e6b-121">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="67e6b-121">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="67e6b-122">NULL でない bigint</span><span class="sxs-lookup"><span data-stu-id="67e6b-122">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="67e6b-p102">役割のアクセス許可セット。使用されるビットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67e6b-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="67e6b-125">2: 役割がノードを管理できる場合は True。</span><span class="sxs-lookup"><span data-stu-id="67e6b-125">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="67e6b-126">4: 役割が子ノードを作成できる場合は True。</span><span class="sxs-lookup"><span data-stu-id="67e6b-126">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="67e6b-127">7: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) に参加できる場合は True。</span><span class="sxs-lookup"><span data-stu-id="67e6b-127">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="67e6b-128">8: 役割がチャット ルーム (またはカテゴリの子チャット ルーム) でチャットできる場合は True。</span><span class="sxs-lookup"><span data-stu-id="67e6b-128">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="67e6b-129">10: 役割がチャット ルームに参加していなくてもチャットの履歴を読むことができる場合は True。</span><span class="sxs-lookup"><span data-stu-id="67e6b-129">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="67e6b-p103">11: 役割がチャット ルームを見ることができる場合は True (これはスコープや可視性などの要素によってさらに微調整されます)。</span><span class="sxs-lookup"><span data-stu-id="67e6b-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="67e6b-132">12: 役割が大会議室のチャット ルームでチャットできる場合は True。</span><span class="sxs-lookup"><span data-stu-id="67e6b-132">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="67e6b-133">13: 役割がノードを表示するときに可視性ルールをバイパスできる場合は True。</span><span class="sxs-lookup"><span data-stu-id="67e6b-133">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="67e6b-134">キー</span><span class="sxs-lookup"><span data-stu-id="67e6b-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67e6b-135">列</span><span class="sxs-lookup"><span data-stu-id="67e6b-135">Column</span></span></th>
<th><span data-ttu-id="67e6b-136">説明</span><span class="sxs-lookup"><span data-stu-id="67e6b-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67e6b-137">Tblroletype.rtypeid</span><span class="sxs-lookup"><span data-stu-id="67e6b-137">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="67e6b-138">主キー。</span><span class="sxs-lookup"><span data-stu-id="67e6b-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

