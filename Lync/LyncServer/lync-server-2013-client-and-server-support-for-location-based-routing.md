---
title: 'Lync Server 2013: 場所に基づくルーティングに対するクライアントとサーバーのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="fa528-102">Lync Server 2013 での場所に基づくルーティングに対するクライアントとサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="fa528-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa528-103">_**最終更新日:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="fa528-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="fa528-104">場所に基づくルーティングは、Lync Server によって適用されます。</span><span class="sxs-lookup"><span data-stu-id="fa528-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="fa528-105">Lync Server は、企業ネットワーク内からユーザーが接続するネットワークサイトを特定できます。</span><span class="sxs-lookup"><span data-stu-id="fa528-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="fa528-106">リモート ユーザーは企業ネットワークの外部に存在するため、リモート ユーザーの場所は不明と見なされます。</span><span class="sxs-lookup"><span data-stu-id="fa528-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="fa528-107">Lync Server のサポート</span><span class="sxs-lookup"><span data-stu-id="fa528-107">Lync Server Support</span></span>

<span data-ttu-id="fa528-108">位置情報に基づくルーティングを行うには、Lync Server 2013 CU1 が、特定のトポロジに含まれるすべてのフロントエンドプールおよび標準エディションのサーバーに展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa528-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="fa528-109">トポロジで特定の Lync コンポーネントに Lync Server 2013 CU1 がインストールされていない場合、場所に基づくルーティングの制限を完全に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa528-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="fa528-110">次の表は、位置情報に基づくルーティングでサポートされているサーバーの役割とバージョンの組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="fa528-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa528-111">プールのバージョン</span><span class="sxs-lookup"><span data-stu-id="fa528-111">Pool version</span></span></th>
<th><span data-ttu-id="fa528-112">仲介サーバーのバージョン</span><span class="sxs-lookup"><span data-stu-id="fa528-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="fa528-113">サポート対象</span><span class="sxs-lookup"><span data-stu-id="fa528-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa528-114">Lync Server 2013 (2013 年2月の累積更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="fa528-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="fa528-115">Lync Server 2013 (2013 年2月の累積更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="fa528-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="fa528-116">はい</span><span class="sxs-lookup"><span data-stu-id="fa528-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa528-117">Lync Server 2013 (2013 年2月の累積更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="fa528-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="fa528-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa528-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="fa528-119">いいえ</span><span class="sxs-lookup"><span data-stu-id="fa528-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa528-120">Lync Server 2013 (2013 年2月の累積更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="fa528-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="fa528-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fa528-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="fa528-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="fa528-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa528-123">Lync Server 2013 (2013 年2月の累積更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="fa528-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="fa528-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="fa528-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="fa528-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="fa528-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa528-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa528-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="fa528-127">任意</span><span class="sxs-lookup"><span data-stu-id="fa528-127">any</span></span></p></td>
<td><p><span data-ttu-id="fa528-128">いいえ</span><span class="sxs-lookup"><span data-stu-id="fa528-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa528-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fa528-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="fa528-130">任意</span><span class="sxs-lookup"><span data-stu-id="fa528-130">any</span></span></p></td>
<td><p><span data-ttu-id="fa528-131">いいえ</span><span class="sxs-lookup"><span data-stu-id="fa528-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa528-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="fa528-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="fa528-133">任意</span><span class="sxs-lookup"><span data-stu-id="fa528-133">any</span></span></p></td>
<td><p><span data-ttu-id="fa528-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="fa528-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="fa528-135">Lync クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="fa528-135">Lync Client Support</span></span>

<span data-ttu-id="fa528-136">次の表は、場所に基づくルーティングでサポートされているクライアントを示しています。</span><span class="sxs-lookup"><span data-stu-id="fa528-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa528-137">クライアントの種類</span><span class="sxs-lookup"><span data-stu-id="fa528-137">Client type</span></span></th>
<th><span data-ttu-id="fa528-138">サポート対象</span><span class="sxs-lookup"><span data-stu-id="fa528-138">Supported</span></span></th>
<th><span data-ttu-id="fa528-139">詳細</span><span class="sxs-lookup"><span data-stu-id="fa528-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa528-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="fa528-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="fa528-141">はい</span><span class="sxs-lookup"><span data-stu-id="fa528-141">yes</span></span></p></td>
<td><p><span data-ttu-id="fa528-142">2013年 2 2013 月の累積更新プログラム (Lync)</span><span class="sxs-lookup"><span data-stu-id="fa528-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa528-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="fa528-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="fa528-144">はい</span><span class="sxs-lookup"><span data-stu-id="fa528-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa528-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="fa528-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="fa528-146">いいえ</span><span class="sxs-lookup"><span data-stu-id="fa528-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa528-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="fa528-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="fa528-148">はい</span><span class="sxs-lookup"><span data-stu-id="fa528-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa528-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="fa528-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="fa528-150">はい</span><span class="sxs-lookup"><span data-stu-id="fa528-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa528-151">Windows 8 版 Lync</span><span class="sxs-lookup"><span data-stu-id="fa528-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="fa528-152">いいえ</span><span class="sxs-lookup"><span data-stu-id="fa528-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa528-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="fa528-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="fa528-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="fa528-154">no</span></span></p></td>
<td><p><span data-ttu-id="fa528-155">場所に基づくルーティングが有効になっているユーザーが使用した場合、Lync Mobile 2013 クライアントで VoIP を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa528-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa528-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="fa528-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="fa528-157">はい</span><span class="sxs-lookup"><span data-stu-id="fa528-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="fa528-158">Lync Mobile 2013 クライアントで VoIP を無効にするには、位置情報に基づくルーティングが有効になっているすべてのユーザーに対して、設定、[IP Audio/ビデオ] の順に移動して、モビリティポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fa528-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="fa528-159">モビリティ ポリシーの詳細については、「<A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa528-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fa528-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa528-160">See Also</span></span>


[<span data-ttu-id="fa528-161">Lync Server 2013 での場所に基づくルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="fa528-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

