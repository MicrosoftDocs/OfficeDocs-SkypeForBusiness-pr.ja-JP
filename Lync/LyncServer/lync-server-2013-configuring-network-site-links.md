---
title: 'Lync Server 2013: ネットワークサイトリンクの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33461781f0392d0e6e4fbfa21bdde8948e7a9a1e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532584"
---
# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="26a80-102">Lync Server 2013 でのネットワークサイトリンクの構成</span><span class="sxs-lookup"><span data-stu-id="26a80-102">Configuring network site links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26a80-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="26a80-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="26a80-104">通話受付管理 (CAC) 構成内で、直接リンクされたサイト間の帯域幅制限を定義するネットワークサイト間ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="26a80-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="26a80-105">ネットワーク サイトが直接リンクを共有している場合、これらの 2 つのサイト間にオーディオ接続およびビデオ接続の帯域幅制限を定義できます。</span><span class="sxs-lookup"><span data-stu-id="26a80-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="26a80-106">Lync Server コントロールパネルを使用してネットワークサイトポリシーを構成することはできません。これを行うには、Lync Server 管理シェルのコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26a80-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="26a80-107">Lync Server 管理シェルから、ネットワークサイトリンク (ネットワークサイト間ポリシーとも呼ばれます) を作成、変更、および削除することができます。</span><span class="sxs-lookup"><span data-stu-id="26a80-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="26a80-108">ネットワーク サイト リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="26a80-108">To create a network site link</span></span>

1.  <span data-ttu-id="26a80-109">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="26a80-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="26a80-110">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a80-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="26a80-111">コマンド プロンプトで、使用している構成で有効な値に置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="26a80-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="26a80-112">この例では、 \_ リノとポートランドのネットワークサイト間の帯域幅制限を設定するリノポートランドという名前の新しいネットワークサイトリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="26a80-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="26a80-113">ネットワーク サイトと帯域幅ポリシーのプロファイルが、このコマンドを実行する前に既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="26a80-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="26a80-114">パラメーターの詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26a80-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="26a80-115">ネットワーク サイト リンクに適用できる帯域幅ポリシーのプロファイルの一覧を取得するには、**Get-CsNetworkBandwidthPolicyProfile** コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="26a80-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="26a80-116">詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26a80-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="26a80-117">ネットワーク サイト リンクを変更するには</span><span class="sxs-lookup"><span data-stu-id="26a80-117">To modify a network site link</span></span>

1.  <span data-ttu-id="26a80-118">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="26a80-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="26a80-119">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a80-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="26a80-120">特定のネットワーク サイト リンクのプロパティを変更するには、**Set-CsNetworkInterSitePolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="26a80-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="26a80-121">接続されたサイトの一方 (または両方) を変更したり、リンクに関連付けられた帯域幅ポリシーのプロファイルを変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="26a80-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="26a80-122">ここでは、リノポートランドという名前のサイトリンクの帯域幅ポリシープロファイルを変更する例を示し \_ ます。</span><span class="sxs-lookup"><span data-stu-id="26a80-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="26a80-123">パラメーターの説明の詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26a80-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="26a80-124">ネットワーク サイト リンクを削除するには</span><span class="sxs-lookup"><span data-stu-id="26a80-124">To delete a network site link</span></span>

1.  <span data-ttu-id="26a80-125">Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="26a80-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="26a80-126">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="26a80-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="26a80-127">ネットワーク サイト リンクを削除するには、**Remove-CsNetworkInterSitePolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="26a80-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="26a80-128">次の例では、リノ \_ ポートランドネットワークサイトリンクを削除します。</span><span class="sxs-lookup"><span data-stu-id="26a80-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="26a80-129">パラメーターの詳細については、「Lync Server Management Shell」のドキュメントの「 [get-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26a80-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="26a80-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="26a80-130">See Also</span></span>


[<span data-ttu-id="26a80-131">Lync Server 2013 での通話受付管理のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="26a80-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="26a80-132">Get-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="26a80-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="26a80-133">Get-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="26a80-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="26a80-134">Get-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="26a80-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="26a80-135">Get-csnetworkintersitepolicy</span><span class="sxs-lookup"><span data-stu-id="26a80-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="26a80-136">Get-csnetworkbandwidthpolicyprofile</span><span class="sxs-lookup"><span data-stu-id="26a80-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

