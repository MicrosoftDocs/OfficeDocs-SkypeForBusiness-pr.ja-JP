---
title: 'Lync Server 2013: Location-Based ルーティングのクライアントとサーバーのサポート'
description: 'Lync Server 2013: Location-Based ルーティングのクライアントとサーバーのサポート。'
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
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549633"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="00eee-103">Lync Server 2013 での Location-Based ルーティングのクライアントとサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="00eee-103">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00eee-104">_**トピックの最終更新日:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="00eee-104">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="00eee-105">Location-Based ルーティングは、Lync Server によって適用されます。</span><span class="sxs-lookup"><span data-stu-id="00eee-105">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="00eee-106">Lync Server は、ユーザーが企業ネットワーク内から接続しているネットワークサイトを識別できます。</span><span class="sxs-lookup"><span data-stu-id="00eee-106">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="00eee-107">リモートユーザーは企業ネットワークの外部に存在するため、その場所は不明と見なされます。</span><span class="sxs-lookup"><span data-stu-id="00eee-107">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="00eee-108">Lync Server のサポート</span><span class="sxs-lookup"><span data-stu-id="00eee-108">Lync Server Support</span></span>

<span data-ttu-id="00eee-109">Location-Based ルーティングでは、Lync Server 2013 CU1 が、特定のトポロジ内のすべてのフロントエンドプールおよび Standard Edition サーバーに展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="00eee-109">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="00eee-110">トポロジ内の特定の Lync コンポーネントに Lync Server 2013 CU1 がインストールされていない場合は、Location-Based ルーティングの制限を完全に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="00eee-110">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="00eee-111">次の表は、Location-Based ルーティングに対してサポートされているサーバーの役割とバージョンの組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="00eee-111">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00eee-112">プールバージョン</span><span class="sxs-lookup"><span data-stu-id="00eee-112">Pool version</span></span></th>
<th><span data-ttu-id="00eee-113">仲介サーバーのバージョン</span><span class="sxs-lookup"><span data-stu-id="00eee-113">Mediation Server version</span></span></th>
<th><span data-ttu-id="00eee-114">サポート</span><span class="sxs-lookup"><span data-stu-id="00eee-114">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00eee-115">Lync Server 2013 年2月2013累積的な更新プログラム</span><span class="sxs-lookup"><span data-stu-id="00eee-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="00eee-116">Lync Server 2013 年2月2013累積的な更新プログラム</span><span class="sxs-lookup"><span data-stu-id="00eee-116">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="00eee-117">はい</span><span class="sxs-lookup"><span data-stu-id="00eee-117">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00eee-118">Lync Server 2013 年2月2013累積的な更新プログラム</span><span class="sxs-lookup"><span data-stu-id="00eee-118">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="00eee-119">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00eee-119">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="00eee-120">no</span><span class="sxs-lookup"><span data-stu-id="00eee-120">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00eee-121">Lync Server 2013 年2月2013累積的な更新プログラム</span><span class="sxs-lookup"><span data-stu-id="00eee-121">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="00eee-122">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="00eee-122">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="00eee-123">no</span><span class="sxs-lookup"><span data-stu-id="00eee-123">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00eee-124">Lync Server 2013 年2月2013累積的な更新プログラム</span><span class="sxs-lookup"><span data-stu-id="00eee-124">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="00eee-125">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="00eee-125">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="00eee-126">no</span><span class="sxs-lookup"><span data-stu-id="00eee-126">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00eee-127">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00eee-127">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="00eee-128">任意</span><span class="sxs-lookup"><span data-stu-id="00eee-128">any</span></span></p></td>
<td><p><span data-ttu-id="00eee-129">no</span><span class="sxs-lookup"><span data-stu-id="00eee-129">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00eee-130">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="00eee-130">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="00eee-131">任意</span><span class="sxs-lookup"><span data-stu-id="00eee-131">any</span></span></p></td>
<td><p><span data-ttu-id="00eee-132">no</span><span class="sxs-lookup"><span data-stu-id="00eee-132">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00eee-133">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="00eee-133">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="00eee-134">任意</span><span class="sxs-lookup"><span data-stu-id="00eee-134">any</span></span></p></td>
<td><p><span data-ttu-id="00eee-135">no</span><span class="sxs-lookup"><span data-stu-id="00eee-135">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="00eee-136">Lync クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="00eee-136">Lync Client Support</span></span>

<span data-ttu-id="00eee-137">次の表は Location-Based ルーティングがサポートするクライアントを示しています。</span><span class="sxs-lookup"><span data-stu-id="00eee-137">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00eee-138">クライアントの種類</span><span class="sxs-lookup"><span data-stu-id="00eee-138">Client type</span></span></th>
<th><span data-ttu-id="00eee-139">サポート</span><span class="sxs-lookup"><span data-stu-id="00eee-139">Supported</span></span></th>
<th><span data-ttu-id="00eee-140">詳細</span><span class="sxs-lookup"><span data-stu-id="00eee-140">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00eee-141">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="00eee-141">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="00eee-142">はい</span><span class="sxs-lookup"><span data-stu-id="00eee-142">yes</span></span></p></td>
<td><p><span data-ttu-id="00eee-143">Lync 2013 年2月2013の累積的な更新プログラムを含む</span><span class="sxs-lookup"><span data-stu-id="00eee-143">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00eee-144">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="00eee-144">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="00eee-145">はい</span><span class="sxs-lookup"><span data-stu-id="00eee-145">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00eee-146">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="00eee-146">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="00eee-147">no</span><span class="sxs-lookup"><span data-stu-id="00eee-147">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00eee-148">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="00eee-148">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="00eee-149">はい</span><span class="sxs-lookup"><span data-stu-id="00eee-149">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00eee-150">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="00eee-150">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="00eee-151">はい</span><span class="sxs-lookup"><span data-stu-id="00eee-151">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00eee-152">Lync for Windows 8</span><span class="sxs-lookup"><span data-stu-id="00eee-152">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="00eee-153">no</span><span class="sxs-lookup"><span data-stu-id="00eee-153">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00eee-154">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="00eee-154">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="00eee-155">no</span><span class="sxs-lookup"><span data-stu-id="00eee-155">no</span></span></p></td>
<td><p><span data-ttu-id="00eee-156">Location-Based ルーティングが有効になっているユーザーが使用する場合は、Lync Mobile 2013 クライアントで VoIP を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00eee-156">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00eee-157">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="00eee-157">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="00eee-158">はい</span><span class="sxs-lookup"><span data-stu-id="00eee-158">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="00eee-159">Lync Mobile 2013 クライアントの VoIP を無効にするには、場所に基づくルーティングが有効になっているすべてのユーザーに対して、[IP Audio/ビデオ] を設定したモビリティポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="00eee-159">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="00eee-160">モビリティポリシーの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">get-csmobilitypolicy</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00eee-160">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="00eee-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="00eee-161">See Also</span></span>


[<span data-ttu-id="00eee-162">Lync Server 2013 での Location-Based ルーティングの計画</span><span class="sxs-lookup"><span data-stu-id="00eee-162">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

