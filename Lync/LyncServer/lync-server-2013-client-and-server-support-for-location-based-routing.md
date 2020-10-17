---
title: 'Lync Server 2013: Location-Based ルーティングのクライアントとサーバーのサポート'
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
ms.openlocfilehash: d85e2ce1738ee5de9d4d542cedd7a9e544771938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529344"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="4f052-102">Lync Server 2013 での Location-Based ルーティングのクライアントとサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="4f052-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f052-103">_**トピックの最終更新日:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="4f052-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="4f052-104">Location-Based ルーティングは、Lync Server によって適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f052-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="4f052-105">Lync Server は、ユーザーが企業ネットワーク内から接続しているネットワークサイトを識別できます。</span><span class="sxs-lookup"><span data-stu-id="4f052-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="4f052-106">リモートユーザーは企業ネットワークの外部に存在するため、その場所は不明と見なされます。</span><span class="sxs-lookup"><span data-stu-id="4f052-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="4f052-107">Lync Server のサポート</span><span class="sxs-lookup"><span data-stu-id="4f052-107">Lync Server Support</span></span>

<span data-ttu-id="4f052-108">Location-Based ルーティングでは、Lync Server 2013 CU1 が、特定のトポロジ内のすべてのフロントエンドプールおよび Standard Edition サーバーに展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f052-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="4f052-109">トポロジ内の特定の Lync コンポーネントに Lync Server 2013 CU1 がインストールされていない場合は、Location-Based ルーティングの制限を完全に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f052-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="4f052-110">次の表は、Location-Based ルーティングに対してサポートされているサーバーの役割とバージョンの組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="4f052-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f052-111">プールバージョン</span><span class="sxs-lookup"><span data-stu-id="4f052-111">Pool version</span></span></th>
<th><span data-ttu-id="4f052-112">仲介サーバーのバージョン</span><span class="sxs-lookup"><span data-stu-id="4f052-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="4f052-113">サポート</span><span class="sxs-lookup"><span data-stu-id="4f052-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f052-114">Lync Server 2013 年2月2013累積的な更新プログラム</span><span class="sxs-lookup"><span data-stu-id="4f052-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4f052-115">Lync Server 2013 年2月2013累積的な更新プログラム</span><span class="sxs-lookup"><span data-stu-id="4f052-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4f052-116">はい</span><span class="sxs-lookup"><span data-stu-id="4f052-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f052-117">Lync Server 2013 年2月2013累積的な更新プログラム</span><span class="sxs-lookup"><span data-stu-id="4f052-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4f052-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f052-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="4f052-119">no</span><span class="sxs-lookup"><span data-stu-id="4f052-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f052-120">Lync Server 2013 年2月2013累積的な更新プログラム</span><span class="sxs-lookup"><span data-stu-id="4f052-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4f052-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4f052-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="4f052-122">no</span><span class="sxs-lookup"><span data-stu-id="4f052-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f052-123">Lync Server 2013 年2月2013累積的な更新プログラム</span><span class="sxs-lookup"><span data-stu-id="4f052-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4f052-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4f052-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="4f052-125">no</span><span class="sxs-lookup"><span data-stu-id="4f052-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f052-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f052-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="4f052-127">任意</span><span class="sxs-lookup"><span data-stu-id="4f052-127">any</span></span></p></td>
<td><p><span data-ttu-id="4f052-128">no</span><span class="sxs-lookup"><span data-stu-id="4f052-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f052-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4f052-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="4f052-130">任意</span><span class="sxs-lookup"><span data-stu-id="4f052-130">any</span></span></p></td>
<td><p><span data-ttu-id="4f052-131">no</span><span class="sxs-lookup"><span data-stu-id="4f052-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f052-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4f052-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="4f052-133">任意</span><span class="sxs-lookup"><span data-stu-id="4f052-133">any</span></span></p></td>
<td><p><span data-ttu-id="4f052-134">no</span><span class="sxs-lookup"><span data-stu-id="4f052-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="4f052-135">Lync クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="4f052-135">Lync Client Support</span></span>

<span data-ttu-id="4f052-136">次の表は Location-Based ルーティングがサポートするクライアントを示しています。</span><span class="sxs-lookup"><span data-stu-id="4f052-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f052-137">クライアントの種類</span><span class="sxs-lookup"><span data-stu-id="4f052-137">Client type</span></span></th>
<th><span data-ttu-id="4f052-138">サポート</span><span class="sxs-lookup"><span data-stu-id="4f052-138">Supported</span></span></th>
<th><span data-ttu-id="4f052-139">詳細</span><span class="sxs-lookup"><span data-stu-id="4f052-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f052-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="4f052-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="4f052-141">はい</span><span class="sxs-lookup"><span data-stu-id="4f052-141">yes</span></span></p></td>
<td><p><span data-ttu-id="4f052-142">Lync 2013 年2月2013の累積的な更新プログラムを含む</span><span class="sxs-lookup"><span data-stu-id="4f052-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f052-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="4f052-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="4f052-144">はい</span><span class="sxs-lookup"><span data-stu-id="4f052-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f052-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4f052-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="4f052-146">no</span><span class="sxs-lookup"><span data-stu-id="4f052-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f052-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="4f052-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="4f052-148">はい</span><span class="sxs-lookup"><span data-stu-id="4f052-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f052-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="4f052-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="4f052-150">はい</span><span class="sxs-lookup"><span data-stu-id="4f052-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f052-151">Lync for Windows 8</span><span class="sxs-lookup"><span data-stu-id="4f052-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="4f052-152">no</span><span class="sxs-lookup"><span data-stu-id="4f052-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f052-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="4f052-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="4f052-154">no</span><span class="sxs-lookup"><span data-stu-id="4f052-154">no</span></span></p></td>
<td><p><span data-ttu-id="4f052-155">Location-Based ルーティングが有効になっているユーザーが使用する場合は、Lync Mobile 2013 クライアントで VoIP を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f052-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f052-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="4f052-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="4f052-157">はい</span><span class="sxs-lookup"><span data-stu-id="4f052-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="4f052-158">Lync Mobile 2013 クライアントの VoIP を無効にするには、場所に基づくルーティングが有効になっているすべてのユーザーに対して、[IP Audio/ビデオ] を設定したモビリティポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4f052-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="4f052-159">モビリティポリシーの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">get-csmobilitypolicy</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f052-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f052-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f052-160">See Also</span></span>


[<span data-ttu-id="4f052-161">Lync Server 2013 での Location-Based ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="4f052-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

