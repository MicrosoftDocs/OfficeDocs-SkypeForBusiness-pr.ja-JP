---
title: 'Lync Server 2013: ネットワーク サイトとサブネットの関連付け'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec5a896af6312fecf53259ac10e72f99598d4a7e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a><span data-ttu-id="5181a-102">Lync Server 2013 でのネットワーク サイトとサブネットの関連付け</span><span class="sxs-lookup"><span data-stu-id="5181a-102">Associate a subnet with a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5181a-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="5181a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="5181a-104">ネットワーク内のすべてのサブネットは、新しいセッションが開始されている間、エンドポイントが配置されているネットワークサイトを特定するために使用されるため、サブネット情報が特定のネットワークサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5181a-104">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="5181a-105">セッションの各パーティの場所がわかっている場合は、高度なエンタープライズ音声機能を使用して、通話の設定またはルーティングを処理する方法を決定するためにその情報を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="5181a-105">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5181a-106">展開内の音声ビデオ エッジ サーバーの構成済みパブリック IP アドレスはすべて、ネットワーク構成設定に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5181a-106">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="5181a-107">これらの IP アドレスは、マスク値 32 のサブネットとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="5181a-107">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="5181a-108">関連付けられたネットワーク サイトは、適切な構成済みネットワーク サイトに対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5181a-108">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="5181a-109">たとえば、セントラルサイトシカゴの A/V エッジサーバーに対応するパブリック IP アドレスは、NetworkSiteID シカゴになります。</span><span class="sxs-lookup"><span data-stu-id="5181a-109">For example, the public IP address that corresponds to the A/V Edge Server in central site Chicago would be NetworkSiteID Chicago.</span></span> <span data-ttu-id="5181a-110">パブリック IP アドレスの詳細については、計画ドキュメントの「 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5181a-110">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5181a-p103">主要状態インジケーター (KHI) 通知が発行され、ネットワークに存在している IP アドレスの一覧を指定します。ここで指定される IP アドレスは、サブネットと関連付けられていないか、IP アドレスを含むサブネットがネットワーク サイトと関連付けられていません。この通知は 8 時間に 1 回以上は発行されません。関連する通知の情報および例は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5181a-p103">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8-hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="5181a-114"><STRONG>ソース:</STRONG>CS 帯域幅ポリシーサービス (コア)</span><span class="sxs-lookup"><span data-stu-id="5181a-114"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="5181a-115"><STRONG>イベント番号:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="5181a-115"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="5181a-116"><STRONG>レベル:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="5181a-116"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="5181a-117"><STRONG>説明:</STRONG>次の IP アドレスのサブネット: &lt;ip アドレス&gt;の一覧が構成されていないか、サブネットがネットワークサイトに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="5181a-117"><STRONG>Description:</STRONG> The subnets for the following IP addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a Network Site.</span></span><BR><span data-ttu-id="5181a-118"><STRONG>原因:</STRONG>対応する IP アドレスのサブネットがネットワーク構成の設定で見つからないか、サブネットがネットワークサイトに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="5181a-118"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="5181a-119"><STRONG>解像度:</STRONG>IP アドレスのリストに対応するサブネットをネットワーク構成の設定に追加し、すべてのサブネットをネットワークサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5181a-119"><STRONG>Resolution:</STRONG> Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="5181a-p104">たとえば、通知に表示された IP アドレス リストが 10.121.248.226 および 10.121.249.20 であった場合、これらの IP アドレスがサブネットに関連付けられていないか、または関連付けられているサブネットがネットワーク サイトに属していないかのどちらかになります。10.121.248.0/24 および 10.121.249.0/24 がこれらのアドレスに対応するサブネットである場合、次の手順でこの問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="5181a-p104">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="5181a-122">IP アドレス 10.121.248.226 が 10.121.248.0/24 サブネットに関連付けられていること、および IP アドレス 10.121.249.20 が 10.121.249.0/24 サブネットに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5181a-122">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
> <LI>
> <P><span data-ttu-id="5181a-123">10.121.248.0/24 および 10.121.249.0/24 サブネットがそれぞれネットワーク サイトに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5181a-123">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>



</div>

<span data-ttu-id="5181a-124">ネットワークサブネットの操作の詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5181a-124">For details about working with network subnets, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="5181a-125">新しい-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5181a-125">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [<span data-ttu-id="5181a-126">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5181a-126">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [<span data-ttu-id="5181a-127">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="5181a-127">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [<span data-ttu-id="5181a-128">CsNetworkSubnet の削除</span><span class="sxs-lookup"><span data-stu-id="5181a-128">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> <span data-ttu-id="5181a-129">多数のサブネットを使用している場合は、コンマ区切り値 (CSV) ファイルを使用してサブネットをサイトに関連付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5181a-129">If you are working with a large number of subnets, we recommend using a comma-separated values (CSV) file to associate the subnets to sites.</span></span> <span data-ttu-id="5181a-130">CSV ファイルには、 <STRONG>IPAddress</STRONG>、 <STRONG>mask</STRONG>、 <STRONG>description</STRONG>、 <STRONG>networksiteid</STRONG>の4つの列が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5181a-130">The CSV file must have the following four columns: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span></span>



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a><span data-ttu-id="5181a-131">管理シェルを使用してサブネットをネットワークサイトに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="5181a-131">To associate a subnet with a network site by using Management Shell</span></span>

1.  <span data-ttu-id="5181a-132">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5181a-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5181a-133">**New-CsNetworkSubnet** コマンドレットを実行して、サブネットをネットワーク サイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5181a-133">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    <span data-ttu-id="5181a-134">例:</span><span class="sxs-lookup"><span data-stu-id="5181a-134">For example:</span></span>
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    <span data-ttu-id="5181a-135">この例では、サブネットの 172.11.12.13 とネットワーク サイトの "Chicago" 間の関連付けが作成されました。</span><span class="sxs-lookup"><span data-stu-id="5181a-135">In this example, you created an association between the subnet 172.11.12.13 and the network site “Chicago”.</span></span>

3.  <span data-ttu-id="5181a-136">トポロジのすべてのサブネットに対して、ステップ 2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5181a-136">Repeat step 2 for all subnets in your topology.</span></span>

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="5181a-137">CSV ファイルをインポートしてサブネットをネットワーク サイトに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="5181a-137">To associate subnets with network sites by importing a CSV file</span></span>

1.  <span data-ttu-id="5181a-p106">追加する予定の、すべてのサブネットが含まれた CSV ファイルを作成します。たとえば、次の内容が含まれる、**subnet.csv** という名前のファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5181a-p106">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  <span data-ttu-id="5181a-140">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5181a-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5181a-141">次のコマンドレットを実行して、**サブネット .csv**をインポートし、その内容を Lync Server 管理ストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="5181a-141">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="5181a-142">Lync Server コントロールパネルを使用してサブネットをネットワークサイトに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="5181a-142">To associate a subnet with a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5181a-143">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5181a-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5181a-144">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5181a-144">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="5181a-145">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5181a-145">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="5181a-146">[**サブネット**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5181a-146">Click the **Subnet** navigation button.</span></span>

4.  <span data-ttu-id="5181a-147">[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5181a-147">Click **New**.</span></span>

5.  <span data-ttu-id="5181a-148">[**新しいサブネット**] ページで、[**サブネット ID**] をクリックし、ネットワーク サイトに関連付けるサブネットで定義される IP アドレス範囲の最初のアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="5181a-148">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6.  <span data-ttu-id="5181a-149">[**マスク**] をクリックし、サブネットに適用するビットマスクを入力します。</span><span class="sxs-lookup"><span data-stu-id="5181a-149">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7.  <span data-ttu-id="5181a-150">[**ネットワーク サイト ID**] をクリックし、このサブネットの追加先となるサイトのサイト ID を選択します。</span><span class="sxs-lookup"><span data-stu-id="5181a-150">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5181a-151">ネットワーク サイトがまだ作成されていない場合、この一覧は空です。</span><span class="sxs-lookup"><span data-stu-id="5181a-151">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="5181a-152">この手順の詳細については、「 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync Server 2013 でネットワークサイトを作成または変更</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5181a-152">For details about the procedure, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="5181a-153">また、<STRONG>Get-CsNetworkSite</STRONG> コマンドレットを実行して、展開のサイト ID を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="5181a-153">You can also retrieve site IDs for your deployment by running the <STRONG>Get-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="5181a-154">詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5181a-154">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="5181a-155">オプションで、[**説明**] をクリックし、このサブネットを説明する追加情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5181a-155">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9.  <span data-ttu-id="5181a-156">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5181a-156">Click **Commit**.</span></span>

<span data-ttu-id="5181a-157">これらのステップを繰り返して、その他のサブネットをネットワーク サイトに追加します。</span><span class="sxs-lookup"><span data-stu-id="5181a-157">Repeat these steps to add other subnets to a network site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

