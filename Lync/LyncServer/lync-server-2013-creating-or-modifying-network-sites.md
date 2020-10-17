---
title: 'Lync Server 2013: ネットワークサイトの作成または変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c88ca28478cbd9d38e9e85c5a852fb93b49c0df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516724"
---
# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="3e763-102">Lync Server 2013 でのネットワークサイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="3e763-102">Creating or modifying network sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e763-103">_**トピックの最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="3e763-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="3e763-104">ネットワーク サイトは、通話受付管理 (CAC) または Enhanced 9-1-1 展開の各地域内で構成されるオフィスまたは拠点です。</span><span class="sxs-lookup"><span data-stu-id="3e763-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="3e763-105">Microsoft Lync Server 2013 コントロールパネルを使用して、サイトを構成し、それらを地域に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="3e763-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="3e763-106">たとえば、北アメリカのネットワーク地域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="3e763-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="3e763-107">CAC ネットワーク サイトは、サイトに帯域幅制限がない場合でも、組織内の各サイトに作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e763-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="3e763-108">Lync Server コントロールパネルから、ネットワークサイトの作成、変更、および削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3e763-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="3e763-109">ネットワーク サイトを作成または変更するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="3e763-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="3e763-110">既存のネットワークサイトの削除の詳細については、「 [Lync Server 2013 での既存のネットワークサイトの削除](lync-server-2013-deleting-an-existing-network-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e763-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="3e763-111">ネットワーク サイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="3e763-111">To create a network site</span></span>

1.  <span data-ttu-id="3e763-112">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e763-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e763-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e763-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e763-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e763-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e763-115">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="3e763-116">[**サイト**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="3e763-117">[**新しいサイト**] で、[**名前**] フィールドにサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3e763-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e763-118">サイト名は、Lync Server 2013 展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e763-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="3e763-119">[**地域**] ドロップダウン リストで、このサイトに関連付けるネットワーク地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="3e763-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="3e763-120">(オプション) このサイトに対する音声またはビデオ通話に帯域幅制限を設定する場合は、[**帯域幅ポリシー**] ドロップダウン リストで該当する設定値を備える帯域幅ポリシー プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e763-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e763-121">[<STRONG>ネットワーク構成</STRONG>] グループの [<STRONG>ポリシーのプロファイル</STRONG>] ページでは、利用可能な帯域幅ポリシー プロファイルの詳細を表示したり、新しい帯域幅ポリシー プロファイルを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="3e763-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="3e763-122">詳細については、「 <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Lync Server 2013 での帯域幅ポリシープロファイルの作成または変更</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e763-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="3e763-123">(オプション) このサイトに、場所に関する設定を提供する場合は、[**場所のポリシー**] ドロップダウン リストで場所のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e763-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e763-124">場所のポリシーは、特定の Enhanced 9-1-1 (E9-1-1) とクライアントの場所に関連する設定をサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3e763-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="3e763-125">[<STRONG>ネットワーク構成</STRONG>] グループの [<STRONG>場所のポリシー</STRONG>] ページでは、利用可能な場所のポリシーの詳細を表示したり、新しい場所のポリシーを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="3e763-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="3e763-126">詳細については、「 <A href="lync-server-2013-viewing-location-policy-information.md">Lync Server 2013 で場所ポリシー情報を表示</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e763-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="3e763-127">(オプション) [**説明**] フィールドに値を入力して、名前だけでは表現することのできないこのサイトの詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3e763-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="3e763-128">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e763-129">新しいネットワーク サイトを作成するとき、[<STRONG>関連付けられたサブネット</STRONG>] テーブルは使用しません。</span><span class="sxs-lookup"><span data-stu-id="3e763-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="3e763-130">サブネットの作成または変更時に、サブネットをサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="3e763-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="3e763-131">詳細については、「 <A href="lync-server-2013-create-or-modify-network-subnets.md">Lync Server 2013 でネットワークサブネットを作成または変更する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e763-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="3e763-132">ネットワーク サイトを変更するには</span><span class="sxs-lookup"><span data-stu-id="3e763-132">To modify a network site</span></span>

1.  <span data-ttu-id="3e763-133">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e763-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e763-134">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e763-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e763-135">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e763-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e763-136">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="3e763-137">[**サイト**] ページで、変更するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="3e763-138">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="3e763-p107">[**サイトの編集**] ページでは、サイトに関連付けられた、説明、地域、帯域幅ポリシー プロファイル、および場所のポリシーを変更できます。詳細については、このトピックの「ネットワーク サイトを作成するには」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e763-p107">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site. For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="3e763-141">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-141">Click **Commit**.</span></span>

<span data-ttu-id="3e763-p108">このページの [**関連付けられたサブネット**] テーブルを変更することはできません。 関連付けられたサブネットの一覧は、参照のために用意されており、サイトの設定を変えるとどのサブネットが影響を受けるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3e763-p108">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="3e763-144">ネットワーク サイトを削除するには</span><span class="sxs-lookup"><span data-stu-id="3e763-144">To delete a network site</span></span>

1.  <span data-ttu-id="3e763-145">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3e763-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e763-146">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3e763-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e763-147">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e763-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e763-148">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="3e763-149">[**サイト**] ページで、削除するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3e763-p110">1 つ以上のサイトを一度に削除できます。 これを実行するには、Ctrl キーを押しながら、複数のサイトを選択します。 また、すべてのサイトを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-p110">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="3e763-153">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="3e763-154">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3e763-p111">ただし、ネットワーク サイトがネットワーク サブネットに関連付けられている場合は、サイトを削除することはできません。 サブネットに関連付けられているサイトを削除しようとすると、エラー メッセージが表示されます。 サイトがサブネットに関連付けられているかどうかを確認するには、そのサイトをクリックして、[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e763-p111">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e763-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e763-158">See Also</span></span>


[<span data-ttu-id="3e763-159">Lync Server 2013 での既存のネットワークサイトの削除</span><span class="sxs-lookup"><span data-stu-id="3e763-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="3e763-160">新しい-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3e763-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="3e763-161">設定-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="3e763-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="3e763-162">-CsNetworkSite の削除</span><span class="sxs-lookup"><span data-stu-id="3e763-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="3e763-163">-CsNetworkSite の取得</span><span class="sxs-lookup"><span data-stu-id="3e763-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

