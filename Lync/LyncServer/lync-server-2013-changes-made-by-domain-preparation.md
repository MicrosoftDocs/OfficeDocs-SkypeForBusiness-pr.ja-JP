---
title: 'Lync Server 2013: ドメインの準備によって加えられた変更'
description: 'Lync Server 2013: ドメインの準備によって加えられた変更。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26400bd1c72c6ae3b8dc1f2d2d8f6c6906b80595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543693"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="74791-103">Lync Server 2013 のドメインの準備によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="74791-103">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74791-104">_**トピックの最終更新日:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="74791-104">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="74791-p101">次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。</span><span class="sxs-lookup"><span data-stu-id="74791-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="74791-107">ドメイン ルートに追加された ACE</span><span class="sxs-lookup"><span data-stu-id="74791-107">ACEs Added to Domain Root</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74791-108">ACE</span><span class="sxs-lookup"><span data-stu-id="74791-108">ACE</span></span></th>
<th><span data-ttu-id="74791-109">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="74791-109">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="74791-110">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="74791-110">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="74791-111">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="74791-111">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="74791-112">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="74791-112">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="74791-113">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="74791-113">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74791-114">コンテナーの読み取り (継承されない)</span><span class="sxs-lookup"><span data-stu-id="74791-114">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="74791-115"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="74791-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-116"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-116"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-117">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-117">No</span></span></p></td>
<td><p><span data-ttu-id="74791-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-118">No</span></span></p></td>
<td><p><span data-ttu-id="74791-119">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-119">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74791-120">User-Account-Restrictions ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="74791-120">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="74791-121"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-121"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-122">No</span></span></p></td>
<td><p><span data-ttu-id="74791-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-123">No</span></span></p></td>
<td><p><span data-ttu-id="74791-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-124">No</span></span></p></td>
<td><p><span data-ttu-id="74791-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-125">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74791-126">Personal-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="74791-126">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="74791-127"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-127"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-128">No</span></span></p></td>
<td><p><span data-ttu-id="74791-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-129">No</span></span></p></td>
<td><p><span data-ttu-id="74791-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-130">No</span></span></p></td>
<td><p><span data-ttu-id="74791-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-131">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74791-132">General-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="74791-132">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="74791-133"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-133"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-134">No</span></span></p></td>
<td><p><span data-ttu-id="74791-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-135">No</span></span></p></td>
<td><p><span data-ttu-id="74791-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-136">No</span></span></p></td>
<td><p><span data-ttu-id="74791-137">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-137">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74791-138">Public-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="74791-138">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="74791-139"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-139"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-140">No</span></span></p></td>
<td><p><span data-ttu-id="74791-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-141">No</span></span></p></td>
<td><p><span data-ttu-id="74791-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-142">No</span></span></p></td>
<td><p><span data-ttu-id="74791-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-143">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74791-144">RTCUserSearchProperty-Set ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="74791-144">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="74791-145"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-145"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-146">No</span></span></p></td>
<td><p><span data-ttu-id="74791-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-147">No</span></span></p></td>
<td><p><span data-ttu-id="74791-148">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-148">No</span></span></p></td>
<td><p><span data-ttu-id="74791-149"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-149"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74791-150">RTCPropertySet ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="74791-150">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="74791-151"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-151"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-152">No</span></span></p></td>
<td><p><span data-ttu-id="74791-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-153">No</span></span></p></td>
<td><p><span data-ttu-id="74791-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-154">No</span></span></p></td>
<td><p><span data-ttu-id="74791-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-155">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74791-156">Proxy-Addresses ユーザー プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="74791-156">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="74791-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-157">No</span></span></p></td>
<td><p><span data-ttu-id="74791-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-158">No</span></span></p></td>
<td><p><span data-ttu-id="74791-159"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-159"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-160">No</span></span></p></td>
<td><p><span data-ttu-id="74791-161">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-161">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74791-162">RTCUserSearchProperty-Set ユーザー プロパティ セットの書き込み</span><span class="sxs-lookup"><span data-stu-id="74791-162">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="74791-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-163">No</span></span></p></td>
<td><p><span data-ttu-id="74791-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-164">No</span></span></p></td>
<td><p><span data-ttu-id="74791-165"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-165"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-166">No</span></span></p></td>
<td><p><span data-ttu-id="74791-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-167">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74791-168">RTCPropertySet ユーザー プロパティ セットの書き込み</span><span class="sxs-lookup"><span data-stu-id="74791-168">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="74791-169">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-169">No</span></span></p></td>
<td><p><span data-ttu-id="74791-170">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-170">No</span></span></p></td>
<td><p><span data-ttu-id="74791-171"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-171"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-172">No</span></span></p></td>
<td><p><span data-ttu-id="74791-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-173">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74791-174">すべての Active Directory オブジェクトの DS-Replication-Get-Changes プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="74791-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="74791-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-175">No</span></span></p></td>
<td><p><span data-ttu-id="74791-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-176">No</span></span></p></td>
<td><p><span data-ttu-id="74791-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-177">No</span></span></p></td>
<td><p><span data-ttu-id="74791-178"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="74791-178"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-179">いいえ</span><span class="sxs-lookup"><span data-stu-id="74791-179">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74791-p102">次の表は、ドメインを準備する際に 3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) に作成される ACE を示しています。特に注記のない限り、これらの ACE はすべて継承されます。</span><span class="sxs-lookup"><span data-stu-id="74791-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="74791-182">組み込みコンテナーに追加された ACE</span><span class="sxs-lookup"><span data-stu-id="74791-182">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74791-183">ACE</span><span class="sxs-lookup"><span data-stu-id="74791-183">ACE</span></span></th>
<th><span data-ttu-id="74791-184">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="74791-184">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="74791-185">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="74791-185">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74791-186">コンテナーの読み取り (継承されない)</span><span class="sxs-lookup"><span data-stu-id="74791-186">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="74791-187"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="74791-187"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="74791-188"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="74791-188"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

