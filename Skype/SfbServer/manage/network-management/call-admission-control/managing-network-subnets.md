---
title: ネットワークのサブネットを管理します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 呼受付制御 (CAC) が実装されているビジネス サーバーの Skype のほとんどの展開では通常あるサブネットの数が多い。 このため、お勧め多くの場合ビジネス サーバー管理シェルには、Skype からサブネットを構成します。
ms.openlocfilehash: e855805aebc61228c185d04cba1faa9de6700f84
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223354"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="13380-104">ビジネス サーバーの Skype のネットワークのサブネットを管理します。</span><span class="sxs-lookup"><span data-stu-id="13380-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="13380-105">ビジネス サーバーのコントロール パネルまたはビジネス サーバー管理シェルの Skype のいずれかの Skype を使用するにはネットワークのサブネットを管理します。</span><span class="sxs-lookup"><span data-stu-id="13380-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="13380-106">呼受付制御 (CAC) が実装されているビジネス サーバーの Skype のほとんどの展開では通常あるサブネットの数が多い。</span><span class="sxs-lookup"><span data-stu-id="13380-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="13380-107">このため、お勧め多くの場合ビジネス サーバー管理シェルには、Skype からサブネットを構成します。</span><span class="sxs-lookup"><span data-stu-id="13380-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="13380-108">ネットワーク サブネットの情報を表示または作成、変更、またはネットワークのサブネットを削除するには、この資料のセクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="13380-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="13380-109">ネットワークのサブネット情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="13380-109">View network subnet information</span></span> 

<span data-ttu-id="13380-110">ネットワークのサブネットを表示するのには、次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="13380-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="13380-111">ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワーク サブネットを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="13380-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="13380-112">ネットワークのサブネットを表示するのには</span><span class="sxs-lookup"><span data-stu-id="13380-112">To view a network subnet</span></span>

1.  <span data-ttu-id="13380-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13380-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13380-114">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="13380-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="13380-115">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="13380-116">[**サブネット**] ページで、表示するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="13380-117">のみ、一度に 1 つのサブネットを表示できます。</span><span class="sxs-lookup"><span data-stu-id="13380-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="13380-118">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="13380-119">ネットワーク サブネットの構成情報を使用して Windows PowerShell コマンドレットで表示します。</span><span class="sxs-lookup"><span data-stu-id="13380-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="13380-120">Windows PowerShell と Get CsNetworkSubnet コマンドレットを使用して、ネットワーク サブネットの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="13380-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="13380-121">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="13380-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="13380-122">ネットワーク サブネットの情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="13380-122">To view network subnet information</span></span>

  - <span data-ttu-id="13380-123">ネットワークのサブネットに関する情報を表示するのには、Skype のビジネス サーバー管理シェルの次のコマンドを入力し、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="13380-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="13380-124">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="13380-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="13380-125">詳細については、 [Get CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13380-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="13380-126">作成またはネットワークのサブネットを変更します。</span><span class="sxs-lookup"><span data-stu-id="13380-126">Create or modify network subnets</span></span> 

<span data-ttu-id="13380-127">このサブネットに属するホストの地理的位置を決定するためにネットワークのサブネットをネットワーク サイトに関連付けられてする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13380-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="13380-128">ビジネス サーバーのコントロール パネルの Skype を使用すると、サブネットを構成します。</span><span class="sxs-lookup"><span data-stu-id="13380-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="13380-129">ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワーク サブネットを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="13380-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="13380-130">呼受付制御 (CAC) が実装されているビジネス サーバーの Skype のほとんどの展開では通常あるサブネットの数が多い。</span><span class="sxs-lookup"><span data-stu-id="13380-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="13380-131">このため、お勧め多くの場合ビジネス サーバー管理シェルには、Skype からサブネットを構成します。</span><span class="sxs-lookup"><span data-stu-id="13380-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="13380-132">そこからは、Windows PowerShell コマンドレット**が CSV のインポート**と連携して**新規 CsNetworkSubnet**を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="13380-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="13380-133">一緒にこれらのコマンドレットを使用して、すると、コンマ区切り値 (.csv) ファイルからサブネットの設定で読み取りでき、同時に複数のサブネットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="13380-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="13380-134">.Csv ファイルからサブネットを作成する方法の例については、[新規 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13380-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="13380-135">ネットワーク サブネットを作成するには</span><span class="sxs-lookup"><span data-stu-id="13380-135">To create a network subnet</span></span>

1.  <span data-ttu-id="13380-136">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13380-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13380-137">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="13380-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="13380-138">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="13380-139">[**サブネット**] ページで [**新規**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="13380-140">**新しいサブネット**の**サブネット ID**フィールドの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="13380-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="13380-141">これは、IP アドレス (174.11.12.0 など) は、サブネットで定義されている IP アドレスの範囲内の最初のアドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="13380-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="13380-142">**マスク**」フィールドには、1 から 32 までの数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="13380-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="13380-143">この値は、作成されているサブネットに適用するのにはビット マスクです。</span><span class="sxs-lookup"><span data-stu-id="13380-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="13380-144">[**ネットワーク サイト ID**には、このサブネットが所属するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="13380-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="13380-145">(省略可能)表すことのできない、名前だけがこのサブネットの詳細については、[**説明**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="13380-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="13380-146">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="13380-147">ネットワーク サブネットを変更するのには</span><span class="sxs-lookup"><span data-stu-id="13380-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="13380-148">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13380-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13380-149">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="13380-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="13380-150">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="13380-151">[**サブネット**] ページで、変更するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="13380-152">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="13380-153">[**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワーク サイト、または説明を変更できます。</span><span class="sxs-lookup"><span data-stu-id="13380-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="13380-154">ビットマスクを変更する場合は、サブネット ID がサブネットで定義されている IP アドレスの範囲内の最初のアドレスをする必要がありますまだすることに留意してください。</span><span class="sxs-lookup"><span data-stu-id="13380-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="13380-155">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="13380-156">ネットワーク サブネットを削除します。</span><span class="sxs-lookup"><span data-stu-id="13380-156">Delete network subnets</span></span>

<span data-ttu-id="13380-157">サブネットを削除するのには、次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="13380-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="13380-158">ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワーク サブネットを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="13380-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="13380-159">呼受付制御 (CAC) が実装されているビジネス サーバーの Skype のほとんどの展開では通常あるサブネットの数が多い。</span><span class="sxs-lookup"><span data-stu-id="13380-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="13380-160">このため、お勧め多くの場合ビジネス サーバー管理シェルには、Skype からサブネットを構成します。</span><span class="sxs-lookup"><span data-stu-id="13380-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="13380-161">そこからは、Windows PowerShell コマンドレット**が CSV のインポート**と連携して**新規 CsNetworkSubnet**を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="13380-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="13380-162">一緒にこれらのコマンドレットを使用して、すると、コンマ区切り値 (.csv) ファイルからサブネットの設定で読み取りでき、同時に複数のサブネットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="13380-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="13380-163">.Csv ファイルからサブネットを作成する方法の例については、[新規 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13380-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="13380-164">ネットワーク サブネットを削除するのには</span><span class="sxs-lookup"><span data-stu-id="13380-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="13380-165">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13380-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13380-166">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="13380-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="13380-167">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="13380-168">[**サブネット**] ページで、削除するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="13380-169">同時に複数のサブネットを削除できます。</span><span class="sxs-lookup"><span data-stu-id="13380-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="13380-170">これを行うには、CTRL キーを押し、CTRL キーを押しながら複数のサブネットを選択します。</span><span class="sxs-lookup"><span data-stu-id="13380-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="13380-171">または、すべてのサブネットを選択するに **[すべて選択**] をクリックして **[編集**] メニューです。</span><span class="sxs-lookup"><span data-stu-id="13380-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="13380-172">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="13380-173">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13380-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="13380-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="13380-174">See Also</span></span>

[<span data-ttu-id="13380-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="13380-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="13380-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="13380-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="13380-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="13380-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="13380-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="13380-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  