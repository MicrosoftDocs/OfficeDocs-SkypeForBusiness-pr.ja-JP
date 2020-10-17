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
ms.openlocfilehash: 2b1eea02c41acf748674cdd7976028a51fdb367e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529504"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="7558b-102">Lync Server 2013 のドメインの準備によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="7558b-102">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7558b-103">_**トピックの最終更新日:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="7558b-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="7558b-p101">次の表は、ドメインを準備する際にドメイン ルートに作成されるアクセス制御エントリ (ACE) を示しています。特に注記のない限り、これらの ACE はすべて継承されます。</span><span class="sxs-lookup"><span data-stu-id="7558b-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="7558b-106">ドメイン ルートに追加された ACE</span><span class="sxs-lookup"><span data-stu-id="7558b-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="7558b-107">ACE</span><span class="sxs-lookup"><span data-stu-id="7558b-107">ACE</span></span></th>
<th><span data-ttu-id="7558b-108">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="7558b-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="7558b-109">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="7558b-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="7558b-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="7558b-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="7558b-111">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="7558b-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="7558b-112">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="7558b-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7558b-113">コンテナーの読み取り (継承されない)</span><span class="sxs-lookup"><span data-stu-id="7558b-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="7558b-114"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-115"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-116">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-116">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-117">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-117">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7558b-119">User-Account-Restrictions ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="7558b-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="7558b-120"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-121">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-122">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-123">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7558b-125">Personal-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="7558b-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="7558b-126"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-127">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-128">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-129">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7558b-131">General-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="7558b-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="7558b-132"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-133">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-134">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-135">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7558b-137">Public-Information ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="7558b-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="7558b-138"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-139">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-140">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-141">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7558b-143">RTCUserSearchProperty-Set ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="7558b-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="7558b-144"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-145">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-146">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-147">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-148"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7558b-149">RTCPropertySet ユーザー プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="7558b-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="7558b-150"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-151">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-152">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-153">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7558b-155">Proxy-Addresses ユーザー プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="7558b-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="7558b-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-156">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-157">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-158"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-159">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7558b-161">RTCUserSearchProperty-Set ユーザー プロパティ セットの書き込み</span><span class="sxs-lookup"><span data-stu-id="7558b-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="7558b-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-162">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-163">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-164"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-165">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7558b-167">RTCPropertySet ユーザー プロパティ セットの書き込み</span><span class="sxs-lookup"><span data-stu-id="7558b-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="7558b-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-168">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-169">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-169">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-170"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-171">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7558b-173">すべての Active Directory オブジェクトの DS-Replication-Get-Changes プロパティ セットの読み取り</span><span class="sxs-lookup"><span data-stu-id="7558b-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="7558b-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-174">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-175">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-176">No</span></span></p></td>
<td><p><span data-ttu-id="7558b-177"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="7558b-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7558b-p102">次の表は、ドメインを準備する際に 3 つの組み込みコンテナー (Users、Computers、および Domain Controllers) に作成される ACE を示しています。特に注記のない限り、これらの ACE はすべて継承されます。</span><span class="sxs-lookup"><span data-stu-id="7558b-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="7558b-181">組み込みコンテナーに追加された ACE</span><span class="sxs-lookup"><span data-stu-id="7558b-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7558b-182">ACE</span><span class="sxs-lookup"><span data-stu-id="7558b-182">ACE</span></span></th>
<th><span data-ttu-id="7558b-183">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="7558b-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="7558b-184">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="7558b-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7558b-185">コンテナーの読み取り (継承されない)</span><span class="sxs-lookup"><span data-stu-id="7558b-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="7558b-186"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="7558b-187"><strong>○</strong></span><span class="sxs-lookup"><span data-stu-id="7558b-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

