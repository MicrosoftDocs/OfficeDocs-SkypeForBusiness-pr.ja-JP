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
ms.openlocfilehash: 4c77c343bff92e25ffc1678bc06e7a0ef05d3f96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="003f9-102">Lync Server 2013 でのネットワークサイトの作成または変更</span><span class="sxs-lookup"><span data-stu-id="003f9-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="003f9-103">_**最終更新日:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="003f9-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="003f9-104">[ネットワークサイト] は、通話受付制御 (CAC) または拡張9-1-1 展開の各領域内に構成されているオフィスまたは場所です。</span><span class="sxs-lookup"><span data-stu-id="003f9-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="003f9-105">Microsoft Lync Server 2013 コントロールパネルを使用して、サイトを構成し、それらを地域と関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="003f9-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="003f9-106">たとえば、北米向けのネットワーク領域は、シカゴ、Redmond、バンクーバーなどのネットワークサイトに関連付けられている場合があります。</span><span class="sxs-lookup"><span data-stu-id="003f9-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="003f9-107">サイト内のすべてのサイトに対して、CAC ネットワークサイトを作成する必要があります。このサイトには帯域幅の制限がありません。</span><span class="sxs-lookup"><span data-stu-id="003f9-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="003f9-108">Lync Server コントロールパネルからネットワークサイトの作成、変更、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="003f9-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="003f9-109">ネットワークサイトを作成または変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="003f9-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="003f9-110">既存のネットワークサイトを削除する方法について詳しくは、「 [Lync Server 2013 で既存のネットワークサイトを削除する](lync-server-2013-deleting-an-existing-network-site.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="003f9-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="003f9-111">ネットワークサイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="003f9-111">To create a network site</span></span>

1.  <span data-ttu-id="003f9-112">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="003f9-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="003f9-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="003f9-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="003f9-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="003f9-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="003f9-115">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="003f9-116">[**サイト**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="003f9-117">[**新しいサイト**] の [**名前**] フィールドに、このサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="003f9-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="003f9-118">サイト名は、Lync Server 2013 の展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="003f9-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="003f9-119">[ **Region** ] ドロップダウンリストで、このサイトに関連付けるネットワーク領域を選びます。</span><span class="sxs-lookup"><span data-stu-id="003f9-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="003f9-120">省略このサイトへの音声通話またはビデオ通話に帯域幅の制限を設定する場合は、[**帯域幅ポリシー** ] ドロップダウンリストから適切な設定を使用して、帯域幅ポリシーのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="003f9-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="003f9-121">利用可能な帯域幅ポリシープロファイルの詳細を表示したり、新しい帯域幅ポリシープロファイルを作成したりするには、[<STRONG>ネットワーク構成</STRONG>] グループの [<STRONG>ポリシープロファイル</STRONG>] ページを使用します。</span><span class="sxs-lookup"><span data-stu-id="003f9-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="003f9-122">詳細について<A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">は、「Lync Server 2013 で帯域幅ポリシープロファイルを作成または変更する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="003f9-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="003f9-123">省略このサイトの場所の設定を指定する場合は、[**場所のポリシー** ] ドロップダウンリストから場所のポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="003f9-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="003f9-124">位置情報ポリシーは、特定の拡張 9-1-1 (E9) およびクライアントの場所の設定をサイトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="003f9-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="003f9-125">利用可能な位置情報ポリシーの詳細を表示するか、[<STRONG>ネットワーク構成</STRONG>] グループの [<STRONG>場所のポリシー</STRONG> ] ページから新しい場所ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="003f9-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="003f9-126">詳細については、「 <A href="lync-server-2013-viewing-location-policy-information.md">Lync Server 2013 で位置情報ポリシー情報を表示</A>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="003f9-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="003f9-127">省略[**説明**] フィールドに値を入力して、このサイトについて、名前だけでは表現できない詳細情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="003f9-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="003f9-128">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="003f9-129">新しいネットワークサイトを作成する場合は、<STRONG>関連するサブネット</STRONG>テーブルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="003f9-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="003f9-130">サブネットを作成または変更するときに、サブネットをサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="003f9-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="003f9-131">詳細については、「 <A href="lync-server-2013-create-or-modify-network-subnets.md">Lync Server 2013 でネットワークサブネットを作成または変更する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="003f9-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="003f9-132">ネットワークサイトを変更するには</span><span class="sxs-lookup"><span data-stu-id="003f9-132">To modify a network site</span></span>

1.  <span data-ttu-id="003f9-133">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="003f9-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="003f9-134">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="003f9-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="003f9-135">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="003f9-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="003f9-136">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="003f9-137">[**サイト**] ページで、変更するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="003f9-138">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="003f9-139">[**サイトの編集**] ページでは、サイトに関連付けられている説明、地域、帯域幅ポリシーのプロファイル、および場所のポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="003f9-139">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="003f9-140">詳細については、このトピックの前半の「ネットワークサイトを作成する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="003f9-140">For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="003f9-141">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-141">Click **Commit**.</span></span>

<span data-ttu-id="003f9-142">このページでは、**関連するサブネット**テーブルを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="003f9-142">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="003f9-143">関連付けられたサブネットの一覧は参照用に提供されるため、サイトの設定を変更したときに影響を受けるサブネットを認識できます。</span><span class="sxs-lookup"><span data-stu-id="003f9-143">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="003f9-144">ネットワークサイトを削除するには</span><span class="sxs-lookup"><span data-stu-id="003f9-144">To delete a network site</span></span>

1.  <span data-ttu-id="003f9-145">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="003f9-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="003f9-146">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="003f9-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="003f9-147">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="003f9-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="003f9-148">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="003f9-149">[**サイト**] ページで、削除するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="003f9-150">一度に複数のサイトを削除できます。</span><span class="sxs-lookup"><span data-stu-id="003f9-150">You can delete more than one site at a time.</span></span> <span data-ttu-id="003f9-151">この操作を行うには、ctrl キーを押しながら複数のサイトを選び、CTRL キーを押しながら選択します。</span><span class="sxs-lookup"><span data-stu-id="003f9-151">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="003f9-152">または、すべてのサイトを選択するには、[<STRONG>編集</STRONG>] メニューの [<STRONG>すべて選択</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-152">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="003f9-153">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="003f9-154">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="003f9-155">ネットワークサイトがネットワークサブネットに関連付けられている場合は、そのサイトを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="003f9-155">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="003f9-156">サブネットに関連付けられているサイトを削除しようとすると、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="003f9-156">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="003f9-157">サイトがいずれかのサブネットに関連付けられているかどうかを確認するには、サイトをクリックし、[<STRONG>編集</STRONG>] メニューの [<STRONG>詳細の表示</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="003f9-157">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="003f9-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="003f9-158">See Also</span></span>


[<span data-ttu-id="003f9-159">Lync Server 2013 で既存のネットワークサイトを削除する</span><span class="sxs-lookup"><span data-stu-id="003f9-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="003f9-160">新しい-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="003f9-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="003f9-161">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="003f9-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="003f9-162">CsNetworkSite の削除</span><span class="sxs-lookup"><span data-stu-id="003f9-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="003f9-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="003f9-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

