---
title: ネットワーク帯域幅ポリシー プロファイルの管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ネットワーク帯域幅ポリシー プロファイルを表示、作成、変更、または削除するには、この記事の手順を使用します。
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816447"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="89b81-103">Skype for Business Server でのネットワーク帯域幅ポリシー プロファイルの管理</span><span class="sxs-lookup"><span data-stu-id="89b81-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="89b81-104">ネットワーク帯域幅ポリシー プロファイルを表示、作成、変更、または削除するには、この記事の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="89b81-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="89b81-105">ネットワーク帯域幅ポリシーのプロファイル情報を表示する</span><span class="sxs-lookup"><span data-stu-id="89b81-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="89b81-106">帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。</span><span class="sxs-lookup"><span data-stu-id="89b81-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="89b81-107">Skype for Business Server では、音声とビデオのモダリティのみを帯域幅制限に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="89b81-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="89b81-108">全体の帯域幅制限とセッション制限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="89b81-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="89b81-109">Skype for Business Server コントロール パネルを使用して、これらのポリシーのコンテナー プロファイルを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="89b81-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="89b81-110">各帯域幅ポリシー プロファイルは、1 つ以上のネットワーク サイトに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="89b81-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="89b81-111">以下の手順に従って、帯域幅ポリシー プロファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="89b81-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="89b81-112">帯域幅ポリシーのプロファイルを表示するには</span><span class="sxs-lookup"><span data-stu-id="89b81-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="89b81-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="89b81-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89b81-114">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="89b81-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="89b81-115">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b81-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="89b81-116">[帯域幅 **ポリシー] ページ** で、表示する帯域幅ポリシー プロファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b81-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="89b81-117">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b81-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="89b81-118">ネットワーク帯域幅ポリシーのプロファイル情報を表示する (Windows PowerShellコマンドレットを使用)</span><span class="sxs-lookup"><span data-stu-id="89b81-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="89b81-119">ネットワーク帯域幅プロファイルは、このコマンドレットと Windows PowerShell使用してGet-CsNetworkBandwidthPolicyProfileできます。</span><span class="sxs-lookup"><span data-stu-id="89b81-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="89b81-120">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="89b81-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="89b81-121">ネットワーク帯域幅ポリシーのプロファイル情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="89b81-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="89b81-122">すべてのネットワーク帯域幅ポリシー プロファイルに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="89b81-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="89b81-123">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="89b81-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="89b81-124">詳細については、[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89b81-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="89b81-125">帯域幅ポリシー プロファイルを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="89b81-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="89b81-126">帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。</span><span class="sxs-lookup"><span data-stu-id="89b81-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="89b81-127">Skype for Business Server では、音声とビデオのモダリティのみを帯域幅制限に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="89b81-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="89b81-128">全体の帯域幅制限とセッション制限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="89b81-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="89b81-129">Skype for Business Server コントロール パネルを使用して、これらのポリシーのコンテナー プロファイルを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="89b81-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="89b81-130">各帯域幅ポリシー プロファイルは、1 つ以上のネットワーク サイトに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="89b81-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="89b81-131">帯域幅ポリシー プロファイルを作成または変更するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="89b81-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="89b81-132">新しい帯域幅ポリシー プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="89b81-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="89b81-133">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="89b81-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89b81-134">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="89b81-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="89b81-135">左側のナビゲーション バーで、[ **ネットワーク構成]** をクリックし、[帯域幅ポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="89b81-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="89b81-136">[帯域幅ポリシー **] ページで、[** 新規] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="89b81-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="89b81-137">[ **新しい帯域幅ポリシー プロファイル**] で、[名前] フィールドに名前 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="89b81-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="89b81-138">この名前は、すべての帯域幅ポリシー プロファイルの中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="89b81-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="89b81-139">[ **オーディオの制限] フィールド** に数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="89b81-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="89b81-140">この値は、すべてのオーディオ接続に割り当てる最大帯域幅 (kbps) です。</span><span class="sxs-lookup"><span data-stu-id="89b81-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="89b81-141">[音声セッション制限] フィールドに **数値を入力** します。</span><span class="sxs-lookup"><span data-stu-id="89b81-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="89b81-142">この値は、個々のオーディオ接続に割り当てる最大帯域幅を kbps で表します。</span><span class="sxs-lookup"><span data-stu-id="89b81-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="89b81-143">この値は 40 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="89b81-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="89b81-144">[ビデオの制限] フィールドに数値 **を入力** します。</span><span class="sxs-lookup"><span data-stu-id="89b81-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="89b81-145">この値は、すべてのビデオ接続に割り当てる最大帯域幅量を kbps で表します。</span><span class="sxs-lookup"><span data-stu-id="89b81-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="89b81-146">[ビデオ セッション制限] フィールドに **数値を入力** します。</span><span class="sxs-lookup"><span data-stu-id="89b81-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="89b81-147">この値は、個々のビデオ接続に割り当てる最大帯域幅を kbps で表します。</span><span class="sxs-lookup"><span data-stu-id="89b81-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="89b81-148">この値は 100 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="89b81-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="89b81-149">(省略可能)[説明] フィールド **に値を入力** して、名前だけでは表現できないこの帯域幅ポリシー プロファイルに関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="89b81-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="89b81-150">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b81-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="89b81-151">新しい帯域幅ポリシー プロファイルを作成しても、帯域幅制限は自動的には適用されません。</span><span class="sxs-lookup"><span data-stu-id="89b81-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="89b81-152">最初に、ポリシー プロファイルをサイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="89b81-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="89b81-153">帯域幅ポリシー プロファイルを変更するには</span><span class="sxs-lookup"><span data-stu-id="89b81-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="89b81-154">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="89b81-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89b81-155">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="89b81-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="89b81-156">左側のナビゲーション バーで、[ **ネットワーク構成]** をクリックし、[帯域幅ポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="89b81-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="89b81-157">[**帯域幅ポリシー**] ページで、変更する帯域幅ポリシー プロファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b81-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="89b81-158">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b81-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="89b81-159">[帯域幅 **ポリシー プロファイルの** 編集] ページで、必要に応じてフィールドを変更します (詳細については、「新しい帯域幅ポリシー プロファイルを作成するには」 [を参照してください](#to-create-a-new-bandwidth-policy-profile))。</span><span class="sxs-lookup"><span data-stu-id="89b81-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="89b81-160">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b81-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="89b81-161">帯域幅ポリシー プロファイルを変更すると、この帯域幅ポリシー プロファイルに関連付けられているすべてのネットワーク サイトの帯域幅制限が直ちに更新されます。</span><span class="sxs-lookup"><span data-stu-id="89b81-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="89b81-162">ネットワーク帯域幅ポリシー プロファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="89b81-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="89b81-163">帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。</span><span class="sxs-lookup"><span data-stu-id="89b81-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="89b81-164">Skype for Business Server では、音声とビデオのモダリティのみを帯域幅制限に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="89b81-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="89b81-165">全体の帯域幅制限とセッション制限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="89b81-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="89b81-166">Skype for Business Server コントロール パネルを使用して、これらのポリシーのコンテナー プロファイルを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="89b81-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="89b81-167">ネットワーク帯域幅ポリシー プロファイルを削除するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="89b81-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="89b81-168">帯域幅ポリシー プロファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="89b81-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="89b81-169">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="89b81-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89b81-170">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="89b81-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="89b81-171">左側のナビゲーション バーで、[ **ネットワーク構成]** をクリックし、[帯域幅ポリシー] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="89b81-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="89b81-172">[帯域幅 **ポリシー] ページ** で、削除する帯域幅ポリシー プロファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b81-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="89b81-173">一度に複数のプロファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="89b81-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="89b81-174">これを行うには、Ctrl キーを押しながら複数のプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="89b81-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="89b81-175">または、すべてのプロファイルを選択するには、[編集] メニューの [ **すべて** 選択] **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="89b81-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="89b81-176">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89b81-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="89b81-177">ネットワーク サイトに関連付けられている帯域幅ポリシー プロファイルを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="89b81-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="89b81-178">プロファイルを削除する前に、まずネットワーク サイトとの関連付けを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89b81-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="89b81-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="89b81-179">See Also</span></span>

[<span data-ttu-id="89b81-180">サイトの通話受付管理の管理</span><span class="sxs-lookup"><span data-stu-id="89b81-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="89b81-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="89b81-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="89b81-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="89b81-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="89b81-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="89b81-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="89b81-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="89b81-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

