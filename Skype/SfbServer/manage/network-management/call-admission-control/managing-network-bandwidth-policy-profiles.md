---
title: ネットワーク帯域幅ポリシープロファイルの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ネットワーク帯域幅ポリシープロファイルを表示、作成、変更、または削除するには、この記事の手順を使用します。
ms.openlocfilehash: 3b2b62e5e823a9d86f1884d79b67483bce38a39f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279523"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="291bb-103">Skype for Business Server でのネットワーク帯域幅ポリシー プロファイルの管理</span><span class="sxs-lookup"><span data-stu-id="291bb-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="291bb-104">ネットワーク帯域幅ポリシープロファイルを表示、作成、変更、または削除するには、この記事の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="291bb-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="291bb-105">ネットワーク帯域幅ポリシーのプロファイル情報を表示する</span><span class="sxs-lookup"><span data-stu-id="291bb-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="291bb-106">通話受付制御 (CAC) の一部として、帯域幅ポリシーを使って、特定のモダリティの帯域幅の制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="291bb-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="291bb-107">Skype for Business Server では、オーディオとビデオのモダリティのみに帯域幅の制限を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="291bb-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="291bb-108">全体的な帯域幅の制限とセッションの制限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="291bb-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="291bb-109">Skype for Business Server コントロールパネルを使って、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="291bb-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="291bb-110">各帯域幅ポリシーのプロファイルは、1つ以上のネットワークサイトに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="291bb-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="291bb-111">帯域幅ポリシーのプロファイルを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="291bb-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="291bb-112">帯域幅ポリシーのプロファイルを表示するには</span><span class="sxs-lookup"><span data-stu-id="291bb-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="291bb-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="291bb-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="291bb-114">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="291bb-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="291bb-115">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="291bb-116">[**帯域幅ポリシー** ] ページで、表示する帯域幅ポリシープロファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="291bb-117">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="291bb-118">Windows PowerShell コマンドレットを使用してネットワーク帯域幅ポリシーのプロファイル情報を表示する</span><span class="sxs-lookup"><span data-stu-id="291bb-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="291bb-119">ネットワーク帯域幅プロファイルを表示するには、Windows PowerShell と CsNetworkBandwidthPolicyProfile コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="291bb-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="291bb-120">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="291bb-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="291bb-121">ネットワーク帯域幅ポリシーのプロファイル情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="291bb-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="291bb-122">すべてのネットワーク帯域幅ポリシープロファイルに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="291bb-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="291bb-123">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="291bb-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="291bb-124">詳細については、 [CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="291bb-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="291bb-125">帯域幅ポリシープロファイルを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="291bb-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="291bb-126">通話受付制御 (CAC) の一部として、帯域幅ポリシーを使って、特定のモダリティの帯域幅の制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="291bb-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="291bb-127">Skype for Business Server では、オーディオとビデオのモダリティのみに帯域幅の制限を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="291bb-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="291bb-128">全体的な帯域幅の制限とセッションの制限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="291bb-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="291bb-129">Skype for Business Server コントロールパネルを使って、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="291bb-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="291bb-130">各帯域幅ポリシーのプロファイルは、1つ以上のネットワークサイトに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="291bb-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="291bb-131">帯域幅ポリシープロファイルを作成または変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="291bb-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="291bb-132">新しい帯域幅ポリシープロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="291bb-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="291bb-133">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="291bb-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="291bb-134">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="291bb-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="291bb-135">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="291bb-136">[**帯域幅ポリシー** ] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="291bb-137">**新しい帯域幅ポリシープロファイル**で、[**名前**] フィールドに名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="291bb-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="291bb-138">この名前は、すべての帯域幅ポリシープロファイルの間で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="291bb-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="291bb-139">[**オーディオ制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="291bb-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="291bb-140">この値は、すべてのオーディオ接続に割り当てることができる最大帯域幅です。 kbps で表されます。</span><span class="sxs-lookup"><span data-stu-id="291bb-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="291bb-141">[**オーディオセッションの制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="291bb-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="291bb-142">この値は、個々の音声接続に割り当てられる帯域幅の上限です。 kbps で表されます。</span><span class="sxs-lookup"><span data-stu-id="291bb-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="291bb-143">この値は40以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="291bb-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="291bb-144">[**ビデオの制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="291bb-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="291bb-145">この値は、すべてのビデオ接続に割り当てることができる最大帯域幅です。 kbps で表されます。</span><span class="sxs-lookup"><span data-stu-id="291bb-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="291bb-146">[**ビデオセッションの制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="291bb-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="291bb-147">この値は、個々のビデオ接続に割り当てることができる最大帯域幅です。 kbps で表されます。</span><span class="sxs-lookup"><span data-stu-id="291bb-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="291bb-148">この値は100以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="291bb-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="291bb-149">省略[**説明**] フィールドに値を入力して、この帯域幅ポリシープロファイルの詳細情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="291bb-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="291bb-150">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="291bb-151">新しい帯域幅ポリシープロファイルを作成しても、帯域幅の制限は自動的に適用されません。</span><span class="sxs-lookup"><span data-stu-id="291bb-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="291bb-152">最初にポリシープロファイルをサイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="291bb-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="291bb-153">帯域幅ポリシーのプロファイルを変更するには</span><span class="sxs-lookup"><span data-stu-id="291bb-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="291bb-154">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="291bb-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="291bb-155">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="291bb-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="291bb-156">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="291bb-157">[**帯域幅ポリシー** ] ページで、変更する帯域幅ポリシープロファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="291bb-158">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="291bb-159">[**帯域幅ポリシープロファイルの編集**] ページで、必要に応じてフィールドを変更します (詳細については、「[新しい帯域幅ポリシープロファイルを作成する」を](#to-create-a-new-bandwidth-policy-profile)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="291bb-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="291bb-160">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="291bb-161">帯域幅ポリシーのプロファイルを変更すると、この帯域幅ポリシープロファイルに関連付けられたすべてのネットワークサイトの帯域幅の制限がすぐに更新されます。</span><span class="sxs-lookup"><span data-stu-id="291bb-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="291bb-162">ネットワーク帯域幅ポリシープロファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="291bb-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="291bb-163">通話受付制御 (CAC) の一部として、帯域幅ポリシーを使って、特定のモダリティの帯域幅の制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="291bb-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="291bb-164">Skype for Business Server では、オーディオとビデオのモダリティのみに帯域幅の制限を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="291bb-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="291bb-165">全体的な帯域幅の制限とセッションの制限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="291bb-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="291bb-166">Skype for Business Server コントロールパネルを使って、これらのポリシーのコンテナープロファイルを作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="291bb-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="291bb-167">ネットワーク帯域幅ポリシーのプロファイルを削除するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="291bb-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="291bb-168">帯域幅ポリシーのプロファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="291bb-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="291bb-169">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="291bb-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="291bb-170">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="291bb-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="291bb-171">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="291bb-172">[**帯域幅ポリシー** ] ページで、削除する帯域幅ポリシープロファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="291bb-173">一度に複数のプロファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="291bb-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="291bb-174">これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数のプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="291bb-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="291bb-175">または、すべてのプロファイルを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="291bb-176">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="291bb-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="291bb-177">ネットワークサイトに関連付けられている帯域幅ポリシープロファイルを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="291bb-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="291bb-178">プロファイルを削除するには、最初にネットワークサイトとの関連付けを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="291bb-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="291bb-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="291bb-179">See Also</span></span>

[<span data-ttu-id="291bb-180">サイトの通話受付制御の管理</span><span class="sxs-lookup"><span data-stu-id="291bb-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="291bb-181">新規-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="291bb-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="291bb-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="291bb-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="291bb-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="291bb-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="291bb-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="291bb-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

