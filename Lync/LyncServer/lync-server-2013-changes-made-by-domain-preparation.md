---
title: 'Lync Server 2013: ドメインの準備によって加えられた変更'
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
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="cf6a7-102">Lync Server 2013 のドメインの準備によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="cf6a7-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf6a7-103">_**トピックの最終更新日:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="cf6a7-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="cf6a7-p101">次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。</span><span class="sxs-lookup"><span data-stu-id="cf6a7-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="cf6a7-106">ドメイン ルートに追加された ACE</span><span class="sxs-lookup"><span data-stu-id="cf6a7-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="cf6a7-107">ACE</span><span class="sxs-lookup"><span data-stu-id="cf6a7-107">ACE</span></span></th>
<th><span data-ttu-id="cf6a7-108">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="cf6a7-109">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="cf6a7-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="cf6a7-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="cf6a7-111">RTCHSUniversal-サービス</span><span class="sxs-lookup"><span data-stu-id="cf6a7-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="cf6a7-112">認証されたユーザー</span><span class="sxs-lookup"><span data-stu-id="cf6a7-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf6a7-113">コンテナーの読み取り (継承されない)</span><span class="sxs-lookup"><span data-stu-id="cf6a7-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-114"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-115"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-116">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-116">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-117">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-117">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6a7-119">User-Account-Restrictions ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="cf6a7-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-120"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-121">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-122">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-123">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6a7-125">Personal-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="cf6a7-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-126"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-127">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-128">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-129">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6a7-131">General-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="cf6a7-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-132"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-133">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-134">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-135">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6a7-137">Public-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="cf6a7-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-138"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-139">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-140">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-141">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6a7-143">RTCUserSearchProperty-Set ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="cf6a7-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-144"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-145">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-146">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-147">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-148"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6a7-149">RTCPropertySet ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="cf6a7-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-150"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-151">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-152">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-153">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6a7-155">Proxy-Addresses ユーザー プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="cf6a7-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-156">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-157">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-158"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-159">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6a7-161">RTCUserSearchProperty-Set ユーザー プロパティ セットの書き込み</span><span class="sxs-lookup"><span data-stu-id="cf6a7-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-162">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-163">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-164"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-165">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6a7-167">RTCPropertySet ユーザー プロパティ セットの書き込み</span><span class="sxs-lookup"><span data-stu-id="cf6a7-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-168">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-169">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-169">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-170"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-171">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6a7-173">すべての Active Directory オブジェクトの DS-Replication-Get-Changes プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="cf6a7-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-174">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-175">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-176">No</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-177"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-178">×</span><span class="sxs-lookup"><span data-stu-id="cf6a7-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cf6a7-p102">次の表は、ドメインを準備する際に 3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) に作成される ACE を示しています。特に注記のない限り、これらの ACE はすべて継承されます。</span><span class="sxs-lookup"><span data-stu-id="cf6a7-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="cf6a7-181">組み込みコンテナーに追加された ACE</span><span class="sxs-lookup"><span data-stu-id="cf6a7-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf6a7-182">ACE</span><span class="sxs-lookup"><span data-stu-id="cf6a7-182">ACE</span></span></th>
<th><span data-ttu-id="cf6a7-183">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="cf6a7-184">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="cf6a7-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf6a7-185">コンテナーの読み取り (継承されない)</span><span class="sxs-lookup"><span data-stu-id="cf6a7-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="cf6a7-186"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="cf6a7-187"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="cf6a7-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

