---
title: サイトの呼受付制御を管理します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ネットワーク サイトは、オフィスや受付制御 (CAC)、~ 9-1-1、およびメディア バイ パスの展開の場合は、各ネットワーク地域内の場所を呼び出します。
ms.openlocfilehash: 53140cf03110991f2c757e5d52e30a6c7db1d7de
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199225"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="f4261-103">Skype for Business Server でのサイトの通話受付管理サービスの管理</span><span class="sxs-lookup"><span data-stu-id="f4261-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="f4261-104">ネットワーク サイトは、オフィスや受付制御 (CAC)、~ 9-1-1、およびメディア バイ パスの展開の場合は、各ネットワーク地域内の場所を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f4261-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="f4261-105">ネットワーク サイトの呼受付制御を構成するのには、この資料の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4261-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="f4261-106">ネットワーク サイト リンクを構成します。</span><span class="sxs-lookup"><span data-stu-id="f4261-106">Configure network site links</span></span>

<span data-ttu-id="f4261-107">呼び出し受付制御 (CAC) 構成では、内では、ネットワークに直接リンクされているサイト間の帯域幅の制限を定義するサイト間ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="f4261-108">ネットワークのサイトでは、直接リンクを共有する場合は、これら 2 つのサイト間でオーディオとビデオ接続の帯域幅の制限を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="f4261-109">ネットワーク サイト ポリシーを構成するビジネス サーバーのコントロール パネルの Skype を使用することはできません、これビジネス サーバー管理シェルのコマンドレット、Skype からを使用するだけです。</span><span class="sxs-lookup"><span data-stu-id="f4261-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f4261-110">作成、変更、およびビジネス サーバー管理シェルには、Skype のネットワーク サイト リンク (ネットワーク サイト間ポリシーとも呼ばれます) を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f4261-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="f4261-111">ネットワーク サイト リンクを作成するには</span><span class="sxs-lookup"><span data-stu-id="f4261-111">To create a network site link</span></span>

1.  <span data-ttu-id="f4261-112">RTCUniversalServerAdmins グループのまたは必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f4261-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="f4261-113">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、 **Skype**ビジネス サーバーをクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="f4261-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="f4261-114">コマンド プロンプトで、構成に対して有効な値を代入する、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f4261-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="f4261-115">Reno をという名前の新しいネットワーク サイト リンクを作成する次の使用例\_ポートランド、リノ、ポートランドのネットワーク サイト間で帯域幅の制限を設定します。</span><span class="sxs-lookup"><span data-stu-id="f4261-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="f4261-116">ネットワーク サイトと帯域幅ポリシーのプロファイルが、このコマンドを実行する前に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4261-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="f4261-117">詳細なパラメーターの説明については、[新規 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4261-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="f4261-118">サイトのネットワーク リンクに適用可能な帯域幅ポリシー プロファイルの一覧を取得するには、 **Get CsNetworkBandwidthPolicyProfile**コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f4261-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="f4261-119">詳細については、 [Get CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4261-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="f4261-120">ネットワーク サイト リンクを変更するのには</span><span class="sxs-lookup"><span data-stu-id="f4261-120">To modify a network site link</span></span>

1.  <span data-ttu-id="f4261-121">RTCUniversalServerAdmins グループのまたは必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f4261-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="f4261-122">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、 **Skype**ビジネス サーバーをクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="f4261-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="f4261-123">**セット CsNetworkInterSitePolicy**コマンドレットを使用して、特定のネットワーク サイト リンクのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="f4261-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="f4261-124">いずれか (または両方) を変更することができますか、接続先のサイトがあり、リンクに関連付けられている帯域幅ポリシーのプロファイルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="f4261-125">Reno をという名前のサイト リンクの帯域幅ポリシーのプロファイルを変更する例を次のとおりです\_ポートランド。</span><span class="sxs-lookup"><span data-stu-id="f4261-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="f4261-126">詳細なパラメーターの説明については、[一連の CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4261-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="f4261-127">ネットワーク サイト リンクを削除するには</span><span class="sxs-lookup"><span data-stu-id="f4261-127">To delete a network site link</span></span>

1.  <span data-ttu-id="f4261-128">RTCUniversalServerAdmins グループのまたは必要なユーザー権限を持つメンバーとしてビジネス サーバー管理シェルの Skype がインストールされているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f4261-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="f4261-129">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、 **Skype**ビジネス サーバーをクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="f4261-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="f4261-130">ネットワーク サイト リンクを削除するのに**削除 CsNetworkInterSitePolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4261-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="f4261-131">Reno を削除する例を次\_ポートランド ネットワーク サイト リンク。</span><span class="sxs-lookup"><span data-stu-id="f4261-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="f4261-132">詳細なパラメーターの説明については、[削除 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4261-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="f4261-133">ネットワーク サイトの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f4261-133">View network site information</span></span>

<span data-ttu-id="f4261-134">ネットワーク サイトは、オフィスまたは呼受付制御 (CAC) または拡張 9-1-1 の展開の各領域内で構成されている場所です。</span><span class="sxs-lookup"><span data-stu-id="f4261-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="f4261-135">ビジネス サーバー管理シェルのいずれか、Skype のビジネス サーバーのコントロール パネルまたは、Skype のネットワーク サイトの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="f4261-136">Skype のビジネス サーバーのコントロール パネルのネットワーク サイトの情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="f4261-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="f4261-137">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f4261-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4261-138">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4261-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f4261-139">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f4261-140">[**サイト**] ページで、表示するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="f4261-141">のみ、一度に 1 つのサイトの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="f4261-142">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f4261-143">Windows PowerShell コマンドレットを使用してネットワーク サイトの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f4261-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f4261-144">Windows PowerShell と Get CsNetworkSite コマンドレットを使用してネットワーク サイトの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="f4261-145">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="f4261-146">ネットワーク サイトの情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="f4261-146">To view network site information</span></span>

  - <span data-ttu-id="f4261-147">ネットワークのすべてのサイトに関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f4261-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="f4261-148">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4261-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="f4261-149">詳細については、 [Get CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4261-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="f4261-150">作成またはネットワーク サイトを変更します。</span><span class="sxs-lookup"><span data-stu-id="f4261-150">Create or modify network sites</span></span> 

<span data-ttu-id="f4261-151">ネットワーク サイトは、オフィスまたは呼受付制御 (CAC) または拡張 9-1-1 の展開の各領域内で構成されている場所です。</span><span class="sxs-lookup"><span data-stu-id="f4261-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="f4261-152">サイトを構成し、地域に関連付けるには、ビジネス サーバーのコントロール パネルの Skype を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="f4261-153">たとえば、北アメリカのネットワーク領域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトに関連付けられている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4261-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="f4261-154">CAC ネットワーク サイトは、そのサイトには、帯域幅の制限があるない場合でも、組織内のすべてのサイトを作成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f4261-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="f4261-155">ビジネス サーバーのコントロール パネルの Skype から作成、変更、およびネットワークのサイトを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f4261-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="f4261-156">作成またはネットワーク サイトを変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4261-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="f4261-157">ネットワーク サイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="f4261-157">To create a network site</span></span>

1.  <span data-ttu-id="f4261-158">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f4261-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4261-159">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4261-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f4261-160">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f4261-161">[**サイト**] ページで [**新規**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="f4261-162">**新しいサイト**では、 **[名前**] フィールドで、このサイトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4261-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f4261-163">サイト名は、ビジネス サーバー配置の Skype 内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4261-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="f4261-164">[**地域**] ドロップダウン リストで、このサイトに関連付けるネットワーク領域を選択します。</span><span class="sxs-lookup"><span data-stu-id="f4261-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="f4261-165">(省略可能)このサイトへのオーディオまたはビデオ通話に帯域幅の制限を配置する場合は、**帯域幅ポリシー**のドロップダウン リストから適切な設定を使用して帯域幅ポリシーのプロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4261-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="f4261-166">使用可能な帯域幅ポリシーのプロファイルの詳細を表示したり、**ネットワークのコンフィギュレーション**グループの**ポリシー Profil** ] ページで新しい帯域幅ポリシーのプロファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="f4261-167">詳細については、[ネットワーク帯域幅ポリシー プロファイルの管理](managing-network-bandwidth-policy-profiles.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4261-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="f4261-168">(省略可能)このサイトの場所を設定する場合は、**場所のポリシー**のドロップ ダウン リストからの場所のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4261-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f4261-169">場所ポリシー サイトに割り当て拡張 9-1-1 (~ 9-1-1) とクライアントの特定の場所の設定です。</span><span class="sxs-lookup"><span data-stu-id="f4261-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="f4261-170">使用可能な場所のポリシーの詳細を表示したり、**ネットワーク構成**グループの [**場所のポリシー** ] ページから、新しい場所のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="f4261-171">(省略可能)表すことのできない名前だけで、このサイトに関する詳細情報を提供する [**説明**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4261-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="f4261-172">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f4261-173">新しいネットワーク サイトを作成するときは、**サブネットの関連付けられている**テーブルを使用しません。</span><span class="sxs-lookup"><span data-stu-id="f4261-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="f4261-174">作成またはサブネットを変更するときは、サブネットをサイトに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f4261-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="f4261-175">詳細については、[ネットワークのサブネットを管理する](managing-network-subnets.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4261-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="f4261-176">ネットワーク サイトを変更するのには</span><span class="sxs-lookup"><span data-stu-id="f4261-176">To modify a network site</span></span>

1.  <span data-ttu-id="f4261-177">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f4261-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4261-178">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4261-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f4261-179">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f4261-180">[**サイト**] ページで、変更するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="f4261-181">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f4261-182">[**サイトの編集**] ページで、説明、地域、帯域幅ポリシーのプロファイル、およびサイトに関連付けられている場所のポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="f4261-183">詳細について[ネットワーク サイトを作成するのには](#to-create-a-network-site)上記を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4261-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="f4261-184">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-184">Click **Commit**.</span></span>

<span data-ttu-id="f4261-185">このページに**関連付けられているサブネット**テーブルを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4261-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="f4261-186">どのサブネットが影響を受けるサイトの設定を変更するときに注意するように、参照に関連付けられているサブネットの一覧が用意されています。</span><span class="sxs-lookup"><span data-stu-id="f4261-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="f4261-187">既存のネットワーク サイトを削除します。</span><span class="sxs-lookup"><span data-stu-id="f4261-187">Delete an existing network site</span></span>

<span data-ttu-id="f4261-188">ネットワーク サイトは、オフィスまたは呼受付制御 (CAC) または拡張 9-1-1 の展開の各領域内で構成されている場所です。</span><span class="sxs-lookup"><span data-stu-id="f4261-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="f4261-189">サイトを構成し、地域に関連付けるには、ビジネス サーバーのコントロール パネルの Skype を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="f4261-190">たとえば、北アメリカのネットワーク領域は、シカゴ、レドモンド、バンクーバーなどのネットワーク サイトに関連付けられている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f4261-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="f4261-191">CAC ネットワーク サイトは、そのサイトには、帯域幅の制限があるない場合でも、組織内のすべてのサイトを作成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f4261-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="f4261-192">ビジネス サーバーのコントロール パネルの Skype から作成、変更、およびネットワークのサイトを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f4261-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="f4261-193">既存のネットワーク サイトを削除するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4261-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="f4261-194">詳細を作成するか、ネットワーク サイトを変更することについては、[サイトの管理の呼び出しの受付制御](managing-call-admission-control-for-sites.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4261-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="f4261-195">ネットワーク サイトを削除するには</span><span class="sxs-lookup"><span data-stu-id="f4261-195">To delete a network site</span></span>

1.  <span data-ttu-id="f4261-196">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f4261-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f4261-197">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="f4261-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f4261-198">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**サイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="f4261-199">[**サイト**] ページで、削除するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f4261-200">一度に複数のサイトを削除できます。</span><span class="sxs-lookup"><span data-stu-id="f4261-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="f4261-201">これを行うには、CTRL キーを押し、CTRL キーを押しながら複数のサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="f4261-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="f4261-202">または、すべてのサイトを選択するには、[**すべて選択\*\*\*\*編集**メニューの [します。</span><span class="sxs-lookup"><span data-stu-id="f4261-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="f4261-203">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="f4261-204">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="f4261-205">ネットワーク サブネットに関連付けられている場合は、ネットワーク サイトを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4261-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="f4261-206">サブネットに関連付けられているサイトを削除しようとすると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4261-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="f4261-207">サイトがすべてのサブネットに関連付けられているかどうか、[サイト] をクリックし、[**編集**] メニュー**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4261-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="f4261-208">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4261-208">See Also</span></span>


[<span data-ttu-id="f4261-209">新しい-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f4261-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="f4261-210">セット CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f4261-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="f4261-211">削除 CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f4261-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="f4261-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="f4261-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="f4261-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f4261-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="f4261-214">新しい-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f4261-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="f4261-215">セット CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f4261-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="f4261-216">削除 CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f4261-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="f4261-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="f4261-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
