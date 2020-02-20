---
title: 'Lync Server 2013: Grant-CsSetupPermission によって行われた変更'
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
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="77141-102">Lync Server 2013 で付与-CsSetupPermission によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="77141-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77141-103">_**トピックの最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="77141-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="77141-104">セットアップを委任するには、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサルグループに対するアクセス許可を付与します。この 2013 OU の RTCUniversalServerAdmins グループのメンバーは、指定されたdomain Admins グループのメンバーではないドメイン。</span><span class="sxs-lookup"><span data-stu-id="77141-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="77141-105">**Grant-CsSetupPermission** コマンドレットは、次の表で指定されているように、RTCUniversalServerAdmins グループに OU に対するアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="77141-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="77141-106">OU 内のオブジェクトに対して付与されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="77141-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77141-107">アクセス許可の適用先:</span><span class="sxs-lookup"><span data-stu-id="77141-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="77141-108">付与されるアクセス許可:</span><span class="sxs-lookup"><span data-stu-id="77141-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77141-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="77141-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="77141-110">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="77141-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-111">servicePrincipalName の読み込み</span><span class="sxs-lookup"><span data-stu-id="77141-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="77141-112">servicePrincipalName の書き込み</span><span class="sxs-lookup"><span data-stu-id="77141-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="77141-113">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="77141-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="77141-114">ディレクトリ変更のレプリケート</span><span class="sxs-lookup"><span data-stu-id="77141-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77141-115">子の serviceConnectionPoint オブジェクト</span><span class="sxs-lookup"><span data-stu-id="77141-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="77141-116">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="77141-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-117">アクセス許可の読み取り</span><span class="sxs-lookup"><span data-stu-id="77141-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="77141-118">アクセス許可の書き込み</span><span class="sxs-lookup"><span data-stu-id="77141-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="77141-119">子の作成</span><span class="sxs-lookup"><span data-stu-id="77141-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="77141-120">子の削除</span><span class="sxs-lookup"><span data-stu-id="77141-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="77141-121">内容の一覧表示</span><span class="sxs-lookup"><span data-stu-id="77141-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="77141-122">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="77141-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="77141-123">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="77141-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="77141-124">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="77141-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77141-125">子の msRTCSIP-Server オブジェクト</span><span class="sxs-lookup"><span data-stu-id="77141-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="77141-126">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="77141-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-127">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="77141-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="77141-128">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="77141-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="77141-129">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="77141-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77141-130">子の msRTCSIP-WebComponents オブジェクト</span><span class="sxs-lookup"><span data-stu-id="77141-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="77141-131">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="77141-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-132">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="77141-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="77141-133">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="77141-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="77141-134">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="77141-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77141-135">子の msRTCSIP-MCU オブジェクト</span><span class="sxs-lookup"><span data-stu-id="77141-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="77141-136">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="77141-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-137">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="77141-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="77141-138">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="77141-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="77141-139">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="77141-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77141-140">子の msRTCSIP-MediationServer オブジェクト</span><span class="sxs-lookup"><span data-stu-id="77141-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="77141-141">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="77141-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-142">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="77141-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="77141-143">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="77141-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="77141-144">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="77141-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77141-145">子の msRTCSIP-ApplicationServer オブジェクト</span><span class="sxs-lookup"><span data-stu-id="77141-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="77141-146">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="77141-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-147">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="77141-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="77141-148">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="77141-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="77141-149">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="77141-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77141-150">子の msRTCSIP-ConnectionPoint オブジェクト</span><span class="sxs-lookup"><span data-stu-id="77141-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="77141-151">特別なアクセス権:</span><span class="sxs-lookup"><span data-stu-id="77141-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-152">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="77141-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="77141-153">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="77141-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="77141-154">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="77141-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77141-155">子のコンピューター オブジェクト</span><span class="sxs-lookup"><span data-stu-id="77141-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="77141-156">serviceConnectionPoint に対する特別なアクセス:</span><span class="sxs-lookup"><span data-stu-id="77141-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-157">子オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="77141-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="77141-158">子オブジェクトの削除</span><span class="sxs-lookup"><span data-stu-id="77141-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="77141-159">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="77141-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="77141-160">パブリック情報に対する特別なアクセス:</span><span class="sxs-lookup"><span data-stu-id="77141-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-161">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="77141-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="77141-162">DNS ホスト名に対する特別なアクセス:</span><span class="sxs-lookup"><span data-stu-id="77141-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="77141-163">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="77141-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

