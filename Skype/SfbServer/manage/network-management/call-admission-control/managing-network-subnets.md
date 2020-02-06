---
title: ネットワークサブネットの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 通話受付制御 (CAC) が実装されている Skype for Business Server の大半の展開では、通常、多数のサブネットが存在します。 このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成することをお勧めします。
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817466"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="c8a49-104">Skype for Business Server でのネットワーク サブネットの管理</span><span class="sxs-lookup"><span data-stu-id="c8a49-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="c8a49-105">Skype for Business Server コントロールパネルまたは Skype for Business Server 管理シェルを使って、ネットワークサブネットを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="c8a49-106">通話受付制御 (CAC) が実装されている Skype for Business Server の大半の展開では、通常、多数のサブネットが存在します。</span><span class="sxs-lookup"><span data-stu-id="c8a49-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="c8a49-107">このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="c8a49-108">この記事のセクションを使用して、ネットワークサブネット情報の表示、またはネットワークサブネットの作成、変更、または削除を行います。</span><span class="sxs-lookup"><span data-stu-id="c8a49-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="c8a49-109">ネットワークサブネット情報を表示する</span><span class="sxs-lookup"><span data-stu-id="c8a49-109">View network subnet information</span></span> 

<span data-ttu-id="c8a49-110">次の手順を使用して、ネットワークサブネットを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="c8a49-111">Skype for Business Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="c8a49-112">ネットワークサブネットを表示するには</span><span class="sxs-lookup"><span data-stu-id="c8a49-112">To view a network subnet</span></span>

1.  <span data-ttu-id="c8a49-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8a49-114">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c8a49-115">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c8a49-116">[ **Subnet** ] ページで、表示するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="c8a49-117">一度に1つのサブネットしか表示できません。</span><span class="sxs-lookup"><span data-stu-id="c8a49-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="c8a49-118">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c8a49-119">Windows PowerShell コマンドレットを使用してネットワークサブネット構成情報を表示する</span><span class="sxs-lookup"><span data-stu-id="c8a49-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="c8a49-120">ネットワークサブネットの情報を表示するには、Windows PowerShell を使用するか、または CsNetworkSubnet コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8a49-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="c8a49-121">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="c8a49-122">ネットワークサブネット情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="c8a49-122">To view network subnet information</span></span>

  - <span data-ttu-id="c8a49-123">すべてのネットワークサブネットに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="c8a49-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="c8a49-124">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="c8a49-125">詳細については、「 [CsNetworkSubnet の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8a49-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="c8a49-126">ネットワークサブネットを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="c8a49-126">Create or modify network subnets</span></span> 

<span data-ttu-id="c8a49-127">ネットワークサブネットは、このサブネットに属しているホストの地理的な場所を判断するために、ネットワークサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8a49-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="c8a49-128">Skype for Business Server コントロールパネルを使用して、サブネットを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="c8a49-129">Skype for Business Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="c8a49-130">通話受付制御 (CAC) が実装されている Skype for Business Server の大半の展開では、通常、多数のサブネットが存在します。</span><span class="sxs-lookup"><span data-stu-id="c8a49-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="c8a49-131">このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="c8a49-132">そこから、Windows PowerShell コマンドレットの**Import-CSV**と組み合わせて、**新しい csnetworksubnet**を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="c8a49-133">これらのコマンドレットを一緒に使用することで、サブネットの設定をコンマ区切り値 (.csv) ファイルから読み取り、複数のサブネットを同時に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="c8a49-134">.Csv ファイルからサブネットを作成する方法の例については、「[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8a49-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="c8a49-135">ネットワークサブネットを作成するには</span><span class="sxs-lookup"><span data-stu-id="c8a49-135">To create a network subnet</span></span>

1.  <span data-ttu-id="c8a49-136">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8a49-137">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c8a49-138">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c8a49-139">[**サブネット**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="c8a49-140">[**新しいサブネット**] で、[**サブネット ID** ] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c8a49-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="c8a49-141">これは IP アドレス (たとえば、174.11.12.0) である必要があり、サブネットで定義された IP アドレス範囲の最初のアドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8a49-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="c8a49-142">[**マスク**] フィールドに、1 ~ 32 の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="c8a49-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="c8a49-143">この値は、作成されるサブネットに適用されるビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="c8a49-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="c8a49-144">[**ネットワークサイト ID**] で、このサブネットが所属するサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="c8a49-145">省略[**説明**] フィールドに値を入力して、このサブネットについて、名前だけでは表現できない詳細情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c8a49-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="c8a49-146">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="c8a49-147">ネットワークサブネットを変更するには</span><span class="sxs-lookup"><span data-stu-id="c8a49-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="c8a49-148">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8a49-149">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c8a49-150">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c8a49-151">[ **Subnet** ] ページで、変更するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="c8a49-152">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c8a49-153">[**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワークサイト、または説明を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="c8a49-154">ビットマスクを変更する場合は、サブネット ID が、サブネットで定義されている IP アドレス範囲の最初のアドレスである必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="c8a49-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="c8a49-155">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="c8a49-156">ネットワークサブネットを削除する</span><span class="sxs-lookup"><span data-stu-id="c8a49-156">Delete network subnets</span></span>

<span data-ttu-id="c8a49-157">次の手順を使用して、サブネットを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="c8a49-158">Skype for Business Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="c8a49-159">通話受付制御 (CAC) が実装されている Skype for Business Server の大半の展開では、通常、多数のサブネットが存在します。</span><span class="sxs-lookup"><span data-stu-id="c8a49-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="c8a49-160">このため、多くの場合、Skype for Business Server 管理シェルからサブネットを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="c8a49-161">そこから、Windows PowerShell コマンドレットの**Import-CSV**と組み合わせて、**新しい csnetworksubnet**を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="c8a49-162">これらのコマンドレットを一緒に使用することで、サブネットの設定をコンマ区切り値 (.csv) ファイルから読み取り、複数のサブネットを同時に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="c8a49-163">.Csv ファイルからサブネットを作成する方法の例については、「[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8a49-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="c8a49-164">ネットワークサブネットを削除するには</span><span class="sxs-lookup"><span data-stu-id="c8a49-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="c8a49-165">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c8a49-166">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c8a49-167">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c8a49-168">[ **Subnet** ] ページで、削除するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="c8a49-169">一度に複数のサブネットを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c8a49-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="c8a49-170">これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数のサブネットを選択します。</span><span class="sxs-lookup"><span data-stu-id="c8a49-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="c8a49-171">または、すべてのサブネットを選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="c8a49-172">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="c8a49-173">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c8a49-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="c8a49-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8a49-174">See Also</span></span>

[<span data-ttu-id="c8a49-175">新しい-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c8a49-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="c8a49-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c8a49-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="c8a49-177">CsNetworkSubnet の削除</span><span class="sxs-lookup"><span data-stu-id="c8a49-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="c8a49-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c8a49-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
