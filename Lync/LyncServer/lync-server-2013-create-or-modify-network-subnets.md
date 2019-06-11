---
title: 'Lync Server 2013: ネットワークサブネットを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27088b59745bac580990b3e898f485d34dcad57
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="22546-102">Lync Server 2013 でネットワークサブネットを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="22546-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22546-103">_**最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="22546-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="22546-104">ネットワークサブネットは、このサブネットに属しているホストの地理的な場所を判断するために、ネットワークサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="22546-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="22546-105">Lync Server コントロールパネルを使用して、サブネットを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="22546-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="22546-106">Lync Server コントロールパネルから、ネットワークサブネットの作成、変更、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="22546-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="22546-107">ネットワークサブネットの削除の詳細については、「 [Lync Server 2013 でのネットワークサブネットの削除](lync-server-2013-deleting-network-subnets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22546-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="22546-108">通話受付制御 (CAC) が実装されている Microsoft Lync Server 2013 の大半の展開では、通常、多数のサブネットが存在します。</span><span class="sxs-lookup"><span data-stu-id="22546-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="22546-109">このため、多くの場合、Lync Server 管理シェルからサブネットを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22546-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="22546-110">そこから、Windows PowerShell コマンドレットの**Import-CSV**と組み合わせて、**新しい csnetworksubnet**を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="22546-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="22546-111">これらのコマンドレットを一緒に使用することで、サブネットの設定をコンマ区切り値 (.csv) ファイルから読み取り、複数のサブネットを同時に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="22546-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="22546-112">.Csv ファイルからサブネットを作成する方法の例については、「[新しい-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22546-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="22546-113">ネットワークサブネットを作成するには</span><span class="sxs-lookup"><span data-stu-id="22546-113">To create a network subnet</span></span>

1.  <span data-ttu-id="22546-114">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="22546-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22546-115">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="22546-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22546-116">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="22546-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="22546-117">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22546-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="22546-118">[**サブネット**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22546-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="22546-119">[**新しいサブネット**] で、[**サブネット ID** ] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="22546-119">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="22546-120">これは IP アドレス (たとえば、174.11.12.0) である必要があり、サブネットで定義された IP アドレス範囲の最初のアドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="22546-120">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="22546-121">[**マスク**] フィールドに、1 ~ 32 の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="22546-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22546-122">この値は、作成されるサブネットに適用されるビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="22546-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="22546-123">[**ネットワークサイト ID**] で、このサブネットが所属するサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="22546-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="22546-124">省略[**説明**] フィールドに値を入力して、このサブネットについて、名前だけでは表現できない詳細情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="22546-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="22546-125">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22546-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="22546-126">ネットワークサブネットを変更するには</span><span class="sxs-lookup"><span data-stu-id="22546-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="22546-127">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="22546-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22546-128">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="22546-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22546-129">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="22546-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="22546-130">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サブネット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22546-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="22546-131">[ **Subnet** ] ページで、変更するサブネットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="22546-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="22546-132">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22546-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="22546-133">[**サブネットの編集**] ページでは、ビットマスク、関連付けられたネットワークサイト、または説明を変更できます。</span><span class="sxs-lookup"><span data-stu-id="22546-133">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="22546-134">ビットマスクを変更する場合は、サブネット ID が、サブネットで定義されている IP アドレス範囲の最初のアドレスである必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22546-134">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="22546-135">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22546-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="22546-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="22546-136">See Also</span></span>


[<span data-ttu-id="22546-137">Lync Server 2013 でのネットワークサブネットの削除</span><span class="sxs-lookup"><span data-stu-id="22546-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="22546-138">Lync Server 2013 ネットワーク領域、サイト、およびサブネットの構成</span><span class="sxs-lookup"><span data-stu-id="22546-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="22546-139">新しい-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="22546-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="22546-140">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="22546-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="22546-141">CsNetworkSubnet の削除</span><span class="sxs-lookup"><span data-stu-id="22546-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="22546-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="22546-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

