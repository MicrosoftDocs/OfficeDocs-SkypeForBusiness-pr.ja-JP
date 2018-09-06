---
title: ネットワーク領域、サイト、およびビジネスの Skype でサブネットを配置します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 作成ネットワーク地域、ネットワーク サイトを変更してビジネス サーバーの Skype のネットワークのサブネットを関連付けます。 これらのすべては、高度なエンタープライズ VoIP 機能に使用します。 メディアのバイパス、受付制御、およびロケーション ベースのルーティングを呼び出します。
ms.openlocfilehash: c4598a1a8ffd46412ce16992788af060e5df0b98
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260406"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="d0989-104">ネットワーク領域、サイト、およびビジネスの Skype でサブネットを配置します。</span><span class="sxs-lookup"><span data-stu-id="d0989-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="d0989-105">作成ネットワーク地域、ネットワーク サイトを変更してビジネス サーバーの Skype のネットワークのサブネットを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d0989-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="d0989-106">これらのすべては、高度なエンタープライズ VoIP 機能に使用します。 メディアのバイパス、受付制御、およびロケーション ベースのルーティングを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d0989-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="d0989-107">高度なエンタープライズ VoIP 機能として、[call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)、[media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)、[ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)、[E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md) を挙げることができます。</span><span class="sxs-lookup"><span data-stu-id="d0989-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [ location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="d0989-108">これらの各機能を使用するには、ネットワーク地域、ネットワーク サイト、サブネットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="d0989-109">たとえば、これらの各機能では、トポロジ内にある各サブネットを特定のネットワーク サイトに関連付け、各ネットワーク サイトをネットワーク地域に関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="d0989-110">これらの用語の詳細については、 [Skype のビジネス サーバーで高度なエンタープライズ VoIP 機能のネットワーク設定](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0989-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)</span></span>

<span data-ttu-id="d0989-111">通話受付管理および E9-1-1 には、ネットワーク サイトの追加構成要件があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="d0989-112">通話受付管理では、WAN の帯域幅が制限されているサイトごとに帯域幅ポリシー プロファイルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="d0989-113">呼受付制御を展開する場合は、する必要があります[Skype ビジネス サーバー用に帯域幅ポリシー プロファイルを作成する](create-bandwidth-policy-profiles.md)ネットワーク サイトを構成する前にします。</span><span class="sxs-lookup"><span data-stu-id="d0989-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="d0989-114">E9-1-1 では、サイトごとに 場所のポリシーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="d0989-115">~ 9-1-1 を展開する場合は、する必要があります[Skype ビジネス サーバー用に作成する場所のポリシー](create-location-policies.md)ネットワーク サイトを構成する前にします。</span><span class="sxs-lookup"><span data-stu-id="d0989-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="d0989-116">ネットワーク地域の作成または変更</span><span class="sxs-lookup"><span data-stu-id="d0989-116">Create or modify a Network Region</span></span>

<span data-ttu-id="d0989-117">これらの機能の 1 つのネットワーク地域を既に作成した場合は、新しいネットワーク領域を作成する必要はありません。その他の高度なエンタープライズ VoIP 機能では、それらの同じネットワーク領域を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0989-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="d0989-p106">ただし、機能固有の設定を適用するために、ネットワーク地域に関する既存の定義に変更を加える必要が生じることがあります。たとえば、E9-1-1 用のネットワーク地域を作成し (この場合は関連付けられた中央サイトは必要ありません)、次に通話受付管理を展開する場合は、中央サイトを指定するためにネットワーク地域の定義を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-p106">You may, however, need to modify an existing network region definition to apply feature-specific settings. For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d0989-120">ビジネス サーバー管理シェルの Skype を使用してネットワーク地域を作成するには</span><span class="sxs-lookup"><span data-stu-id="d0989-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d0989-121">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d0989-122">New-CsNetworkRegion コマンドレットを実行してネットワーク地域を作成します。</span><span class="sxs-lookup"><span data-stu-id="d0989-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="d0989-123">例:</span><span class="sxs-lookup"><span data-stu-id="d0989-123">For example:</span></span>

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="d0989-124">この例では、「北米」と呼ばれるネットワーク領域を作成したサイト ID のシカゴでの中央サイトに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="d0989-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="d0989-125">トポロジでのネットワーク地域の作成を完了するには、ネットワーク地域ごとの設定値を使用してステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0989-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d0989-126">Skype を使用してビジネス サーバーのコントロール パネルのネットワーク領域を作成するには</span><span class="sxs-lookup"><span data-stu-id="d0989-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d0989-127">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d0989-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d0989-128">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="d0989-129">[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-129">Click **Region**.</span></span>

4. <span data-ttu-id="d0989-130">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-130">Click **New**.</span></span>

5. <span data-ttu-id="d0989-131">[**新しい地域**] ページで、[**名前**] をクリックしてネットワーク地域の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0989-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="d0989-132">[**中央サイト**] をクリックし、リストにある中央サイトを 1 つクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="d0989-133">オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0989-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="d0989-134">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-134">Click **Commit**.</span></span>

9. <span data-ttu-id="d0989-135">トポロジでのネットワーク地域の作成を完了するには、その他の地域の設定値を使用してステップ 4 ～ 8 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0989-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d0989-136">ビジネス サーバー管理シェルの Skype を使用してネットワーク地域を変更するのには</span><span class="sxs-lookup"><span data-stu-id="d0989-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d0989-137">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d0989-138">Set-CsNetworkRegion コマンドレットを実行して、既存のネットワーク地域を変更します。</span><span class="sxs-lookup"><span data-stu-id="d0989-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="d0989-139">例:</span><span class="sxs-lookup"><span data-stu-id="d0989-139">For example:</span></span>

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="d0989-140">この例では、説明を変更することによって「北米」(このトピックで前述した手順を使用して作成された) と呼ばれる、既存のネットワークの領域を変更します。</span><span class="sxs-lookup"><span data-stu-id="d0989-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="d0989-141">「北米」領域の説明が存在していた場合は、このコマンドで上書き値です。説明が設定されていない場合、この設定にします。</span><span class="sxs-lookup"><span data-stu-id="d0989-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="d0989-142">その他のネットワーク地域を変更するには、その他の地域の設定値を使用してステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0989-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d0989-143">Skype を使用してビジネス サーバーのコントロール パネルのネットワーク領域を変更するのには</span><span class="sxs-lookup"><span data-stu-id="d0989-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d0989-144">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d0989-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d0989-145">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="d0989-146">[**地域**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="d0989-147">表で、変更するネットワーク地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="d0989-148">[**編集**] をクリックして、[**詳細の表示...**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="d0989-149">[**地域の編集**] ページで、必要に応じてこのネットワーク地域の設定の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="d0989-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="d0989-150">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-150">Click **Commit**.</span></span>

8. <span data-ttu-id="d0989-151">ネットワーク地域の変更を完了するには、他の地域の設定値を使用してステップ 4 ～ 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0989-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="d0989-152">ネットワーク サイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="d0989-152">Create or modify a network site</span></span>

<span data-ttu-id="d0989-153">これらの機能の 1 つのネットワーク サイトを既に作成した場合は、新しいネットワーク サイトを作成する必要はありません。その他の高度なエンタープライズ VoIP 機能では、それらの同じネットワーク サイトを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0989-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="d0989-154">機能固有の設定を適用する既存のネットワーク サイトの定義を変更する必要があります可能性があります、ただし、です。</span><span class="sxs-lookup"><span data-stu-id="d0989-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="d0989-155">たとえば、~ 9-1-1 のネットワーク サイトを作成した場合は、帯域幅ポリシー プロファイルを適用する呼受付制御の展開時にネットワーク サイトを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d0989-156">Skype ビジネス サーバー管理シェルを使用してネットワーク サイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="d0989-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d0989-157">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d0989-158">New-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0989-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="d0989-159">例:</span><span class="sxs-lookup"><span data-stu-id="d0989-159">For example:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="d0989-160">「シカゴ」と呼ばれるネットワーク サイトを作成するこの例では、「北米」ネットワークの領域にあります。</span><span class="sxs-lookup"><span data-stu-id="d0989-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0989-161">このコマンドを正常に実行するには、NorthAmerica ネットワーク地域があらかじめ存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="d0989-162">トポロジのネットワーク サイトを作成するには、他のサイトの設定値を使用してステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0989-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d0989-163">ビジネス サーバーのコントロール パネルの Skype を使用してネットワーク サイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="d0989-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d0989-164">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d0989-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d0989-165">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="d0989-166">[**サイト**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="d0989-167">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-167">Click **New**.</span></span>

5. <span data-ttu-id="d0989-168">[**新しいサイト**] ページで、[**名前**] をクリックしてネットワーク サイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0989-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="d0989-169">[**地域**] をクリックして、リストで地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="d0989-170">オプションで、[**帯域幅ポリシー**] をクリックして、リストで帯域幅ポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0989-171">帯域幅ポリシーが必要なのは、サイトで通話受付管理を展開する場合だけです。</span><span class="sxs-lookup"><span data-stu-id="d0989-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="d0989-172">オプションで、[**場所のポリシー**] をクリックして、リストで場所のポリシーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0989-173">場所のポリシーが必要なのは、サイトで E9-1-1 を展開する場合だけです。</span><span class="sxs-lookup"><span data-stu-id="d0989-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="d0989-174">オプションで、[**説明**] をクリックして、このネットワーク サイトを説明する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0989-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="d0989-175">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-175">Click **Commit**.</span></span>

11. <span data-ttu-id="d0989-176">使用しているトポロジのネットワーク サイトの作成を完了するには、他のサイトの設定値を使用してステップ 4 ～ 10 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0989-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d0989-177">Skype ビジネス サーバー管理シェルを使用してネットワーク サイトを変更するのには</span><span class="sxs-lookup"><span data-stu-id="d0989-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d0989-178">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d0989-179">Set-CsNetworkSite コマンドレットを実行して、ネットワーク サイトを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0989-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="d0989-180">例:</span><span class="sxs-lookup"><span data-stu-id="d0989-180">For example:</span></span>

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="d0989-181">この例では、「アルバカーキ」と呼ばれるサイトは「北米」ネットワークの領域に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0989-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="d0989-182">ネットワーク サイトの構成を変更して、通話受付管理、E9-1-1、またはメディア バイパスを展開するには、Set-CsNetworkSite コマンドレットをそれぞれ BWPolicyProfileID または LocationPolicy パラメーターと組み合わせて実行し、ネットワーク サイトの設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="d0989-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0989-p110">メディア バイパス用に BypassID パラメーターが用意されていますが、自動生成されるバイパス ID を上書きしないことを強くお勧めします。 メディア バイパス用にネットワーク サイトを構成するために、追加パラメーターを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d0989-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="d0989-185">使用しているトポロジのネットワーク サイトの変更を完了するには、他のサイトの設定値を使用してステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0989-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d0989-186">ビジネス サーバーのコントロール パネルの Skype を使用してネットワーク サイトを変更するのには</span><span class="sxs-lookup"><span data-stu-id="d0989-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d0989-187">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d0989-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d0989-188">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="d0989-189">[**サイト**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="d0989-190">表内で、変更するネットワーク サイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="d0989-191">[**編集**] をクリックして、[**詳細の表示...**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="d0989-192">[**サイトの編集**] ページで、必要に応じてこのネットワーク サイトの設定の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="d0989-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="d0989-193">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-193">Click **Commit**.</span></span>

8. <span data-ttu-id="d0989-194">ネットワーク サイトの変更を完了するには、他のサイトの設定値を使用してステップ 4 ～ 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0989-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="d0989-195">ネットワーク サイトとサブネットの関連付け</span><span class="sxs-lookup"><span data-stu-id="d0989-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="d0989-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="d0989-196"></span></span>

<span data-ttu-id="d0989-197">サブネット情報を使用してエンドポイントが存在する新しいセッションが開始されたときにネットワーク サイトを判断するため、ネットワーク内のすべてのサブネットが、特定のネットワーク サイトに関連付けられてする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="d0989-198">セッションの各パーティの場所がわかっている場合は、エンタープライズ VoIP の機能が適用できる設定の呼び出しを処理する方法を決定するには、その情報の詳細、またはルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d0989-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="d0989-199">展開内の音声ビデオ エッジ サーバーの構成済みパブリック IP アドレスはすべて、ネットワーク構成設定に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="d0989-200">これらの IP アドレスは、マスク値 32 のサブネットとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="d0989-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="d0989-201">関連付けられたネットワーク サイトは、適切な構成済みネットワーク サイトに対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0989-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="d0989-202">A に対応するパブリック IP アドレスなどのシカゴの中央サイトで音声ビデオ エッジ サービスがシカゴの NetworkSiteID になるとします。</span><span class="sxs-lookup"><span data-stu-id="d0989-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d0989-203">Skype ビジネス サーバー管理シェルを使用してネットワーク サイトとサブネットを関連付けるに</span><span class="sxs-lookup"><span data-stu-id="d0989-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="d0989-204">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d0989-205">ネットワーク サイトとサブネットを関連付けるには、**新規 CsNetworkSubnet**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0989-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="d0989-206">例:</span><span class="sxs-lookup"><span data-stu-id="d0989-206">For example:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="d0989-207">この例では、サブネットの 172.11.12.13 とネットワーク サイトの"Chicago"間の関連付けを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0989-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="d0989-208">トポロジのすべてのサブネットに対して、ステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="d0989-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="d0989-209">CSV ファイルをインポートしてサブネットをネットワーク サイトに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="d0989-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="d0989-p113">追加する予定の、すべてのサブネットが含まれた CSV ファイルを作成します。たとえば、次の内容が含まれる、**subnet.csv** という名前のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0989-p113">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="d0989-212">Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="d0989-213">**Subnet.csv**をインポートするのには次のコマンドレットを実行し、Lync Server 管理ストア内の内容を格納します。</span><span class="sxs-lookup"><span data-stu-id="d0989-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet $_IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d0989-214">ビジネス サーバーのコントロール パネルの Skype を使用してネットワーク サイトとサブネットを関連付けるに</span><span class="sxs-lookup"><span data-stu-id="d0989-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d0989-215">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d0989-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d0989-216">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="d0989-217">[**サブネット**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="d0989-218">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-218">Click **New**.</span></span>

5. <span data-ttu-id="d0989-219">[**新しいサブネット**] ページで、[**サブネット ID**] をクリックし、ネットワーク サイトに関連付けるサブネットで定義される IP アドレス範囲の最初のアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d0989-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="d0989-220">[**マスク**] をクリックし、サブネットに適用するビットマスクを入力します。</span><span class="sxs-lookup"><span data-stu-id="d0989-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="d0989-221">[**ネットワーク サイト ID**] をクリックし、このサブネットの追加先となるサイトのサイト ID を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0989-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0989-222">ネットワーク サイトがまだ作成されていない場合、この一覧は空です。</span><span class="sxs-lookup"><span data-stu-id="d0989-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="d0989-223">詳細手順については、[作成または変更するネットワーク サイト](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0989-223">For details about the procedure, see [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="d0989-224">**Get CsNetworkSite**コマンドレットを実行して展開するためのサイト Id を取得することも。</span><span class="sxs-lookup"><span data-stu-id="d0989-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="d0989-225">詳細については、Skype ビジネス サーバー管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0989-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="d0989-226">オプションで、[**説明**] をクリックし、このサブネットを説明する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="d0989-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="d0989-227">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0989-227">Click **Commit**.</span></span>

<span data-ttu-id="d0989-228">これらのステップを繰り返して、その他のサブネットをネットワーク サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d0989-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="d0989-229">キーの稼働状態インジケーター (KHI) の警告を発生すると、ネットワーク内に存在する IP アドレスの一覧を指定するが、いずれかに関連付けられていないサブネットの IP アドレスを含むサブネットがネットワーク サイトに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="d0989-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="d0989-230">このアラートは生成されません 2 回以上、8 時間以内です。</span><span class="sxs-lookup"><span data-stu-id="d0989-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="d0989-231">アラートの関連情報と例については次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d0989-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="d0989-232">**ソース**: CS 帯域幅ポリシー サービス (コア)</span><span class="sxs-lookup"><span data-stu-id="d0989-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="d0989-233">**イベント番号**: 36034</span><span class="sxs-lookup"><span data-stu-id="d0989-233">**Event number**: 36034</span></span>

 <span data-ttu-id="d0989-234">**レベル**: 2</span><span class="sxs-lookup"><span data-stu-id="d0989-234">**Level**: 2</span></span>

 <span data-ttu-id="d0989-235">**説明**: 次の IP アドレスのサブネット:\<リストの IP アドレス\>いずれかの方法が構成されていない、またはサブネットがネットワーク サイトに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="d0989-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="d0989-236">**原因**: 対応する IP アドレスのサブネットがネットワーク構成設定にないか、サブネットがネットワーク サイトに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="d0989-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="d0989-237">**解決方法**: IP アドレス リストに対応するサブネットをネットワーク構成設定に追加し、すべてのサブネットをネットワーク サイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d0989-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="d0989-p116">たとえば、通知に表示された IP アドレス リストが 10.121.248.226 および 10.121.249.20 であった場合、これらの IP アドレスがサブネットに関連付けられていないか、または関連付けられているサブネットがネットワーク サイトに属していないかのどちらかになります。10.121.248.0/24 および 10.121.249.0/24 がこれらのアドレスに対応するサブネットである場合、次の手順でこの問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="d0989-p116">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="d0989-240">IP アドレス 10.121.248.226 が 10.121.248.0/24 サブネットに関連付けられていること、および IP アドレス 10.121.249.20 が 10.121.249.0/24 サブネットに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0989-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="d0989-241">10.121.248.0/24 および 10.121.249.0/24 サブネットがそれぞれネットワーク サイトに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0989-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0989-242">この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。</span><span class="sxs-lookup"><span data-stu-id="d0989-242">See also</span></span>
<span data-ttu-id="d0989-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="d0989-243"></span></span>


[<span data-ttu-id="d0989-244">新しい-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d0989-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="d0989-245">Get CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d0989-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="d0989-246">セット CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d0989-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="d0989-247">削除 CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d0989-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="d0989-248">新しい-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d0989-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="d0989-249">Get CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d0989-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="d0989-250">セット CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d0989-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="d0989-251">削除 CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="d0989-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

