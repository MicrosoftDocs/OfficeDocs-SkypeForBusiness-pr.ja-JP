---
title: ネットワーク領域の管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ネットワーク領域 * は、通話受付制御、E9-1、メディアバイパスの構成で使用されるネットワークハブまたはバックボーンです。
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279530"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="e66ef-103">Skype for Business Server でのネットワーク領域の管理</span><span class="sxs-lookup"><span data-stu-id="e66ef-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="e66ef-104">*ネットワーク領域*とは、通話受付制御、E9-1、メディアバイパスの構成で使用されるネットワークハブまたはバックボーンのことです。</span><span class="sxs-lookup"><span data-stu-id="e66ef-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="e66ef-105">ネットワーク領域を表示、作成、または変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="e66ef-106">たとえば、1つの音声機能のネットワーク領域を既に作成している場合は、新しいネットワークの領域を作成する必要はありません。その他の高度なエンタープライズ Voip 機能でも、同じネットワーク領域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="e66ef-107">ただし、機能固有の設定を適用するために、ネットワーク地域に関する既存の定義に変更を加える必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="e66ef-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="e66ef-108">たとえば、E9-1-1 用のネットワーク地域を作成し (この場合は関連付けられた中央サイトは必要ありません)、次に通話受付管理を展開する場合は、中央サイトを指定するためにネットワーク地域の定義を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66ef-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="e66ef-109">この記事の手順を使用して、ネットワークの地域情報を表示したり、ネットワーク領域を作成、変更、または削除したりします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="e66ef-110">ネットワークの地域情報を表示する</span><span class="sxs-lookup"><span data-stu-id="e66ef-110">View network region information</span></span> 


<span data-ttu-id="e66ef-111">ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e66ef-112">すべてのネットワーク領域はセントラルサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66ef-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="e66ef-113">セントラルサイトは、通話受付制御 (CAC) 帯域幅ポリシーサービスが実行されているデータセンターサイトです。</span><span class="sxs-lookup"><span data-stu-id="e66ef-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="e66ef-114">Skype for Business Server コントロールパネルを使用して、ネットワークの領域を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="e66ef-115">[ネットワーク] 領域には、インターネット経由の代替パスが音声とビデオに接続できるかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="e66ef-116">既存のネットワーク領域を表示するには、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e66ef-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="e66ef-117">Skype for Business Server コントロールパネルでネットワーク領域に関する情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="e66ef-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="e66ef-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e66ef-119">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e66ef-120">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="e66ef-121">[**領域**] ページで、表示する地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="e66ef-122">表示できる領域は一度に1つだけです。</span><span class="sxs-lookup"><span data-stu-id="e66ef-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="e66ef-123">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e66ef-124">Windows PowerShell コマンドレットを使用したネットワーク領域情報の表示</span><span class="sxs-lookup"><span data-stu-id="e66ef-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="e66ef-125">ネットワークの地域情報は、Windows PowerShell と、ユーザーの**入手用の Networkregion**コマンドレットを使って表示できます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="e66ef-126">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="e66ef-127">ネットワークの地域情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="e66ef-127">To view network region information</span></span>

  - <span data-ttu-id="e66ef-128">すべてのネットワーク領域に関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="e66ef-129">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="e66ef-130">詳細については、「 [CsNetworkRegion の取得](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e66ef-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="e66ef-131">ネットワーク領域を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="e66ef-131">Create or modify network regions</span></span> 

<span data-ttu-id="e66ef-132">ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e66ef-133">すべてのネットワーク領域はセントラルサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66ef-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="e66ef-134">セントラルサイトは、通話受付制御 (CAC) 帯域幅ポリシーサービスが実行されているデータセンターサイトです。</span><span class="sxs-lookup"><span data-stu-id="e66ef-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="e66ef-135">Skype for Business Server コントロールパネルを使用して、ネットワークの領域を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="e66ef-136">[ネットワーク] 領域には、インターネット経由の代替パスが音声とビデオに接続できるかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="e66ef-137">Skype for Business Server コントロールパネルから、ネットワークの領域を作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="e66ef-138">このトピックは、ネットワーク領域の作成と変更に使用します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="e66ef-139">ネットワークの領域を作成するには</span><span class="sxs-lookup"><span data-stu-id="e66ef-139">To create a network region</span></span>

1.  <span data-ttu-id="e66ef-140">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e66ef-141">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e66ef-142">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="e66ef-143">[**領域**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="e66ef-144">[**新しい領域**] ページで、[**名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="e66ef-145">この値は、Skype for Business Server の展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66ef-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="e66ef-146">[**セントラルサイト**] ドロップダウンリストから、このネットワーク領域のセントラルサイトを選びます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="e66ef-147">[**オーディオ代替パスを有効にする**] チェックボックスは、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="e66ef-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="e66ef-148">このフィールドは、十分な帯域幅がプライマリパスに存在しない場合に、代替パスを介して音声通話をルーティングするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="e66ef-149">オフロードをインターネットにオフにする必要がある場合にのみ、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="e66ef-150">いずれかの通話がインターネット通話の場合は、帯域幅の設定に関係なく、このチェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66ef-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="e66ef-151">[**ビデオの代替パスを有効にする**] チェックボックスは、既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="e66ef-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="e66ef-152">このフィールドは、ビデオ通話が、プライマリパスに十分な帯域幅が存在しない場合に、代替パスを使用してビデオ通話をルーティングするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="e66ef-153">オフロードをインターネットにオフにする必要がある場合にのみ、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="e66ef-154">いずれかの通話がインターネット通話の場合は、帯域幅の設定に関係なく、このチェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66ef-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="e66ef-155">省略[**説明**] フィールドに値を入力して、この領域について、名前だけでは表現できない詳細情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="e66ef-156">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-156">Click **Commit**.</span></span>

<span data-ttu-id="e66ef-157">**関連付けら**れたサイトテーブルは、ネットワーク領域の作成には使用されません。</span><span class="sxs-lookup"><span data-stu-id="e66ef-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="e66ef-158">サイトを作成または変更するときに、サイトを地域に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="e66ef-159">詳しくは、「[サイトの通話受付制御を管理する](managing-call-admission-control-for-sites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e66ef-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="e66ef-160">ネットワークの領域を変更するには</span><span class="sxs-lookup"><span data-stu-id="e66ef-160">To modify a network region</span></span>

1.  <span data-ttu-id="e66ef-161">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e66ef-162">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e66ef-163">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="e66ef-164">[**領域**] ページで、変更する領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="e66ef-165">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e66ef-166">[**領域の編集**] ページで、オーディオおよびビデオの代替パスを有効または無効にする設定を変更したり、説明を変更したりすることができます (詳細については、このトピックの「ネットワーク領域を作成する」セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e66ef-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="e66ef-167">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-167">Click **Commit**.</span></span>

<span data-ttu-id="e66ef-168">このページでは、**関連付けられたサイト**を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e66ef-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="e66ef-169">関連付けられたサイトの一覧は参照用に提供されるため、地域設定を変更したときに影響を受けるサイトがわかります。</span><span class="sxs-lookup"><span data-stu-id="e66ef-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="e66ef-170">既存のネットワーク領域を削除する</span><span class="sxs-lookup"><span data-stu-id="e66ef-170">Delete existing network regions</span></span> 

<span data-ttu-id="e66ef-171">ネットワーク領域は、ネットワークのさまざまな部分を複数の地域で相互接続します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="e66ef-172">すべてのネットワーク領域はセントラルサイトと関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e66ef-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="e66ef-173">セントラルサイトは、通話受付制御 (CAC) 帯域幅ポリシーサービスが実行されているデータセンターサイトです。</span><span class="sxs-lookup"><span data-stu-id="e66ef-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="e66ef-174">Skype for Business Server コントロールパネルを使用して、ネットワークの領域を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="e66ef-175">[ネットワーク] 領域には、インターネット経由の代替パスが音声とビデオに接続できるかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="e66ef-176">Skype for Business Server コントロールパネルから、ネットワークの領域を作成、変更、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="e66ef-177">既存のネットワーク領域を削除するには、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="e66ef-178">ネットワークの領域を削除するには</span><span class="sxs-lookup"><span data-stu-id="e66ef-178">To delete a network region</span></span>

1.  <span data-ttu-id="e66ef-179">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e66ef-180">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="e66ef-181">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**地域**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="e66ef-182">[**領域**] ページで、削除する地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="e66ef-183">一度に複数の領域を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="e66ef-184">これを行うには、ctrl キーを押しながら、CTRL キーを押しながら複数の領域を選択します。</span><span class="sxs-lookup"><span data-stu-id="e66ef-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="e66ef-185">または、すべての領域を選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="e66ef-186">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="e66ef-187">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="e66ef-188">ネットワーク領域がネットワークサイトに関連付けられている場合、その領域を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e66ef-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="e66ef-189">サイトに関連付けられている領域を削除しようとすると、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e66ef-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="e66ef-190">領域がいずれかのサイトに関連付けられているかどうかを確認するには、地域を選択し、[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e66ef-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="e66ef-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="e66ef-191">See Also</span></span>

[<span data-ttu-id="e66ef-192">ネットワーク領域ルートの管理</span><span class="sxs-lookup"><span data-stu-id="e66ef-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="e66ef-193">新しい CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e66ef-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="e66ef-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e66ef-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="e66ef-195">CsNetworkRegion の削除</span><span class="sxs-lookup"><span data-stu-id="e66ef-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="e66ef-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="e66ef-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
