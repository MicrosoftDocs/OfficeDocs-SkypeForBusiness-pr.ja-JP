---
title: 'Lync Server 2013: 場所に基づくルーティングに対するクライアントとサーバーのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="0269e-102">Lync Server 2013 での場所に基づくルーティングに対するクライアントとサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="0269e-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0269e-103">_**最終更新日:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="0269e-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="0269e-104">場所に基づくルーティングは、Lync Server によって適用されます。</span><span class="sxs-lookup"><span data-stu-id="0269e-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="0269e-105">Lync Server は、企業ネットワーク内からユーザーが接続するネットワークサイトを特定できます。</span><span class="sxs-lookup"><span data-stu-id="0269e-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="0269e-106">リモート ユーザーは企業ネットワークの外部に存在するため、リモート ユーザーの場所は不明と見なされます。</span><span class="sxs-lookup"><span data-stu-id="0269e-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="0269e-107">Lync Server のサポート</span><span class="sxs-lookup"><span data-stu-id="0269e-107">Lync Server Support</span></span>

<span data-ttu-id="0269e-108">位置情報に基づくルーティングを行うには、Lync Server 2013 CU1 が、特定のトポロジに含まれるすべてのフロントエンドプールおよび標準エディションのサーバーに展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0269e-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="0269e-109">トポロジで特定の Lync コンポーネントに Lync Server 2013 CU1 がインストールされていない場合、場所に基づくルーティングの制限を完全に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0269e-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="0269e-110">次の表は、位置情報に基づくルーティングでサポートされているサーバーの役割とバージョンの組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="0269e-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0269e-111">プールのバージョン</span><span class="sxs-lookup"><span data-stu-id="0269e-111">Pool version</span></span></th>
<th><span data-ttu-id="0269e-112">仲介サーバーのバージョン</span><span class="sxs-lookup"><span data-stu-id="0269e-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="0269e-113">サポート対象</span><span class="sxs-lookup"><span data-stu-id="0269e-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0269e-114">Lync Server 2013 (2013 年2月の累積更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="0269e-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="0269e-115">Lync Server 2013 (2013 年2月の累積更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="0269e-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="0269e-116">はい</span><span class="sxs-lookup"><span data-stu-id="0269e-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0269e-117">Lync Server 2013 (2013 年2月の累積更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="0269e-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="0269e-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0269e-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="0269e-119">いいえ</span><span class="sxs-lookup"><span data-stu-id="0269e-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0269e-120">Lync Server 2013 (2013 年2月の累積更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="0269e-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="0269e-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0269e-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="0269e-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="0269e-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0269e-123">Lync Server 2013 (2013 年2月の累積更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="0269e-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="0269e-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0269e-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="0269e-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="0269e-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0269e-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0269e-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="0269e-127">任意</span><span class="sxs-lookup"><span data-stu-id="0269e-127">any</span></span></p></td>
<td><p><span data-ttu-id="0269e-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="0269e-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0269e-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0269e-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="0269e-130">任意</span><span class="sxs-lookup"><span data-stu-id="0269e-130">any</span></span></p></td>
<td><p><span data-ttu-id="0269e-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="0269e-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0269e-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0269e-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="0269e-133">任意</span><span class="sxs-lookup"><span data-stu-id="0269e-133">any</span></span></p></td>
<td><p><span data-ttu-id="0269e-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="0269e-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="0269e-135">Lync クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="0269e-135">Lync Client Support</span></span>

<span data-ttu-id="0269e-136">次の表は、場所に基づくルーティングでサポートされているクライアントを示しています。</span><span class="sxs-lookup"><span data-stu-id="0269e-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0269e-137">クライアントの種類</span><span class="sxs-lookup"><span data-stu-id="0269e-137">Client type</span></span></th>
<th><span data-ttu-id="0269e-138">サポート対象</span><span class="sxs-lookup"><span data-stu-id="0269e-138">Supported</span></span></th>
<th><span data-ttu-id="0269e-139">詳細</span><span class="sxs-lookup"><span data-stu-id="0269e-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0269e-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0269e-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="0269e-141">はい</span><span class="sxs-lookup"><span data-stu-id="0269e-141">yes</span></span></p></td>
<td><p><span data-ttu-id="0269e-142">2013年 2 2013 月の累積更新プログラム (Lync)</span><span class="sxs-lookup"><span data-stu-id="0269e-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0269e-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0269e-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="0269e-144">はい</span><span class="sxs-lookup"><span data-stu-id="0269e-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0269e-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0269e-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="0269e-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="0269e-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0269e-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="0269e-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="0269e-148">はい</span><span class="sxs-lookup"><span data-stu-id="0269e-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0269e-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="0269e-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="0269e-150">はい</span><span class="sxs-lookup"><span data-stu-id="0269e-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0269e-151">Windows 8 版 Lync</span><span class="sxs-lookup"><span data-stu-id="0269e-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="0269e-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="0269e-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0269e-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="0269e-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="0269e-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="0269e-154">no</span></span></p></td>
<td><p><span data-ttu-id="0269e-155">場所に基づくルーティングが有効になっているユーザーが使用した場合、Lync Mobile 2013 クライアントで VoIP を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0269e-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0269e-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="0269e-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="0269e-157">はい</span><span class="sxs-lookup"><span data-stu-id="0269e-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="0269e-158">Lync Mobile 2013 クライアントで VoIP を無効にするには、位置情報に基づくルーティングが有効になっているすべてのユーザーに対して、設定、[IP Audio/ビデオ] の順に移動して、モビリティポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0269e-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="0269e-159">モビリティ ポリシーの詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0269e-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0269e-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="0269e-160">See Also</span></span>


[<span data-ttu-id="0269e-161">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="0269e-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

