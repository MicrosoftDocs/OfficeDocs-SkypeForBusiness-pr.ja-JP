---
title: 'Lync Server 2013: ドメインの準備によって行われた変更'
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
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="3dbc3-102">Lync Server 2013 でのドメインの準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="3dbc3-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dbc3-103">_**最終更新日:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="3dbc3-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="3dbc3-104">次の表に、ドメインの準備でドメインルート上に作成されるアクセス制御エントリ (Ace) を示します。</span><span class="sxs-lookup"><span data-stu-id="3dbc3-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="3dbc3-105">特に注記がない限り、すべての Ace が継承されます。</span><span class="sxs-lookup"><span data-stu-id="3dbc3-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="3dbc3-106">ドメインルートに追加された Ace</span><span class="sxs-lookup"><span data-stu-id="3dbc3-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="3dbc3-107">AS</span><span class="sxs-lookup"><span data-stu-id="3dbc3-107">ACE</span></span></th>
<th><span data-ttu-id="3dbc3-108">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="3dbc3-109">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="3dbc3-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="3dbc3-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="3dbc3-111">RTCHSUniversal-サービス</span><span class="sxs-lookup"><span data-stu-id="3dbc3-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="3dbc3-112">認証済み-ユーザー</span><span class="sxs-lookup"><span data-stu-id="3dbc3-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dbc3-113">読み取りコンテナー (継承されません)</span><span class="sxs-lookup"><span data-stu-id="3dbc3-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-114"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-115"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-116">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-116">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-117">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-117">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-118">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbc3-119">ユーザー PropertySet の読み取りユーザーアカウントの制限</span><span class="sxs-lookup"><span data-stu-id="3dbc3-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-120"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-121">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-121">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-122">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-123">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-123">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-124">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbc3-125">ユーザー PropertySet の個人情報を読む</span><span class="sxs-lookup"><span data-stu-id="3dbc3-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-126"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-127">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-127">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-128">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-129">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-129">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbc3-131">ユーザー PropertySet の読み取りの概要-情報</span><span class="sxs-lookup"><span data-stu-id="3dbc3-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-132"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-133">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-133">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-134">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-135">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-135">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-136">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbc3-137">ユーザー PropertySet パブリック情報を読む</span><span class="sxs-lookup"><span data-stu-id="3dbc3-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-138"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-139">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-140">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-140">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-141">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-142">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbc3-143">ユーザー PropertySet RTCUserSearchProperty セットを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="3dbc3-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-144"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-145">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-146">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-147">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-148"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbc3-149">ユーザー PropertySet RTCPropertySet を読む</span><span class="sxs-lookup"><span data-stu-id="3dbc3-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-150"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-151">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-151">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-152">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-153">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbc3-155">ユーザープロパティプロキシアドレスの書き込み</span><span class="sxs-lookup"><span data-stu-id="3dbc3-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-156">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-157">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-158"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-159">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-159">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbc3-161">User PropertySet RTCUserSearchProperty セットの書き込み</span><span class="sxs-lookup"><span data-stu-id="3dbc3-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-162">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-163">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-163">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-164"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-165">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-165">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-166">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3dbc3-167">ユーザー PropertySet の書き込み RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3dbc3-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-168">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-168">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-169">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-169">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-170"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-171">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-171">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-172">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3dbc3-173">PropertySet の DS-レプリケーション-すべての Active Directory オブジェクトの変更内容を確認する</span><span class="sxs-lookup"><span data-stu-id="3dbc3-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-174">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-175">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-176">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-176">No</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-177"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3dbc3-179">次の表は、3つの組み込みコンテナー (ユーザー、コンピューター、ドメインコントローラー) で、ドメインの準備によって作成される Ace を示しています。</span><span class="sxs-lookup"><span data-stu-id="3dbc3-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="3dbc3-180">特に注記がない限り、すべての Ace が継承されます。</span><span class="sxs-lookup"><span data-stu-id="3dbc3-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="3dbc3-181">組み込みのコンテナーに追加された Ace</span><span class="sxs-lookup"><span data-stu-id="3dbc3-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3dbc3-182">AS</span><span class="sxs-lookup"><span data-stu-id="3dbc3-182">ACE</span></span></th>
<th><span data-ttu-id="3dbc3-183">RTCUniversal-UserReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="3dbc3-184">RTCUniversal-ServerReadOnly-グループ</span><span class="sxs-lookup"><span data-stu-id="3dbc3-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3dbc3-185">読み取りコンテナー (継承されません)</span><span class="sxs-lookup"><span data-stu-id="3dbc3-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="3dbc3-186"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3dbc3-187"><strong>はい</strong></span><span class="sxs-lookup"><span data-stu-id="3dbc3-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

