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
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="c490a-102">Lync Server 2013 のドメインの準備によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="c490a-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c490a-103">_**トピックの最終更新日:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="c490a-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="c490a-p101">次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。</span><span class="sxs-lookup"><span data-stu-id="c490a-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="c490a-106">ドメイン ルートに追加された ACE</span><span class="sxs-lookup"><span data-stu-id="c490a-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="c490a-107">ACE</span><span class="sxs-lookup"><span data-stu-id="c490a-107">ACE</span></span></th>
<th><span data-ttu-id="c490a-108">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="c490a-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="c490a-109">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="c490a-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="c490a-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="c490a-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="c490a-111">RTCHSUniversal-サービス</span><span class="sxs-lookup"><span data-stu-id="c490a-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="c490a-112">認証されたユーザー</span><span class="sxs-lookup"><span data-stu-id="c490a-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c490a-113">コンテナーの読み取り (継承されない)</span><span class="sxs-lookup"><span data-stu-id="c490a-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c490a-114"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-115"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-116">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-116">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-117">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-117">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c490a-119">User-Account-Restrictions ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="c490a-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="c490a-120"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-121">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-122">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-123">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c490a-125">Personal-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="c490a-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="c490a-126"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-127">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-128">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-129">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c490a-131">General-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="c490a-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="c490a-132"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-133">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-134">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-135">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c490a-137">Public-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="c490a-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="c490a-138"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-139">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-140">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-141">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c490a-143">RTCUserSearchProperty-Set ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="c490a-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="c490a-144"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-145">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-146">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-147">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-148"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c490a-149">RTCPropertySet ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="c490a-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="c490a-150"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-151">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-152">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-153">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c490a-155">Proxy-Addresses ユーザー プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="c490a-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="c490a-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-156">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-157">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-158"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-159">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c490a-161">RTCUserSearchProperty-Set ユーザー プロパティ セットの書き込み</span><span class="sxs-lookup"><span data-stu-id="c490a-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="c490a-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-162">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-163">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-164"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-165">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c490a-167">RTCPropertySet ユーザー プロパティ セットの書き込み</span><span class="sxs-lookup"><span data-stu-id="c490a-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="c490a-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-168">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-169">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-169">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-170"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-171">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c490a-173">すべての Active Directory オブジェクトの DS-Replication-Get-Changes プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="c490a-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="c490a-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-174">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-175">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="c490a-176">No</span></span></p></td>
<td><p><span data-ttu-id="c490a-177"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-178">×</span><span class="sxs-lookup"><span data-stu-id="c490a-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c490a-p102">次の表は、ドメインを準備する際に 3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) に作成される ACE を示しています。特に注記のない限り、これらの ACE はすべて継承されます。</span><span class="sxs-lookup"><span data-stu-id="c490a-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="c490a-181">組み込みコンテナーに追加された ACE</span><span class="sxs-lookup"><span data-stu-id="c490a-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c490a-182">ACE</span><span class="sxs-lookup"><span data-stu-id="c490a-182">ACE</span></span></th>
<th><span data-ttu-id="c490a-183">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="c490a-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="c490a-184">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="c490a-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c490a-185">コンテナーの読み取り (継承されない)</span><span class="sxs-lookup"><span data-stu-id="c490a-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c490a-186"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c490a-187"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="c490a-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

