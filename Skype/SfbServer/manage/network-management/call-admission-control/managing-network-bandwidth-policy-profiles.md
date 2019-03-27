---
title: ネットワーク帯域幅ポリシーのプロファイルを管理します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この資料の表示、作成、変更、またはネットワークの帯域幅ポリシーのプロファイルを削除する手順を使用します。
ms.openlocfilehash: d27e4df1b549afd3c176f8b54453c44bb97819f8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878901"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="df2c3-103">Skype for Business Server でのネットワーク帯域幅ポリシー プロファイルの管理</span><span class="sxs-lookup"><span data-stu-id="df2c3-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="df2c3-104">この資料の表示、作成、変更、またはネットワークの帯域幅ポリシーのプロファイルを削除する手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="df2c3-105">ネットワークの帯域幅のポリシー プロファイルの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="df2c3-106">呼受付制御 (CAC) の一環として、帯域幅ポリシーを使用して、特定のモダリティの帯域幅の制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="df2c3-107">ビジネス サーバーの Skype にのみオーディオおよびビデオのモダリティ割り当てることができる帯域幅の制限です。</span><span class="sxs-lookup"><span data-stu-id="df2c3-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="df2c3-108">全体的な帯域幅の制限とセッション制限を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="df2c3-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="df2c3-109">ビジネス サーバーのコントロール パネルの Skype を使用するには作成、変更、またはこれらのポリシーのコンテナー プロファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="df2c3-110">各帯域幅ポリシーのプロファイルは、1 つまたは複数のネットワーク サイトと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="df2c3-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="df2c3-111">帯域幅ポリシーのプロファイルを表示するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="df2c3-112">帯域幅ポリシーのプロファイルを表示するのには</span><span class="sxs-lookup"><span data-stu-id="df2c3-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="df2c3-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df2c3-114">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="df2c3-115">左側のナビゲーション ・ バーで**ネットワークの構成**] をクリックし、**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="df2c3-116">[**帯域幅ポリシー** ] ページでは、帯域幅ポリシーのプロファイルを表示するをクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="df2c3-117">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="df2c3-118">Windows PowerShell コマンドレットを使用して、ネットワーク帯域幅ポリシーのプロファイル情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="df2c3-119">ネットワーク帯域幅のプロファイルは、Windows PowerShell と Get CsNetworkBandwidthPolicyProfile コマンドレットを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="df2c3-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="df2c3-120">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="df2c3-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="df2c3-121">ネットワーク帯域幅ポリシーのプロファイル情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="df2c3-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="df2c3-122">すべてのネットワーク帯域幅ポリシー プロファイルに関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="df2c3-123">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df2c3-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="df2c3-124">詳細については、 [Get CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df2c3-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="df2c3-125">作成または帯域幅ポリシーのプロファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="df2c3-126">呼受付制御 (CAC) の一環として、帯域幅ポリシーを使用して、特定のモダリティの帯域幅の制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="df2c3-127">ビジネス サーバーの Skype にのみオーディオおよびビデオのモダリティ割り当てることができる帯域幅の制限です。</span><span class="sxs-lookup"><span data-stu-id="df2c3-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="df2c3-128">全体的な帯域幅の制限とセッション制限を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="df2c3-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="df2c3-129">ビジネス サーバーのコントロール パネルの Skype を使用するには作成、変更、またはこれらのポリシーのコンテナー プロファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="df2c3-130">各帯域幅ポリシーのプロファイルは、1 つまたは複数のネットワーク サイトと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="df2c3-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="df2c3-131">作成または帯域幅ポリシーのプロファイルを変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="df2c3-132">新しい帯域幅ポリシー プロファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="df2c3-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="df2c3-133">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df2c3-134">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="df2c3-135">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="df2c3-136">[**帯域幅ポリシー** ] ページで [**新規**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="df2c3-137">**新しい帯域幅ポリシー プロファイル**の **[名前**] フィールドに名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="df2c3-138">この名前は、すべての帯域幅ポリシー プロファイルの中で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2c3-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="df2c3-139">**オーディオの制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="df2c3-140">この値は、帯域幅を kbps 単位で表されるすべてのオーディオ接続に割り当てることの最大量です。</span><span class="sxs-lookup"><span data-stu-id="df2c3-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="df2c3-141">**オーディオ セッションの制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="df2c3-142">この値は、帯域幅を kbps 単位で表される、個々 のオーディオ接続に割り当てることの最大量です。</span><span class="sxs-lookup"><span data-stu-id="df2c3-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="df2c3-143">この値は、40 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2c3-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="df2c3-144">**ビデオの制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="df2c3-145">この値は、帯域幅を kbps 単位で表されるすべてのビデオ接続に割り当てることの最大量です。</span><span class="sxs-lookup"><span data-stu-id="df2c3-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="df2c3-146">**ビデオ セッションの制限**] フィールドに数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="df2c3-147">この値は、最大限の帯域幅を kbps 単位で表される、個々 のビデオ接続に割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="df2c3-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="df2c3-148">この値は、100 以上にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2c3-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="df2c3-149">(省略可能)表すことのできない名前だけで、この帯域幅ポリシー プロファイルの詳細については、[**説明**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="df2c3-150">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="df2c3-151">新しい帯域幅ポリシー プロファイルを作成するも、帯域幅の制限は自動的に適用されません。</span><span class="sxs-lookup"><span data-stu-id="df2c3-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="df2c3-152">サイト ポリシーのプロファイルを関連付ける必要があります最初。</span><span class="sxs-lookup"><span data-stu-id="df2c3-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="df2c3-153">帯域幅ポリシーのプロファイルを変更するのには</span><span class="sxs-lookup"><span data-stu-id="df2c3-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="df2c3-154">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df2c3-155">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="df2c3-156">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="df2c3-157">[**帯域幅ポリシー** ] ページで、変更する帯域幅ポリシーのプロファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="df2c3-158">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="df2c3-159">[**帯域幅ポリシーのプロファイルの編集**] ページで、必要に応じてフィールドを変更します (詳細についてを参照してください[新しい帯域幅ポリシー プロファイルを作成する](#to-create-a-new-bandwidth-policy-profile))。</span><span class="sxs-lookup"><span data-stu-id="df2c3-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="df2c3-160">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="df2c3-161">帯域幅ポリシーのプロファイルを変更すると、この帯域幅ポリシー プロファイルに関連付けられているすべてのネットワーク サイトの帯域幅の制限が即座に更新されます。</span><span class="sxs-lookup"><span data-stu-id="df2c3-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="df2c3-162">ネットワーク帯域幅ポリシー プロファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="df2c3-163">呼受付制御 (CAC) の一環として、帯域幅ポリシーを使用して、特定のモダリティの帯域幅の制限を定義します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="df2c3-164">ビジネス サーバーの Skype にのみオーディオおよびビデオのモダリティ割り当てることができる帯域幅の制限です。</span><span class="sxs-lookup"><span data-stu-id="df2c3-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="df2c3-165">全体的な帯域幅の制限とセッション制限を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="df2c3-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="df2c3-166">ビジネス サーバーのコントロール パネルの Skype を使用するには作成、変更、またはこれらのポリシーのコンテナー プロファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="df2c3-167">ネットワークの帯域幅ポリシー プロファイルを削除するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="df2c3-168">帯域幅ポリシー プロファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="df2c3-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="df2c3-169">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="df2c3-170">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="df2c3-171">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**帯域幅ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="df2c3-172">[**帯域幅ポリシー** ] ページで、削除する帯域幅ポリシーのプロファイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="df2c3-173">同時に複数のプロファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="df2c3-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="df2c3-174">これを行うには、CTRL キーを押し、CTRL キーを押しながら複数のプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="df2c3-175">または、すべてのプロファイルを選択するに **[すべて選択**] をクリックして **[編集**] メニューです。</span><span class="sxs-lookup"><span data-stu-id="df2c3-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="df2c3-176">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df2c3-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="df2c3-177">ネットワーク サイトに関連付けられている帯域幅ポリシーのプロファイルを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="df2c3-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="df2c3-178">プロファイルを削除する前に、ネットワーク サイトとの関連付けを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2c3-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="df2c3-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="df2c3-179">See Also</span></span>

[<span data-ttu-id="df2c3-180">サイトの呼受付制御を管理します。</span><span class="sxs-lookup"><span data-stu-id="df2c3-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="df2c3-181">新しい-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="df2c3-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="df2c3-182">セット CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="df2c3-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="df2c3-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="df2c3-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="df2c3-184">削除 CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="df2c3-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

