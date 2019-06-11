---
title: 'Lync Server 2013: ドメインの準備によって行われた変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b674e2c3d65aeda22838dca08ac5b016fa83359
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="dbb92-102">Lync Server 2013 でのドメインの準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="dbb92-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbb92-103">_**最終更新日:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="dbb92-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="dbb92-104">次の表に、ドメインの準備でドメインルート上に作成されるアクセス制御エントリ (Ace) を示します。</span><span class="sxs-lookup"><span data-stu-id="dbb92-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="dbb92-105">特に注記がない限り、すべての Ace が継承されます。</span><span class="sxs-lookup"><span data-stu-id="dbb92-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="dbb92-106">ドメインルートに追加された Ace</span><span class="sxs-lookup"><span data-stu-id="dbb92-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="dbb92-107">AS</span><span class="sxs-lookup"><span data-stu-id="dbb92-107">ACE</span></span></th>
<th><span data-ttu-id="dbb92-108">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="dbb92-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="dbb92-109">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="dbb92-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="dbb92-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="dbb92-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="dbb92-111">RTCHSUniversal-サービス</span><span class="sxs-lookup"><span data-stu-id="dbb92-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="dbb92-112">認証済み-ユーザー</span><span class="sxs-lookup"><span data-stu-id="dbb92-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbb92-113">読み取りコンテナー (継承されません)</span><span class="sxs-lookup"><span data-stu-id="dbb92-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="dbb92-114"><strong>うん</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-115"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-116">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-116">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-117">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-117">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbb92-119">ユーザー PropertySet の読み取りユーザーアカウントの制限</span><span class="sxs-lookup"><span data-stu-id="dbb92-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="dbb92-120"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-121">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-122">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-123">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbb92-125">ユーザー PropertySet の個人情報を読む</span><span class="sxs-lookup"><span data-stu-id="dbb92-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="dbb92-126"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-127">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-128">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-129">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbb92-131">ユーザー PropertySet の読み取りの概要-情報</span><span class="sxs-lookup"><span data-stu-id="dbb92-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="dbb92-132"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-133">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-134">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-135">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbb92-137">ユーザー PropertySet パブリック情報を読む</span><span class="sxs-lookup"><span data-stu-id="dbb92-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="dbb92-138"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-139">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-140">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-141">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbb92-143">ユーザー PropertySet RTCUserSearchProperty セットを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="dbb92-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="dbb92-144"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-145">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-146">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-147">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-148"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbb92-149">ユーザー PropertySet RTCPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="dbb92-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="dbb92-150"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-151">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-152">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-153">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbb92-155">ユーザープロパティプロキシアドレスの書き込み</span><span class="sxs-lookup"><span data-stu-id="dbb92-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="dbb92-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-156">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-157">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-158"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-159">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbb92-161">User PropertySet RTCUserSearchProperty セットの書き込み</span><span class="sxs-lookup"><span data-stu-id="dbb92-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="dbb92-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-162">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-163">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-164"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-165">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbb92-167">ユーザー PropertySet の書き込み RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="dbb92-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="dbb92-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-168">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-169">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-169">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-170"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-171">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbb92-173">PropertySet の DS-レプリケーション-すべての Active Directory オブジェクトの変更内容を確認する</span><span class="sxs-lookup"><span data-stu-id="dbb92-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="dbb92-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-174">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-175">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-176">No</span></span></p></td>
<td><p><span data-ttu-id="dbb92-177"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="dbb92-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dbb92-179">次の表は、3つの組み込みコンテナー (ユーザー、コンピューター、ドメインコントローラー) で、ドメインの準備によって作成される Ace を示しています。</span><span class="sxs-lookup"><span data-stu-id="dbb92-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="dbb92-180">特に注記がない限り、すべての Ace が継承されます。</span><span class="sxs-lookup"><span data-stu-id="dbb92-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="dbb92-181">組み込みのコンテナーに追加された Ace</span><span class="sxs-lookup"><span data-stu-id="dbb92-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbb92-182">AS</span><span class="sxs-lookup"><span data-stu-id="dbb92-182">ACE</span></span></th>
<th><span data-ttu-id="dbb92-183">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="dbb92-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="dbb92-184">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="dbb92-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbb92-185">読み取りコンテナー (継承されません)</span><span class="sxs-lookup"><span data-stu-id="dbb92-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="dbb92-186"><strong>うん</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="dbb92-187"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="dbb92-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

