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
ms.openlocfilehash: e2ac69190ab93b4b6d81fed13538cc6fcaa91f20
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816397"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="ac4dd-104">Skype for Business Server でのネットワーク サブネットの管理</span><span class="sxs-lookup"><span data-stu-id="ac4dd-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="ac4dd-105">Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して、ネットワーク サブネットを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="ac4dd-106">通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="ac4dd-107">このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="ac4dd-108">この記事のセクションを使用して、ネットワーク サブネット情報を表示したり、ネットワーク サブネットを作成、変更、または削除したりします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="ac4dd-109">ネットワーク サブネット情報の表示</span><span class="sxs-lookup"><span data-stu-id="ac4dd-109">View network subnet information</span></span> 

<span data-ttu-id="ac4dd-110">次の手順を使用して、ネットワーク サブネットを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="ac4dd-111">Skype for Business Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="ac4dd-112">ネットワーク サブネットを表示するには</span><span class="sxs-lookup"><span data-stu-id="ac4dd-112">To view a network subnet</span></span>

1.  <span data-ttu-id="ac4dd-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ac4dd-114">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ac4dd-115">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[サブネット] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ac4dd-116">[**サブネット**] ページで、表示するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="ac4dd-117">一度に表示できるのは 1 つのサブネットのみです。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="ac4dd-118">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ac4dd-119">ネットワーク サブネットの構成情報を表示するには、次のWindows PowerShell使用します。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ac4dd-120">ネットワーク サブネット情報は、ネットワーク サブネットと Windows PowerShellコマンドレットをGet-CsNetworkSubnetできます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="ac4dd-121">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="ac4dd-122">ネットワーク サブネット情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="ac4dd-122">To view network subnet information</span></span>

  - <span data-ttu-id="ac4dd-123">すべてのネットワーク サブネットに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="ac4dd-124">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="ac4dd-125">詳細については、[Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="ac4dd-126">ネットワーク サブネットを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="ac4dd-126">Create or modify network subnets</span></span> 

<span data-ttu-id="ac4dd-127">ネットワーク サブネットは、そのサブネットに所属するホストの地理的な場所を指定するために、ネットワーク サイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="ac4dd-128">Skype for Business Server コントロール パネルを使用してサブネットを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="ac4dd-129">Skype for Business Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="ac4dd-130">通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="ac4dd-131">このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ac4dd-132">そこから、新しいコマンドレット Import-CSV と共に **New-CsNetworkSubnet** Windows PowerShell **呼び出すことができます**。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="ac4dd-133">これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="ac4dd-134">csv ファイルからサブネットを作成する方法の例については、「[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="ac4dd-135">ネットワーク サブネットを作成するには</span><span class="sxs-lookup"><span data-stu-id="ac4dd-135">To create a network subnet</span></span>

1.  <span data-ttu-id="ac4dd-136">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ac4dd-137">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ac4dd-138">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[サブネット] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ac4dd-139">[**サブネット**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="ac4dd-p107">[**新しいサブネット**] で、[**サブネット ID**] フィールドに値を入力します。 これは、IP アドレス (174.11.12.0 など) である必要があります。また、サブネットで定義される IP アドレス範囲の最初のアドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-p107">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="ac4dd-142">[**マスク**] フィールドで、1 ～ 32 の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ac4dd-143">この値は、作成するサブネットに適用するビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="ac4dd-144">[**ネットワーク サイト ID**] で、このサブネットが所属するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="ac4dd-145">(オプション) [**説明**] フィールドに値を入力して、名前だけでは表現することのできないこのサブネットの詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="ac4dd-146">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="ac4dd-147">ネットワーク サブネットを変更するには</span><span class="sxs-lookup"><span data-stu-id="ac4dd-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="ac4dd-148">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ac4dd-149">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ac4dd-150">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[サブネット] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ac4dd-151">[**サブネット**] ページで、変更するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="ac4dd-152">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ac4dd-p108">[**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワーク サイト、または説明を変更できます。 ビットマスクを変更する場合は、変更後もサブネット ID がサブネットで定義される IP アドレス範囲の最初のアドレスでなければならないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-p108">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="ac4dd-155">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="ac4dd-156">ネットワーク サブネットを削除する</span><span class="sxs-lookup"><span data-stu-id="ac4dd-156">Delete network subnets</span></span>

<span data-ttu-id="ac4dd-157">次の手順を使用して、サブネットを削除できます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="ac4dd-158">Skype for Business Server コントロール パネルから、ネットワーク サブネットを作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="ac4dd-159">通話受付管理 (CAC) が実装されている Skype for Business Server のほとんどの展開では、通常、多数のサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="ac4dd-160">このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成する方が最適です。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ac4dd-161">そこから、新しいコマンドレット Import-CSV と共に **New-CsNetworkSubnet** Windows PowerShell **呼び出すことができます**。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="ac4dd-162">これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="ac4dd-163">.csv ファイルからサブネットを作成する方法の例は、「[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="ac4dd-164">ネットワーク サブネットを削除するには</span><span class="sxs-lookup"><span data-stu-id="ac4dd-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="ac4dd-165">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ac4dd-166">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ac4dd-167">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[サブネット] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="ac4dd-168">[**サブネット**] ページで、削除するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="ac4dd-p111">1 つ以上のサブネットを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のサブネットを選択します。または、すべてのサブネットを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-p111">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="ac4dd-172">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ac4dd-173">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac4dd-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="ac4dd-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac4dd-174">See Also</span></span>

[<span data-ttu-id="ac4dd-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ac4dd-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="ac4dd-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ac4dd-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="ac4dd-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ac4dd-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="ac4dd-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ac4dd-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
