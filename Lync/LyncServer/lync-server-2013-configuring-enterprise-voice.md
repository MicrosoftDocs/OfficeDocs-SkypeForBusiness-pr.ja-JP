---
title: 'Lync Server 2013: エンタープライズ Voip の構成'
description: 'Lync Server 2013: エンタープライズ Voip の構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49a231b92bf7b04aa3466927a79258f0cbad4e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548433"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="102cd-103">Lync Server 2013 でのエンタープライズ Voip の構成</span><span class="sxs-lookup"><span data-stu-id="102cd-103">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="102cd-104">_**トピックの最終更新日:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="102cd-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="102cd-105">エンタープライズ Voip を展開するには、次のものを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="102cd-105">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="102cd-106">トランクを作成する</span><span class="sxs-lookup"><span data-stu-id="102cd-106">Create a Trunk</span></span>

  - <span data-ttu-id="102cd-107">音声ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="102cd-107">Define a Voice Policy</span></span>

  - <span data-ttu-id="102cd-108">音声ルートを定義する</span><span class="sxs-lookup"><span data-stu-id="102cd-108">Define a Voice Route</span></span>

  - <span data-ttu-id="102cd-109">エンタープライズ VoIP に対するユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="102cd-109">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="102cd-110">トランクを作成する</span><span class="sxs-lookup"><span data-stu-id="102cd-110">Create a Trunk</span></span>

<span data-ttu-id="102cd-111">エンタープライズ Voip 展開でトランクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="102cd-111">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="102cd-112">Location-Based ルーティングでは、トランクごとにトランク構成を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="102cd-112">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="102cd-113">Lync Server トポロジビルダーを使用してトランクを定義し、Lync Server Windows PowerShell コマンド、Get-cstrunkconfiguration、または Lync Server コントロールパネルを使用して、対応するトランク構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="102cd-113">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="102cd-114">トランク構成での Location-Based ルーティングを有効にする方法の詳細については、「Enable Location-Based Routing to トランク」を参照してください。このトピックでは、「Enable [Location-Based routing In Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="102cd-114">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="102cd-115">この例では、次の表は、このシナリオで使用されているトランクを示しています。</span><span class="sxs-lookup"><span data-stu-id="102cd-115">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="102cd-116">詳細については、「 [Define more トランク In Topology Builder In Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="102cd-116">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="102cd-117">トランク名</span><span class="sxs-lookup"><span data-stu-id="102cd-117">Trunk name</span></span></th>
<th><span data-ttu-id="102cd-118">システムの種類</span><span class="sxs-lookup"><span data-stu-id="102cd-118">System type</span></span></th>
<th><span data-ttu-id="102cd-119">名前</span><span class="sxs-lookup"><span data-stu-id="102cd-119">Name</span></span></th>
<th><span data-ttu-id="102cd-120">場所</span><span class="sxs-lookup"><span data-stu-id="102cd-120">Location</span></span></th>
<th><span data-ttu-id="102cd-121">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="102cd-121">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="102cd-122">トランク 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="102cd-122">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="102cd-123">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="102cd-123">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="102cd-124">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="102cd-124">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="102cd-125">デリー</span><span class="sxs-lookup"><span data-stu-id="102cd-125">Delhi</span></span></p></td>
<td><p><span data-ttu-id="102cd-126">MS1</span><span class="sxs-lookup"><span data-stu-id="102cd-126">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="102cd-127">トランク 2 HYD</span><span class="sxs-lookup"><span data-stu-id="102cd-127">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="102cd-128">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="102cd-128">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="102cd-129">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="102cd-129">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="102cd-130">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="102cd-130">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="102cd-131">MS1</span><span class="sxs-lookup"><span data-stu-id="102cd-131">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="102cd-132">トランク 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="102cd-132">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="102cd-133">PBX</span><span class="sxs-lookup"><span data-stu-id="102cd-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="102cd-134">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="102cd-134">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="102cd-135">デリー</span><span class="sxs-lookup"><span data-stu-id="102cd-135">Delhi</span></span></p></td>
<td><p><span data-ttu-id="102cd-136">MS1</span><span class="sxs-lookup"><span data-stu-id="102cd-136">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="102cd-137">トランク 4 HYD</span><span class="sxs-lookup"><span data-stu-id="102cd-137">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="102cd-138">PBX</span><span class="sxs-lookup"><span data-stu-id="102cd-138">PBX</span></span></p></td>
<td><p><span data-ttu-id="102cd-139">HYD</span><span class="sxs-lookup"><span data-stu-id="102cd-139">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="102cd-140">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="102cd-140">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="102cd-141">MS1</span><span class="sxs-lookup"><span data-stu-id="102cd-141">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="102cd-142">音声ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="102cd-142">Defines Voice Policies</span></span>

<span data-ttu-id="102cd-143">エンタープライズ Voip 展開の音声ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="102cd-143">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="102cd-144">音声ポリシーを定義して、Location-Based ルーティングを使用するために必要なサブセットだけがある場合は、ユーザーのサブセットに Location-Based ルーティング制限を適用します。</span><span class="sxs-lookup"><span data-stu-id="102cd-144">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="102cd-145">この例では、次の表に、このシナリオで使用されている音声ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="102cd-145">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="102cd-146">説明のために、Location-Based ルーティングに固有の設定のみが表に含まれています。</span><span class="sxs-lookup"><span data-stu-id="102cd-146">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="102cd-147">詳細については、「 [Lync Server 2013 で通話機能および権限を承認するための音声ポリシーと PSTN 使用法レコードの構成](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="102cd-147">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="102cd-148">音声ポリシー1</span><span class="sxs-lookup"><span data-stu-id="102cd-148">Voice policy 1</span></span></th>
<th><span data-ttu-id="102cd-149">音声ポリシー2</span><span class="sxs-lookup"><span data-stu-id="102cd-149">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="102cd-150">音声ポリシー ID</span><span class="sxs-lookup"><span data-stu-id="102cd-150">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="102cd-151">ニューデリー音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="102cd-151">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="102cd-152">Hyderabad 音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="102cd-152">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="102cd-153">PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="102cd-153">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="102cd-154">ニューデリー使用法、PBX Del usage、PBX Hyd usage</span><span class="sxs-lookup"><span data-stu-id="102cd-154">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="102cd-155">Hyderabad usage、PBX Hyd usage、PBX Del usage</span><span class="sxs-lookup"><span data-stu-id="102cd-155">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="102cd-156">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="102cd-156">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="102cd-157">False</span><span class="sxs-lookup"><span data-stu-id="102cd-157">False</span></span></p></td>
<td><p><span data-ttu-id="102cd-158">False</span><span class="sxs-lookup"><span data-stu-id="102cd-158">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="102cd-159">音声ルートを定義する</span><span class="sxs-lookup"><span data-stu-id="102cd-159">Define Voice Routes</span></span>

<span data-ttu-id="102cd-160">エンタープライズ Voip 展開の音声ルートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="102cd-160">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="102cd-161">この例では、次の表に、このシナリオで使用されている音声ルートを示します。</span><span class="sxs-lookup"><span data-stu-id="102cd-161">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="102cd-162">説明のために、Location-Based ルーティングに固有の設定のみが表に含まれています。</span><span class="sxs-lookup"><span data-stu-id="102cd-162">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="102cd-163">詳細については、「 [Lync Server 2013 で送信呼び出しの音声ルートを構成する](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="102cd-163">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="102cd-164">音声ルート1</span><span class="sxs-lookup"><span data-stu-id="102cd-164">Voice route 1</span></span></th>
<th><span data-ttu-id="102cd-165">音声ルート2</span><span class="sxs-lookup"><span data-stu-id="102cd-165">Voice route 2</span></span></th>
<th><span data-ttu-id="102cd-166">音声ルート3</span><span class="sxs-lookup"><span data-stu-id="102cd-166">Voice route 3</span></span></th>
<th><span data-ttu-id="102cd-167">ボイスルート4</span><span class="sxs-lookup"><span data-stu-id="102cd-167">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="102cd-168">名前</span><span class="sxs-lookup"><span data-stu-id="102cd-168">Name</span></span></p></td>
<td><p><span data-ttu-id="102cd-169">ニューデリー</span><span class="sxs-lookup"><span data-stu-id="102cd-169">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="102cd-170">Hyderabad ルート</span><span class="sxs-lookup"><span data-stu-id="102cd-170">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="102cd-171">PBX の Del ルート</span><span class="sxs-lookup"><span data-stu-id="102cd-171">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="102cd-172">PBX Hyd ルート</span><span class="sxs-lookup"><span data-stu-id="102cd-172">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="102cd-173">PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="102cd-173">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="102cd-174">ニューデリーの使用法</span><span class="sxs-lookup"><span data-stu-id="102cd-174">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="102cd-175">Hyderabad の使用状況</span><span class="sxs-lookup"><span data-stu-id="102cd-175">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="102cd-176">PBX の Del の使用</span><span class="sxs-lookup"><span data-stu-id="102cd-176">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="102cd-177">PBX Hyd の使用状況</span><span class="sxs-lookup"><span data-stu-id="102cd-177">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="102cd-178">樹幹</span><span class="sxs-lookup"><span data-stu-id="102cd-178">Trunk</span></span></p></td>
<td><p><span data-ttu-id="102cd-179">トランク 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="102cd-179">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="102cd-180">トランク 2 HYD</span><span class="sxs-lookup"><span data-stu-id="102cd-180">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="102cd-181">トランク 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="102cd-181">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="102cd-182">トランク 4 HYD</span><span class="sxs-lookup"><span data-stu-id="102cd-182">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="102cd-183">エンタープライズ VoIP に対するユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="102cd-183">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="102cd-184">エンタープライズ Voip に対してユーザーを有効にし、以前に定義した音声ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="102cd-184">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="102cd-185">この例では、次の表は、このシナリオで使用されている割り当てを示しています。</span><span class="sxs-lookup"><span data-stu-id="102cd-185">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="102cd-186">説明のために、Location-Based ルーティングに固有の設定のみが表に含まれています。</span><span class="sxs-lookup"><span data-stu-id="102cd-186">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="102cd-187">詳細については、「 [Lync Server 2013 のエンタープライズ voip でユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="102cd-187">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="102cd-188">ニューデリーにあるユーザー</span><span class="sxs-lookup"><span data-stu-id="102cd-188">Users located in Delhi</span></span></th>
<th><span data-ttu-id="102cd-189">Hyderabad にあるユーザー</span><span class="sxs-lookup"><span data-stu-id="102cd-189">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="102cd-190">関連付けられた音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="102cd-190">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="102cd-191">ニューデリー音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="102cd-191">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="102cd-192">Hyderabad 音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="102cd-192">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="102cd-193">サンプルユーザー</span><span class="sxs-lookup"><span data-stu-id="102cd-193">Sample users</span></span></p></td>
<td><p><span data-ttu-id="102cd-194">「DEL-LYNC-1, DEL-LYNC-2, DEL-3」</span><span class="sxs-lookup"><span data-stu-id="102cd-194">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="102cd-195">HYD-1、HYD、HYD (LYNC-3)</span><span class="sxs-lookup"><span data-stu-id="102cd-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="102cd-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="102cd-196">See Also</span></span>


[<span data-ttu-id="102cd-197">Lync Server 2013 での Location-Based ルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="102cd-197">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

