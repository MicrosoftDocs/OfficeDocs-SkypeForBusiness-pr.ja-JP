---
title: 'Lync Server 2013: Grant-CsSetupPermission による変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc63cf814f2bd901ab9753fe0f4501e7f44e2189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="471c2-102">Lync Server 2013 での権限の付与によって行われる変更</span><span class="sxs-lookup"><span data-stu-id="471c2-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="471c2-103">_**最終更新日:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="471c2-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="471c2-104">設定を委任するには、特定の Active Directory 組織単位 (OU) に対して RTCUniversalServerAdmins ユニバーサルグループへのアクセス許可を付与し、その OU の RTCUniversalServerAdmins グループのメンバーが指定した Lync Server 2013 をインストールできるようにすることができます。domain Admins グループのメンバーになりません。</span><span class="sxs-lookup"><span data-stu-id="471c2-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="471c2-105">**グラント setuppermissions**コマンドレットは、次の表で指定されているように、OU に対して RTCUniversalServerAdmins group アクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="471c2-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="471c2-106">OU 内のオブジェクトに付与されているアクセス許可</span><span class="sxs-lookup"><span data-stu-id="471c2-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="471c2-107">権限の対象:</span><span class="sxs-lookup"><span data-stu-id="471c2-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="471c2-108">付与されるアクセス許可:</span><span class="sxs-lookup"><span data-stu-id="471c2-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="471c2-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="471c2-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="471c2-110">特殊なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-111">ServicePrincipalName を読み上げる</span><span class="sxs-lookup"><span data-stu-id="471c2-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="471c2-112">ServicePrincipalName の書き込み</span><span class="sxs-lookup"><span data-stu-id="471c2-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="471c2-113">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="471c2-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="471c2-114">ディレクトリの変更の複製</span><span class="sxs-lookup"><span data-stu-id="471c2-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="471c2-115">子孫の serviceConnectionPoint オブジェクト</span><span class="sxs-lookup"><span data-stu-id="471c2-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="471c2-116">特殊なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-117">読み取りアクセス許可</span><span class="sxs-lookup"><span data-stu-id="471c2-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="471c2-118">書き込み権限</span><span class="sxs-lookup"><span data-stu-id="471c2-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="471c2-119">子の作成</span><span class="sxs-lookup"><span data-stu-id="471c2-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="471c2-120">子の削除</span><span class="sxs-lookup"><span data-stu-id="471c2-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="471c2-121">リストの内容</span><span class="sxs-lookup"><span data-stu-id="471c2-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="471c2-122">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="471c2-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="471c2-123">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="471c2-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="471c2-124">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="471c2-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="471c2-125">下位の Msrtcsip-userenabled true オブジェクト</span><span class="sxs-lookup"><span data-stu-id="471c2-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="471c2-126">特殊なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-127">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="471c2-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="471c2-128">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="471c2-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="471c2-129">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="471c2-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="471c2-130">下位の Msrtcsip-userenabled true-WebComponents オブジェクト</span><span class="sxs-lookup"><span data-stu-id="471c2-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="471c2-131">特殊なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-132">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="471c2-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="471c2-133">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="471c2-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="471c2-134">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="471c2-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="471c2-135">子孫の Msrtcsip-userenabled true-MCU オブジェクト</span><span class="sxs-lookup"><span data-stu-id="471c2-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="471c2-136">特殊なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-137">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="471c2-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="471c2-138">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="471c2-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="471c2-139">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="471c2-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="471c2-140">子孫の Msrtcsip-userenabled true-MediationServer オブジェクト</span><span class="sxs-lookup"><span data-stu-id="471c2-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="471c2-141">特殊なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-142">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="471c2-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="471c2-143">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="471c2-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="471c2-144">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="471c2-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="471c2-145">子 Msrtcsip-userenabled true ApplicationServer オブジェクト</span><span class="sxs-lookup"><span data-stu-id="471c2-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="471c2-146">特殊なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-147">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="471c2-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="471c2-148">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="471c2-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="471c2-149">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="471c2-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="471c2-150">子 Msrtcsip-userenabled true ConnectionPoint オブジェクト</span><span class="sxs-lookup"><span data-stu-id="471c2-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="471c2-151">特殊なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-152">プロパティの書き込み</span><span class="sxs-lookup"><span data-stu-id="471c2-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="471c2-153">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="471c2-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="471c2-154">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="471c2-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="471c2-155">子コンピューターオブジェクト</span><span class="sxs-lookup"><span data-stu-id="471c2-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="471c2-156">ServiceConnectionPoint の特殊なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-157">子オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="471c2-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="471c2-158">子オブジェクトを削除する</span><span class="sxs-lookup"><span data-stu-id="471c2-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="471c2-159">ツリーの削除</span><span class="sxs-lookup"><span data-stu-id="471c2-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="471c2-160">パブリック情報への特別なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-161">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="471c2-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="471c2-162">DNS ホスト名の特殊なアクセス:</span><span class="sxs-lookup"><span data-stu-id="471c2-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="471c2-163">プロパティの読み取り</span><span class="sxs-lookup"><span data-stu-id="471c2-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

