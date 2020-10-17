---
title: 'Lync Server 2013: Grant-CsSetupPermission によって加えられた変更'
description: 'Lync Server 2013: Grant-CsSetupPermission によって行われた変更。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543603"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="94842-103">Lync Server 2013 での Grant-CsSetupPermission による変更</span><span class="sxs-lookup"><span data-stu-id="94842-103">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94842-104">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="94842-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="94842-105">セットアップを委任するには、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサルグループに対するアクセス許可を付与します。この OU の RTCUniversalServerAdmins グループのメンバーは、Domain Admins グループのメンバーではなく、指定したドメインに Lync Server 2013 をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="94842-105">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="94842-106">**Grant-CsSetupPermission** コマンドレットは、次の表で指定されているように、RTCUniversalServerAdmins グループに OU に対するアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="94842-106">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="94842-107">OU 内のオブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="94842-107">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="94842-108">アクセス許可の適用先:</span><span class="sxs-lookup"><span data-stu-id="94842-108">Permissions apply to:</span></span></th>
<th><span data-ttu-id="94842-109">付与されるアクセス許可:</span><span class="sxs-lookup"><span data-stu-id="94842-109">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="94842-110">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="94842-110">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="94842-111">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="94842-111">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-112">servicePrincipalName の読み込み</span><span class="sxs-lookup"><span data-stu-id="94842-112">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="94842-113">servicePrincipalName の書き込み</span><span class="sxs-lookup"><span data-stu-id="94842-113">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="94842-114">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="94842-114">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="94842-115">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="94842-115">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94842-116">子の serviceConnectionPoint オブジェクト</span><span class="sxs-lookup"><span data-stu-id="94842-116">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="94842-117">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="94842-117">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-118">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="94842-118">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="94842-119">アクセス許可の書き込み</span><span class="sxs-lookup"><span data-stu-id="94842-119">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="94842-120">子の作成</span><span class="sxs-lookup"><span data-stu-id="94842-120">Create child</span></span></p></li>
<li><p><span data-ttu-id="94842-121">子の削除</span><span class="sxs-lookup"><span data-stu-id="94842-121">Delete child</span></span></p></li>
<li><p><span data-ttu-id="94842-122">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="94842-122">List contents</span></span></p></li>
<li><p><span data-ttu-id="94842-123">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="94842-123">Write property</span></span></p></li>
<li><p><span data-ttu-id="94842-124">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="94842-124">Read property</span></span></p></li>
<li><p><span data-ttu-id="94842-125">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="94842-125">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94842-126">子の msRTCSIP-Server オブジェクト</span><span class="sxs-lookup"><span data-stu-id="94842-126">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="94842-127">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="94842-127">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-128">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="94842-128">Write property</span></span></p></li>
<li><p><span data-ttu-id="94842-129">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="94842-129">Read property</span></span></p></li>
<li><p><span data-ttu-id="94842-130">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="94842-130">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94842-131">子の msRTCSIP-WebComponents オブジェクト</span><span class="sxs-lookup"><span data-stu-id="94842-131">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="94842-132">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="94842-132">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-133">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="94842-133">Write property</span></span></p></li>
<li><p><span data-ttu-id="94842-134">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="94842-134">Read property</span></span></p></li>
<li><p><span data-ttu-id="94842-135">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="94842-135">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94842-136">子の msRTCSIP-MCU オブジェクト</span><span class="sxs-lookup"><span data-stu-id="94842-136">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="94842-137">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="94842-137">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-138">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="94842-138">Write property</span></span></p></li>
<li><p><span data-ttu-id="94842-139">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="94842-139">Read property</span></span></p></li>
<li><p><span data-ttu-id="94842-140">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="94842-140">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94842-141">子の msRTCSIP-MediationServer オブジェクト</span><span class="sxs-lookup"><span data-stu-id="94842-141">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="94842-142">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="94842-142">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-143">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="94842-143">Write property</span></span></p></li>
<li><p><span data-ttu-id="94842-144">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="94842-144">Read property</span></span></p></li>
<li><p><span data-ttu-id="94842-145">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="94842-145">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94842-146">子の msRTCSIP-ApplicationServer オブジェクト</span><span class="sxs-lookup"><span data-stu-id="94842-146">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="94842-147">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="94842-147">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-148">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="94842-148">Write property</span></span></p></li>
<li><p><span data-ttu-id="94842-149">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="94842-149">Read property</span></span></p></li>
<li><p><span data-ttu-id="94842-150">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="94842-150">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="94842-151">子の msRTCSIP-ConnectionPoint オブジェクト</span><span class="sxs-lookup"><span data-stu-id="94842-151">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="94842-152">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="94842-152">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-153">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="94842-153">Write property</span></span></p></li>
<li><p><span data-ttu-id="94842-154">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="94842-154">Read property</span></span></p></li>
<li><p><span data-ttu-id="94842-155">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="94842-155">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="94842-156">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="94842-156">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="94842-157">serviceConnectionPoint に対する特別なアクセス:</span><span class="sxs-lookup"><span data-stu-id="94842-157">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-158">子オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="94842-158">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="94842-159">子オブジェクトの削除</span><span class="sxs-lookup"><span data-stu-id="94842-159">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="94842-160">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="94842-160">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="94842-161">パブリック情報に対する特別なアクセス:</span><span class="sxs-lookup"><span data-stu-id="94842-161">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-162">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="94842-162">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="94842-163">DNS ホスト名に対する特別なアクセス:</span><span class="sxs-lookup"><span data-stu-id="94842-163">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="94842-164">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="94842-164">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

