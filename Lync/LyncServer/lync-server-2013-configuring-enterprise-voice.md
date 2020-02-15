---
title: 'Lync Server 2013: エンタープライズ Voip の構成'
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
ms.openlocfilehash: 76105b9bee5ce35801196b5a4cd20b2a1feed3e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="6d92d-102">Lync Server 2013 でのエンタープライズ Voip の構成</span><span class="sxs-lookup"><span data-stu-id="6d92d-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d92d-103">_**トピックの最終更新日:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="6d92d-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="6d92d-104">エンタープライズ Voip を展開するには、次のものを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d92d-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="6d92d-105">トランクを作成する</span><span class="sxs-lookup"><span data-stu-id="6d92d-105">Create a Trunk</span></span>

  - <span data-ttu-id="6d92d-106">音声ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="6d92d-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="6d92d-107">音声ルートを定義する</span><span class="sxs-lookup"><span data-stu-id="6d92d-107">Define a Voice Route</span></span>

  - <span data-ttu-id="6d92d-108">エンタープライズ VoIP に対するユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="6d92d-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="6d92d-109">トランクを作成する</span><span class="sxs-lookup"><span data-stu-id="6d92d-109">Create a Trunk</span></span>

<span data-ttu-id="6d92d-110">エンタープライズ Voip 展開でトランクを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d92d-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="6d92d-111">場所に基づくルーティングの場合は、トランクごとにトランク構成を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d92d-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="6d92d-112">Lync Server トポロジビルダーを使用してトランクを定義し、Lync Server Windows PowerShell コマンド、Get-cstrunkconfiguration、または Lync Server コントロールパネルを使用して、対応するトランク構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="6d92d-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="6d92d-113">トランク構成での場所に基づくルーティングを有効にする方法については、「トランクへの場所に基づくルーティングを有効にする」を参照してください。詳細については、トピック「 [Lync Server 2013 での場所に基づくルーティングの有効化](lync-server-2013-enabling-location-based-routing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d92d-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="6d92d-114">この例では、次の表は、このシナリオで使用されているトランクを示しています。</span><span class="sxs-lookup"><span data-stu-id="6d92d-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="6d92d-115">詳細については、「 [Define more トランク In Topology Builder In Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d92d-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="6d92d-116">トランク名</span><span class="sxs-lookup"><span data-stu-id="6d92d-116">Trunk name</span></span></th>
<th><span data-ttu-id="6d92d-117">システムの種類</span><span class="sxs-lookup"><span data-stu-id="6d92d-117">System type</span></span></th>
<th><span data-ttu-id="6d92d-118">名前</span><span class="sxs-lookup"><span data-stu-id="6d92d-118">Name</span></span></th>
<th><span data-ttu-id="6d92d-119">場所</span><span class="sxs-lookup"><span data-stu-id="6d92d-119">Location</span></span></th>
<th><span data-ttu-id="6d92d-120">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="6d92d-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d92d-121">トランク 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="6d92d-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="6d92d-122">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="6d92d-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="6d92d-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="6d92d-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="6d92d-124">デリー</span><span class="sxs-lookup"><span data-stu-id="6d92d-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="6d92d-125">MS1</span><span class="sxs-lookup"><span data-stu-id="6d92d-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d92d-126">トランク 2 HYD</span><span class="sxs-lookup"><span data-stu-id="6d92d-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="6d92d-127">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="6d92d-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="6d92d-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="6d92d-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="6d92d-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6d92d-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="6d92d-130">MS1</span><span class="sxs-lookup"><span data-stu-id="6d92d-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d92d-131">トランク 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="6d92d-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="6d92d-132">PBX</span><span class="sxs-lookup"><span data-stu-id="6d92d-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="6d92d-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="6d92d-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="6d92d-134">デリー</span><span class="sxs-lookup"><span data-stu-id="6d92d-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="6d92d-135">MS1</span><span class="sxs-lookup"><span data-stu-id="6d92d-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d92d-136">トランク 4 HYD</span><span class="sxs-lookup"><span data-stu-id="6d92d-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="6d92d-137">PBX</span><span class="sxs-lookup"><span data-stu-id="6d92d-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="6d92d-138">HYD</span><span class="sxs-lookup"><span data-stu-id="6d92d-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="6d92d-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6d92d-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="6d92d-140">MS1</span><span class="sxs-lookup"><span data-stu-id="6d92d-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="6d92d-141">音声ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="6d92d-141">Defines Voice Policies</span></span>

<span data-ttu-id="6d92d-142">エンタープライズ Voip 展開の音声ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d92d-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="6d92d-143">場所に基づくルーティングを使用するために必要なサブセットだけがある場合は、ユーザーのサブセットに対して場所ベースのルーティング制限を強制する音声ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="6d92d-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="6d92d-144">この例では、次の表に、このシナリオで使用されている音声ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="6d92d-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="6d92d-145">説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d92d-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="6d92d-146">詳細については、「 [Lync Server 2013 で通話機能および権限を承認するための音声ポリシーと PSTN 使用法レコードの構成](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d92d-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="6d92d-147">音声ポリシー1</span><span class="sxs-lookup"><span data-stu-id="6d92d-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="6d92d-148">音声ポリシー2</span><span class="sxs-lookup"><span data-stu-id="6d92d-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d92d-149">音声ポリシー ID</span><span class="sxs-lookup"><span data-stu-id="6d92d-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="6d92d-150">ニューデリー音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="6d92d-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="6d92d-151">Hyderabad 音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="6d92d-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d92d-152">PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="6d92d-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="6d92d-153">ニューデリー使用法、PBX Del usage、PBX Hyd usage</span><span class="sxs-lookup"><span data-stu-id="6d92d-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="6d92d-154">Hyderabad usage、PBX Hyd usage、PBX Del usage</span><span class="sxs-lookup"><span data-stu-id="6d92d-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d92d-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="6d92d-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="6d92d-156">False</span><span class="sxs-lookup"><span data-stu-id="6d92d-156">False</span></span></p></td>
<td><p><span data-ttu-id="6d92d-157">False</span><span class="sxs-lookup"><span data-stu-id="6d92d-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="6d92d-158">音声ルートを定義する</span><span class="sxs-lookup"><span data-stu-id="6d92d-158">Define Voice Routes</span></span>

<span data-ttu-id="6d92d-159">エンタープライズ Voip 展開の音声ルートを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d92d-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="6d92d-160">この例では、次の表に、このシナリオで使用されている音声ルートを示します。</span><span class="sxs-lookup"><span data-stu-id="6d92d-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="6d92d-161">説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d92d-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="6d92d-162">詳細については、「 [Lync Server 2013 で送信呼び出しの音声ルートを構成する](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d92d-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="6d92d-163">音声ルート1</span><span class="sxs-lookup"><span data-stu-id="6d92d-163">Voice route 1</span></span></th>
<th><span data-ttu-id="6d92d-164">音声ルート2</span><span class="sxs-lookup"><span data-stu-id="6d92d-164">Voice route 2</span></span></th>
<th><span data-ttu-id="6d92d-165">音声ルート3</span><span class="sxs-lookup"><span data-stu-id="6d92d-165">Voice route 3</span></span></th>
<th><span data-ttu-id="6d92d-166">ボイスルート4</span><span class="sxs-lookup"><span data-stu-id="6d92d-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d92d-167">名前</span><span class="sxs-lookup"><span data-stu-id="6d92d-167">Name</span></span></p></td>
<td><p><span data-ttu-id="6d92d-168">ニューデリー</span><span class="sxs-lookup"><span data-stu-id="6d92d-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="6d92d-169">Hyderabad ルート</span><span class="sxs-lookup"><span data-stu-id="6d92d-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="6d92d-170">PBX の Del ルート</span><span class="sxs-lookup"><span data-stu-id="6d92d-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="6d92d-171">PBX Hyd ルート</span><span class="sxs-lookup"><span data-stu-id="6d92d-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d92d-172">PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="6d92d-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="6d92d-173">ニューデリーの使用法</span><span class="sxs-lookup"><span data-stu-id="6d92d-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="6d92d-174">Hyderabad の使用状況</span><span class="sxs-lookup"><span data-stu-id="6d92d-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="6d92d-175">PBX の Del の使用</span><span class="sxs-lookup"><span data-stu-id="6d92d-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="6d92d-176">PBX Hyd の使用状況</span><span class="sxs-lookup"><span data-stu-id="6d92d-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d92d-177">樹幹</span><span class="sxs-lookup"><span data-stu-id="6d92d-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="6d92d-178">トランク 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="6d92d-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="6d92d-179">トランク 2 HYD</span><span class="sxs-lookup"><span data-stu-id="6d92d-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="6d92d-180">トランク 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="6d92d-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="6d92d-181">トランク 4 HYD</span><span class="sxs-lookup"><span data-stu-id="6d92d-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="6d92d-182">エンタープライズ VoIP に対するユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="6d92d-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="6d92d-183">エンタープライズ Voip に対してユーザーを有効にし、以前に定義した音声ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6d92d-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="6d92d-184">この例では、次の表は、このシナリオで使用されている割り当てを示しています。</span><span class="sxs-lookup"><span data-stu-id="6d92d-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="6d92d-185">説明のため、表には場所に基づいたルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d92d-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="6d92d-186">詳細については、「 [Lync Server 2013 のエンタープライズ voip でユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d92d-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="6d92d-187">ニューデリーにあるユーザー</span><span class="sxs-lookup"><span data-stu-id="6d92d-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="6d92d-188">Hyderabad にあるユーザー</span><span class="sxs-lookup"><span data-stu-id="6d92d-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d92d-189">関連付けられた音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="6d92d-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="6d92d-190">ニューデリー音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="6d92d-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="6d92d-191">Hyderabad 音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="6d92d-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d92d-192">サンプルユーザー</span><span class="sxs-lookup"><span data-stu-id="6d92d-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="6d92d-193">「DEL-LYNC-1, DEL-LYNC-2, DEL-3」</span><span class="sxs-lookup"><span data-stu-id="6d92d-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="6d92d-194">HYD-1、HYD、HYD (LYNC-3)</span><span class="sxs-lookup"><span data-stu-id="6d92d-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6d92d-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d92d-195">See Also</span></span>


[<span data-ttu-id="6d92d-196">Lync Server 2013 での場所に基づくルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="6d92d-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

