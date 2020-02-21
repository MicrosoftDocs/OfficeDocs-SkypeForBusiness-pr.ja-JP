---
title: 'Lync Server 2013: ネットワークサブネットの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1eafbf7322fadd8d0373d3f2c40a0f495928c98
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="bf3c2-102">Lync Server 2013 でのネットワークサブネットの作成または変更</span><span class="sxs-lookup"><span data-stu-id="bf3c2-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf3c2-103">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="bf3c2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="bf3c2-104">ネットワーク サブネットは、そのサブネットに所属するホストの地理的な場所を指定するために、ネットワーク サイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="bf3c2-105">Lync Server コントロールパネルを使用して、サブネットを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="bf3c2-106">Lync Server コントロールパネルから、ネットワークサブネットを作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="bf3c2-107">ネットワークサブネットの削除の詳細については、「 [Lync Server 2013 でのネットワークサブネットの削除](lync-server-2013-deleting-network-subnets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="bf3c2-108">通話受付管理 (CAC) が実装されている Microsoft Lync Server 2013 のほとんどの展開では、通常、多くのサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="bf3c2-109">このため、多くの場合、Lync Server 管理シェルからサブネットを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="bf3c2-110">そこから、Windows PowerShell コマンドレットの**Import-CSV**と共に、**新しい-csnetworksubnet**を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="bf3c2-111">これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="bf3c2-112">csv ファイルからサブネットを作成する方法の例については、「[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="bf3c2-113">ネットワーク サブネットを作成するには</span><span class="sxs-lookup"><span data-stu-id="bf3c2-113">To create a network subnet</span></span>

1.  <span data-ttu-id="bf3c2-114">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bf3c2-115">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bf3c2-116">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bf3c2-117">左側のナビゲーション バーで [**ネットワーク構成**]、[**サブネット**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="bf3c2-118">[**サブネット**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="bf3c2-p104">[**新しいサブネット**] で、[**サブネット ID**] フィールドに値を入力します。 これは、IP アドレス (174.11.12.0 など) である必要があります。また、サブネットで定義される IP アドレス範囲の最初のアドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-p104">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="bf3c2-121">[**マスク**] フィールドで、1 ～ 32 の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf3c2-122">この値は、作成するサブネットに適用するビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="bf3c2-123">[**ネットワーク サイト ID**] で、このサブネットが所属するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="bf3c2-124">(オプション) [**説明**] フィールドに値を入力して、名前だけでは表現することのできないこのサブネットの詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="bf3c2-125">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="bf3c2-126">ネットワーク サブネットを変更するには</span><span class="sxs-lookup"><span data-stu-id="bf3c2-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="bf3c2-127">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bf3c2-128">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bf3c2-129">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bf3c2-130">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="bf3c2-131">[**サブネット**] ページで、変更するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="bf3c2-132">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="bf3c2-p106">[**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワーク サイト、または説明を変更できます。 ビットマスクを変更する場合は、変更後もサブネット ID がサブネットで定義される IP アドレス範囲の最初のアドレスでなければならないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-p106">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="bf3c2-135">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf3c2-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf3c2-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf3c2-136">See Also</span></span>


[<span data-ttu-id="bf3c2-137">Lync Server 2013 でのネットワークサブネットの削除</span><span class="sxs-lookup"><span data-stu-id="bf3c2-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="bf3c2-138">Lync Server 2013 のネットワーク地域、サイト、およびサブネットについて</span><span class="sxs-lookup"><span data-stu-id="bf3c2-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="bf3c2-139">新しい-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="bf3c2-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="bf3c2-140">設定-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="bf3c2-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="bf3c2-141">-CsNetworkSubnet の削除</span><span class="sxs-lookup"><span data-stu-id="bf3c2-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="bf3c2-142">-CsNetworkSubnet の取得</span><span class="sxs-lookup"><span data-stu-id="bf3c2-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

