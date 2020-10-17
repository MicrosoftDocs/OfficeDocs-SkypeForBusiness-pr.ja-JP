---
title: 'Lync Server 2013: ネットワークサブネットの作成または変更'
description: 'Lync Server 2013: ネットワークサブネットを作成または変更します。'
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
ms.openlocfilehash: 37695707bf39b10c351a4990b132c9799406f9c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546923"
---
# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="561aa-103">Lync Server 2013 でのネットワークサブネットの作成または変更</span><span class="sxs-lookup"><span data-stu-id="561aa-103">Create or modify network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="561aa-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="561aa-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="561aa-105">ネットワーク サブネットは、そのサブネットに所属するホストの地理的な場所を指定するために、ネットワーク サイトに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="561aa-105">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="561aa-106">Lync Server コントロールパネルを使用して、サブネットを構成できます。</span><span class="sxs-lookup"><span data-stu-id="561aa-106">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="561aa-107">Lync Server コントロールパネルから、ネットワークサブネットを作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="561aa-107">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="561aa-108">ネットワークサブネットの削除の詳細については、「 [Lync Server 2013 でのネットワークサブネットの削除](lync-server-2013-deleting-network-subnets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="561aa-108">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="561aa-109">通話受付管理 (CAC) が実装されている Microsoft Lync Server 2013 のほとんどの展開では、通常、多くのサブネットがあります。</span><span class="sxs-lookup"><span data-stu-id="561aa-109">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="561aa-110">このため、多くの場合、Lync Server 管理シェルからサブネットを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="561aa-110">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="561aa-111">そこから、Windows PowerShell コマンドレットの**Import-CSV**と共に、**新しい-csnetworksubnet**を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="561aa-111">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="561aa-112">これらのコマンドレットを使用すると、コンマ区切り値 (.csv) ファイルからサブネット設定を読み込み、同時に複数のサブネットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="561aa-112">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="561aa-113">csv ファイルからサブネットを作成する方法の例については、「[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="561aa-113">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="561aa-114">ネットワーク サブネットを作成するには</span><span class="sxs-lookup"><span data-stu-id="561aa-114">To create a network subnet</span></span>

1.  <span data-ttu-id="561aa-115">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="561aa-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="561aa-116">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="561aa-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="561aa-117">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="561aa-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="561aa-118">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561aa-118">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="561aa-119">[**サブネット**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561aa-119">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="561aa-p104">[**新しいサブネット**] で、[**サブネット ID**] フィールドに値を入力します。 これは、IP アドレス (174.11.12.0 など) である必要があります。また、サブネットで定義される IP アドレス範囲の最初のアドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="561aa-p104">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="561aa-122">[**マスク**] フィールドで、1 ～ 32 の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="561aa-122">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="561aa-123">この値は、作成するサブネットに適用するビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="561aa-123">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="561aa-124">[**ネットワーク サイト ID**] で、このサブネットが所属するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="561aa-124">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="561aa-125">(オプション) [**説明**] フィールドに値を入力して、名前だけでは表現することのできないこのサブネットの詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="561aa-125">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="561aa-126">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561aa-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="561aa-127">ネットワーク サブネットを変更するには</span><span class="sxs-lookup"><span data-stu-id="561aa-127">To modify a network subnet</span></span>

1.  <span data-ttu-id="561aa-128">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="561aa-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="561aa-129">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="561aa-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="561aa-130">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="561aa-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="561aa-131">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561aa-131">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="561aa-132">[**サブネット**] ページで、変更するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="561aa-132">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="561aa-133">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561aa-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="561aa-p106">[**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワーク サイト、または説明を変更できます。 ビットマスクを変更する場合は、変更後もサブネット ID がサブネットで定義される IP アドレス範囲の最初のアドレスでなければならないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="561aa-p106">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="561aa-136">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="561aa-136">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="561aa-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="561aa-137">See Also</span></span>


[<span data-ttu-id="561aa-138">Lync Server 2013 でのネットワークサブネットの削除</span><span class="sxs-lookup"><span data-stu-id="561aa-138">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="561aa-139">Lync Server 2013 のネットワーク地域、サイト、およびサブネットについて</span><span class="sxs-lookup"><span data-stu-id="561aa-139">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="561aa-140">新しい-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="561aa-140">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="561aa-141">設定-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="561aa-141">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="561aa-142">-CsNetworkSubnet の削除</span><span class="sxs-lookup"><span data-stu-id="561aa-142">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="561aa-143">-CsNetworkSubnet の取得</span><span class="sxs-lookup"><span data-stu-id="561aa-143">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

