---
title: 'Lync Server 2013: 帯域幅ポリシープロファイルの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c46ec104972eff34f73825fbb384259fc6eb4ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="55b9b-102">Lync Server 2013 での帯域幅ポリシープロファイルの作成または変更</span><span class="sxs-lookup"><span data-stu-id="55b9b-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55b9b-103">_**トピックの最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="55b9b-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="55b9b-104">帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。</span><span class="sxs-lookup"><span data-stu-id="55b9b-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="55b9b-105">Microsoft Lync Server 2013 では、オーディオおよびビデオモダリティのみに帯域幅制限を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="55b9b-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="55b9b-106">全体の帯域幅制限とセッション制限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="55b9b-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="55b9b-107">Lync Server コントロールパネルを使用して、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="55b9b-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="55b9b-108">各帯域幅ポリシー プロファイルは、1 つ以上のネットワーク サイトに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="55b9b-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="55b9b-109">帯域幅ポリシープロファイルを作成または変更するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="55b9b-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="55b9b-110">帯域幅ポリシープロファイルを削除するには、「 [Lync Server 2013 でのネットワーク帯域幅ポリシープロファイルの削除](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b9b-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="55b9b-111">新しい帯域幅ポリシープロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="55b9b-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="55b9b-112">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="55b9b-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="55b9b-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="55b9b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="55b9b-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b9b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="55b9b-115">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55b9b-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="55b9b-116">[**帯域幅ポリシー** ] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55b9b-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="55b9b-117">[**新しい帯域幅ポリシープロファイル**] で、[**名前**] フィールドに名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="55b9b-117">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="55b9b-118">この名前は、すべての帯域幅ポリシープロファイルの間で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b9b-118">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="55b9b-119">[**音声制限**] フィールドに、数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="55b9b-119">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="55b9b-120">この値は、すべてのオーディオ接続に割り当てる最大帯域幅 (kbps) で表されます。</span><span class="sxs-lookup"><span data-stu-id="55b9b-120">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="55b9b-121">[**オーディオセッション制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="55b9b-121">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="55b9b-122">この値は、個々の音声接続に割り当てる最大帯域幅 (kbps) で表されます。</span><span class="sxs-lookup"><span data-stu-id="55b9b-122">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="55b9b-123">この値は、40以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b9b-123">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="55b9b-124">[**ビデオの制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="55b9b-124">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="55b9b-125">この値は、すべてのビデオ接続に割り当てる最大帯域幅 (kbps で表されます) です。</span><span class="sxs-lookup"><span data-stu-id="55b9b-125">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="55b9b-126">[**ビデオセッション制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="55b9b-126">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="55b9b-127">この値は、個々のビデオ接続に割り当てる最大帯域幅 (kbps で表されます) です。</span><span class="sxs-lookup"><span data-stu-id="55b9b-127">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="55b9b-128">この値は、100以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b9b-128">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="55b9b-129">オプション[**説明**] フィールドに値を入力して、名前だけでは表現できないこの帯域幅ポリシープロファイルの詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="55b9b-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="55b9b-130">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55b9b-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55b9b-131">新しい帯域幅ポリシープロファイルを作成しても、帯域幅制限が自動的に適用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="55b9b-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="55b9b-132">最初にポリシープロファイルをサイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b9b-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="55b9b-133">ポリシープロファイルをサイトに関連付ける方法の詳細については、「 <A href="lync-server-2013-creating-or-modifying-network-sites.md">Lync Server 2013 でのネットワークサイトの作成または変更</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b9b-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="55b9b-134">帯域幅ポリシー プロファイルを変更するには</span><span class="sxs-lookup"><span data-stu-id="55b9b-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="55b9b-135">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="55b9b-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="55b9b-136">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="55b9b-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="55b9b-137">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b9b-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="55b9b-138">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55b9b-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="55b9b-139">[**帯域幅ポリシー**] ページで、変更する帯域幅ポリシー プロファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55b9b-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="55b9b-140">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55b9b-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="55b9b-141">[**帯域幅ポリシープロファイルの編集**] ページで、必要に応じてフィールドを変更します (詳細については、このトピックで前述した「帯域幅ポリシープロファイルを作成するには」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="55b9b-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="55b9b-142">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55b9b-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55b9b-143">帯域幅ポリシープロファイルを変更すると、この帯域幅ポリシープロファイルに関連付けられているすべてのネットワークサイトの帯域幅制限がすぐに更新されます。</span><span class="sxs-lookup"><span data-stu-id="55b9b-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55b9b-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="55b9b-144">See Also</span></span>


[<span data-ttu-id="55b9b-145">Lync Server 2013 でのネットワーク帯域幅ポリシープロファイルの削除</span><span class="sxs-lookup"><span data-stu-id="55b9b-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="55b9b-146">Lync Server 2013 で通話受付管理を構成する</span><span class="sxs-lookup"><span data-stu-id="55b9b-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="55b9b-147">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="55b9b-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="55b9b-148">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="55b9b-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="55b9b-149">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="55b9b-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

