---
title: ネットワーク サブネットの管理
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
description: 通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。 このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。
ms.openlocfilehash: ef771ad78f00085374038203e1049790a9179e88
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122441"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="266bc-104">Skype for Business Server でのネットワーク サブネットの管理</span><span class="sxs-lookup"><span data-stu-id="266bc-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="266bc-105">Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルのいずれかを使用して、ネットワーク サブネットを管理できます。</span><span class="sxs-lookup"><span data-stu-id="266bc-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="266bc-106">通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="266bc-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="266bc-107">このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。</span><span class="sxs-lookup"><span data-stu-id="266bc-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="266bc-108">この記事のセクションを使用して、ネットワーク サブネット情報を表示するか、ネットワーク サブネットを作成、変更、または削除します。</span><span class="sxs-lookup"><span data-stu-id="266bc-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="266bc-109">ネットワーク サブネット情報の表示</span><span class="sxs-lookup"><span data-stu-id="266bc-109">View network subnet information</span></span> 

<span data-ttu-id="266bc-110">次の手順を使用して、ネットワーク サブネットを表示できます。</span><span class="sxs-lookup"><span data-stu-id="266bc-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="266bc-111">Skype for Business Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="266bc-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="266bc-112">ネットワーク サブネットを表示するには</span><span class="sxs-lookup"><span data-stu-id="266bc-112">To view a network subnet</span></span>

1.  <span data-ttu-id="266bc-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="266bc-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="266bc-114">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="266bc-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="266bc-115">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サブネット] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="266bc-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="266bc-116">[**サブネット**] ページで、表示するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="266bc-117">一度に表示できるのは 1 つのサブネットのみです。</span><span class="sxs-lookup"><span data-stu-id="266bc-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="266bc-118">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="266bc-119">ネットワーク サブネット構成情報を表示するには、コマンドレットを使用Windows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="266bc-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="266bc-120">ネットワーク サブネットの情報は、ネットワーク と Windows PowerShellコマンドレットをGet-CsNetworkSubnetできます。</span><span class="sxs-lookup"><span data-stu-id="266bc-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="266bc-121">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="266bc-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="266bc-122">ネットワーク サブネット情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="266bc-122">To view network subnet information</span></span>

  - <span data-ttu-id="266bc-123">すべてのネットワーク サブネットに関する情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="266bc-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="266bc-124">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="266bc-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="266bc-125">詳細については、[Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="266bc-125">For more information, see the help topic for the [Get-CsNetworkSubnet](/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="266bc-126">ネットワーク サブネットの作成または変更</span><span class="sxs-lookup"><span data-stu-id="266bc-126">Create or modify network subnets</span></span> 

<span data-ttu-id="266bc-127">ネットワーク サブネットは、そのサブネットに所属するホストの地理的な場所を指定するために、ネットワーク サイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="266bc-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="266bc-128">Skype for Business Server コントロール パネルを使用してサブネットを構成できます。</span><span class="sxs-lookup"><span data-stu-id="266bc-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="266bc-129">Skype for Business Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="266bc-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="266bc-130">通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="266bc-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="266bc-131">このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。</span><span class="sxs-lookup"><span data-stu-id="266bc-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="266bc-132">そこから **New-CsNetworkSubnet** を呼び出し、Windows PowerShell **Import-CSV コマンドレットと組み合わせて呼び出すことができます**。</span><span class="sxs-lookup"><span data-stu-id="266bc-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="266bc-133">これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="266bc-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="266bc-134">csv ファイルからサブネットを作成する方法の例については、「[New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="266bc-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="266bc-135">ネットワーク サブネットを作成するには</span><span class="sxs-lookup"><span data-stu-id="266bc-135">To create a network subnet</span></span>

1.  <span data-ttu-id="266bc-136">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="266bc-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="266bc-137">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="266bc-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="266bc-138">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サブネット] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="266bc-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="266bc-139">[**サブネット**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="266bc-p107">[**新しいサブネット**] で、[**サブネット ID**] フィールドに値を入力します。 これは、IP アドレス (174.11.12.0 など) である必要があります。また、サブネットで定義される IP アドレス範囲の最初のアドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="266bc-p107">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="266bc-142">[**マスク**] フィールドで、1 ～ 32 の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="266bc-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="266bc-143">この値は、作成するサブネットに適用するビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="266bc-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="266bc-144">[**ネットワーク サイト ID**] で、このサブネットが所属するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="266bc-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="266bc-145">(オプション) [**説明**] フィールドに値を入力して、名前だけでは表現することのできないこのサブネットの詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="266bc-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="266bc-146">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="266bc-147">ネットワーク サブネットを変更するには</span><span class="sxs-lookup"><span data-stu-id="266bc-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="266bc-148">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="266bc-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="266bc-149">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="266bc-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="266bc-150">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サブネット] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="266bc-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="266bc-151">[**サブネット**] ページで、変更するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="266bc-152">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="266bc-p108">[**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワーク サイト、または説明を変更できます。 ビットマスクを変更する場合は、変更後もサブネット ID がサブネットで定義される IP アドレス範囲の最初のアドレスでなければならないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="266bc-p108">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="266bc-155">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="266bc-156">ネットワーク サブネットの削除</span><span class="sxs-lookup"><span data-stu-id="266bc-156">Delete network subnets</span></span>

<span data-ttu-id="266bc-157">次の手順を使用して、サブネットを削除できます。</span><span class="sxs-lookup"><span data-stu-id="266bc-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="266bc-158">Skype for Business Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="266bc-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="266bc-159">通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="266bc-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="266bc-160">このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。</span><span class="sxs-lookup"><span data-stu-id="266bc-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="266bc-161">そこから **New-CsNetworkSubnet** を呼び出し、Windows PowerShell **Import-CSV コマンドレットと組み合わせて呼び出すことができます**。</span><span class="sxs-lookup"><span data-stu-id="266bc-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="266bc-162">これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="266bc-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="266bc-163">.csv ファイルからサブネットを作成する方法の例は、「[New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="266bc-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="266bc-164">ネットワーク サブネットを削除するには</span><span class="sxs-lookup"><span data-stu-id="266bc-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="266bc-165">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="266bc-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="266bc-166">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="266bc-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="266bc-167">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[サブネット] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="266bc-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="266bc-168">[**サブネット**] ページで、削除するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="266bc-p111">1 つ以上のサブネットを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のサブネットを選択します。または、すべてのサブネットを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-p111">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="266bc-172">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="266bc-173">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="266bc-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="266bc-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="266bc-174">See Also</span></span>

[<span data-ttu-id="266bc-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="266bc-175">New-CsNetworkSubnet</span></span>](/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="266bc-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="266bc-176">Set-CsNetworkSubnet</span></span>](/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="266bc-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="266bc-177">Remove-CsNetworkSubnet</span></span>](/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="266bc-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="266bc-178">Get-CsNetworkSubnet</span></span>](/powershell/module/skype/Get-CsNetworkSubnet)