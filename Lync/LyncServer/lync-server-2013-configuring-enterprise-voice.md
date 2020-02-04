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
ms.openlocfilehash: 9d6bf9f79725f1f4812ac1e1c1c3c0e3217b939b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="ee4a4-102">Lync Server 2013 でのエンタープライズ Voip の設定</span><span class="sxs-lookup"><span data-stu-id="ee4a4-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee4a4-103">_**最終更新日:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="ee4a4-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="ee4a4-104">エンタープライズ Voip を展開するには、次の設定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="ee4a4-105">トランクを作成する</span><span class="sxs-lookup"><span data-stu-id="ee4a4-105">Create a Trunk</span></span>

  - <span data-ttu-id="ee4a4-106">ボイスポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="ee4a4-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="ee4a4-107">ボイスルートの定義</span><span class="sxs-lookup"><span data-stu-id="ee4a4-107">Define a Voice Route</span></span>

  - <span data-ttu-id="ee4a4-108">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ee4a4-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="ee4a4-109">トランクを作成する</span><span class="sxs-lookup"><span data-stu-id="ee4a4-109">Create a Trunk</span></span>

<span data-ttu-id="ee4a4-110">エンタープライズ Voip 展開で trunks を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="ee4a4-111">位置に基づくルーティングの場合、トランクごとにトランク構成を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="ee4a4-112">Lync Server Topology Builder を使用して、trunks を定義し、Lync Server Windows PowerShell コマンド、新規 Set-cstrunkconfiguration、Lync Server コントロールパネルを使用して、対応するトランク構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="ee4a4-113">トランク構成で位置情報に基づくルーティングを有効にする方法の詳細については、「 [Lync Server 2013 で位置](lync-server-2013-enabling-location-based-routing.md)情報に基づくルーティングを有効にする Trunks を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="ee4a4-114">この例では、次の表はこのシナリオで使用される trunks を示しています。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="ee4a4-115">詳細については、「 [Lync Server 2013 のトポロジビルダーで追加の trunks を定義](lync-server-2013-define-additional-trunks-in-topology-builder.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="ee4a4-116">トランク名</span><span class="sxs-lookup"><span data-stu-id="ee4a4-116">Trunk name</span></span></th>
<th><span data-ttu-id="ee4a4-117">システムの種類</span><span class="sxs-lookup"><span data-stu-id="ee4a4-117">System type</span></span></th>
<th><span data-ttu-id="ee4a4-118">名前</span><span class="sxs-lookup"><span data-stu-id="ee4a4-118">Name</span></span></th>
<th><span data-ttu-id="ee4a4-119">場所</span><span class="sxs-lookup"><span data-stu-id="ee4a4-119">Location</span></span></th>
<th><span data-ttu-id="ee4a4-120">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="ee4a4-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee4a4-121">トランク1の DEL-GW</span><span class="sxs-lookup"><span data-stu-id="ee4a4-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-122">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="ee4a4-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="ee4a4-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="ee4a4-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-125">MS1</span><span class="sxs-lookup"><span data-stu-id="ee4a4-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee4a4-126">トランク 2 HYD</span><span class="sxs-lookup"><span data-stu-id="ee4a4-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-127">PSTN ゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="ee4a4-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-128">HYD</span><span class="sxs-lookup"><span data-stu-id="ee4a4-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="ee4a4-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-130">MS1</span><span class="sxs-lookup"><span data-stu-id="ee4a4-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee4a4-131">トランク 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="ee4a4-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-132">PBX</span><span class="sxs-lookup"><span data-stu-id="ee4a4-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="ee4a4-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="ee4a4-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-135">MS1</span><span class="sxs-lookup"><span data-stu-id="ee4a4-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee4a4-136">トランク 4 HYD</span><span class="sxs-lookup"><span data-stu-id="ee4a4-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-137">PBX</span><span class="sxs-lookup"><span data-stu-id="ee4a4-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-138">HYD</span><span class="sxs-lookup"><span data-stu-id="ee4a4-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="ee4a4-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-140">MS1</span><span class="sxs-lookup"><span data-stu-id="ee4a4-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="ee4a4-141">ボイスポリシーを定義します</span><span class="sxs-lookup"><span data-stu-id="ee4a4-141">Defines Voice Policies</span></span>

<span data-ttu-id="ee4a4-142">エンタープライズ Voip の展開には、音声ポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="ee4a4-143">場所に基づくルーティングを使用するために必要なものが一部だけの場合は、ユーザーのサブセットに対して位置情報に基づくルーティング制限を適用するためのボイスポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="ee4a4-144">この例では、次の表はこのシナリオで使用される音声ポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="ee4a4-145">この表には、場所に基づくルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="ee4a4-146">詳細については、「[ボイスポリシーと PSTN 使用状況レコードを構成して、Lync Server 2013 での通話機能と特権を承認する](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="ee4a4-147">ボイスポリシー1</span><span class="sxs-lookup"><span data-stu-id="ee4a4-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="ee4a4-148">ボイスポリシー2</span><span class="sxs-lookup"><span data-stu-id="ee4a4-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee4a4-149">ボイスポリシー ID</span><span class="sxs-lookup"><span data-stu-id="ee4a4-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-150">ニューデリーのボイスポリシー</span><span class="sxs-lookup"><span data-stu-id="ee4a4-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-151">Hyderabad ボイスポリシー</span><span class="sxs-lookup"><span data-stu-id="ee4a4-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee4a4-152">PSTN の使用状況</span><span class="sxs-lookup"><span data-stu-id="ee4a4-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-153">ニューデリー使用量, PBX Del usage, PBX Hyd usage</span><span class="sxs-lookup"><span data-stu-id="ee4a4-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-154">Hyderabad usage、PBX Hyd usage、PBX Del usage</span><span class="sxs-lookup"><span data-stu-id="ee4a4-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee4a4-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="ee4a4-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-156">False</span><span class="sxs-lookup"><span data-stu-id="ee4a4-156">False</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-157">False</span><span class="sxs-lookup"><span data-stu-id="ee4a4-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="ee4a4-158">ボイスルートの定義</span><span class="sxs-lookup"><span data-stu-id="ee4a4-158">Define Voice Routes</span></span>

<span data-ttu-id="ee4a4-159">エンタープライズ Voip 展開には、ボイスルーティングを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="ee4a4-160">この例では、次の表はこのシナリオで使用されるボイスルートを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="ee4a4-161">この表には、場所に基づくルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="ee4a4-162">詳細については、「 [Lync Server 2013 で送信通話の音声ルートを構成する](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="ee4a4-163">ボイスルート1</span><span class="sxs-lookup"><span data-stu-id="ee4a4-163">Voice route 1</span></span></th>
<th><span data-ttu-id="ee4a4-164">ボイスルート2</span><span class="sxs-lookup"><span data-stu-id="ee4a4-164">Voice route 2</span></span></th>
<th><span data-ttu-id="ee4a4-165">ボイスルート3</span><span class="sxs-lookup"><span data-stu-id="ee4a4-165">Voice route 3</span></span></th>
<th><span data-ttu-id="ee4a4-166">ボイスルーティング4</span><span class="sxs-lookup"><span data-stu-id="ee4a4-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee4a4-167">名前</span><span class="sxs-lookup"><span data-stu-id="ee4a4-167">Name</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-168">ニューデリールート</span><span class="sxs-lookup"><span data-stu-id="ee4a4-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-169">Hyderabad ルート</span><span class="sxs-lookup"><span data-stu-id="ee4a4-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-170">PBX の Del ルート</span><span class="sxs-lookup"><span data-stu-id="ee4a4-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-171">PBX Hyd ルート</span><span class="sxs-lookup"><span data-stu-id="ee4a4-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee4a4-172">PSTN の使用状況</span><span class="sxs-lookup"><span data-stu-id="ee4a4-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-173">ニューデリーの利用状況</span><span class="sxs-lookup"><span data-stu-id="ee4a4-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-174">Hyderabad の使用状況</span><span class="sxs-lookup"><span data-stu-id="ee4a4-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-175">PBX の Del の利用状況</span><span class="sxs-lookup"><span data-stu-id="ee4a4-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-176">PBX Hyd の使用</span><span class="sxs-lookup"><span data-stu-id="ee4a4-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee4a4-177">トランク</span><span class="sxs-lookup"><span data-stu-id="ee4a4-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-178">トランク1の DEL-GW</span><span class="sxs-lookup"><span data-stu-id="ee4a4-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-179">トランク 2 HYD</span><span class="sxs-lookup"><span data-stu-id="ee4a4-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-180">トランク 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="ee4a4-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-181">トランク 4 HYD</span><span class="sxs-lookup"><span data-stu-id="ee4a4-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="ee4a4-182">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="ee4a4-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="ee4a4-183">エンタープライズ Voip のユーザーを有効にし、以前に定義した音声ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="ee4a4-184">この例では、次の表はこのシナリオで使用される割り当てを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="ee4a4-185">この表には、場所に基づくルーティングに固有の設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="ee4a4-186">詳細については、「 [Lync Server 2013 でエンタープライズ voip のユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee4a4-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="ee4a4-187">ニューデリーにあるユーザ</span><span class="sxs-lookup"><span data-stu-id="ee4a4-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="ee4a4-188">Hyderabad にあるユーザー</span><span class="sxs-lookup"><span data-stu-id="ee4a4-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee4a4-189">関連付けられている音声ポリシー</span><span class="sxs-lookup"><span data-stu-id="ee4a4-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-190">ニューデリーのボイスポリシー</span><span class="sxs-lookup"><span data-stu-id="ee4a4-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-191">Hyderabad ボイスポリシー</span><span class="sxs-lookup"><span data-stu-id="ee4a4-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee4a4-192">サンプルユーザー</span><span class="sxs-lookup"><span data-stu-id="ee4a4-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-193">DEL-LYNC-1、DEL-LYNC-2、DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="ee4a4-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="ee4a4-194">HYD-1、HYD、LYNC-2、HYD、LYNC-3</span><span class="sxs-lookup"><span data-stu-id="ee4a4-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ee4a4-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee4a4-195">See Also</span></span>


[<span data-ttu-id="ee4a4-196">Lync Server 2013 の場所に基づくルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="ee4a4-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

