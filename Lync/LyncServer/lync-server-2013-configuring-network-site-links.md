---
title: 'Lync Server 2013: ネットワークサイトリンクを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ddd5e28cd37cd31e28e5c6427b9b700b5a4c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="dabb7-102">Lync Server 2013 でネットワークサイトリンクを構成する</span><span class="sxs-lookup"><span data-stu-id="dabb7-102">Configuring network site links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dabb7-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dabb7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dabb7-104">通話受付制御 (CAC) 構成では、直接リンクされているサイト間の帯域幅の制限を定義するネットワーク間ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dabb7-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="dabb7-105">ネットワークサイトが直接リンクを共有している場合、オーディオおよびビデオ接続の帯域幅の制限は、これら2つのサイト間で定義できます。</span><span class="sxs-lookup"><span data-stu-id="dabb7-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="dabb7-106">Lync Server コントロールパネルを使ってネットワークサイトポリシーを構成することはできません。これは、Lync Server 管理シェルのコマンドレットを使用することによってのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="dabb7-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="dabb7-107">Lync Server 管理シェルからネットワークサイトリンク (ネットワークのサイト間ポリシーとも呼ばれます) を作成、変更、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="dabb7-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="dabb7-108">ネットワークサイトのリンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="dabb7-108">To create a network site link</span></span>

1.  <span data-ttu-id="dabb7-109">Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dabb7-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dabb7-110">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dabb7-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dabb7-111">コマンドプロンプトで、次のコマンドを入力します。これは、構成に対して有効な値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="dabb7-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="dabb7-112">この例では、Reno とポートランドのネットワーク\_サイト間の帯域幅の制限を設定する Reno ポートランドという名前の新しいネットワークサイトリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="dabb7-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="dabb7-113">このコマンドを実行する前に、ネットワークサイトと帯域幅ポリシーのプロファイルが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="dabb7-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="dabb7-114">パラメーターの詳細については、「Lync Server Management Shell ドキュメントの[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dabb7-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="dabb7-115">ネットワークサイトリンクに適用できる帯域幅ポリシープロファイルの一覧を取得するには、 **CsNetworkBandwidthPolicyProfile**コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dabb7-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="dabb7-116">詳細については、「Lync Server 管理シェルドキュメントの[CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dabb7-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="dabb7-117">ネットワークサイトのリンクを変更するには</span><span class="sxs-lookup"><span data-stu-id="dabb7-117">To modify a network site link</span></span>

1.  <span data-ttu-id="dabb7-118">Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dabb7-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dabb7-119">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dabb7-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dabb7-120">指定のネットワークサイトリンクのプロパティを変更するには、 **CsNetworkInterSitePolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dabb7-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="dabb7-121">いずれか (または両方) または接続されたサイトを変更することができます。また、リンクに関連付けられている帯域幅ポリシープロファイルを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="dabb7-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="dabb7-122">Reno\_ポートランドという名前のサイトリンクの帯域幅ポリシープロファイルを変更する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dabb7-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="dabb7-123">パラメーターの詳細については、「Lync Server Management Shell ドキュメントの[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dabb7-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="dabb7-124">ネットワークサイトのリンクを削除するには</span><span class="sxs-lookup"><span data-stu-id="dabb7-124">To delete a network site link</span></span>

1.  <span data-ttu-id="dabb7-125">Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dabb7-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dabb7-126">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dabb7-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dabb7-127">ネットワークサイトへのリンクを削除するには、 **CsNetworkInterSitePolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dabb7-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="dabb7-128">次の例では、\_Reno ポートランドネットワークサイトのリンクを削除します。</span><span class="sxs-lookup"><span data-stu-id="dabb7-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="dabb7-129">パラメーターの詳細については、「Lync Server Management Shell ドキュメントの[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dabb7-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dabb7-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="dabb7-130">See Also</span></span>


[<span data-ttu-id="dabb7-131">Lync Server 2013 での通話受付制御コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dabb7-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="dabb7-132">新規-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dabb7-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="dabb7-133">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dabb7-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="dabb7-134">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dabb7-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="dabb7-135">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="dabb7-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="dabb7-136">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="dabb7-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

