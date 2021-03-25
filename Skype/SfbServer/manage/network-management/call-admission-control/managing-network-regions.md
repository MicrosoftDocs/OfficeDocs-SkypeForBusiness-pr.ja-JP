---
title: ネットワーク地域の管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ネットワーク領域* は、通話受付管理、E9-1-1、およびメディア バイパスの構成で使用されるネットワーク ハブまたはバックボーンです。
ms.openlocfilehash: 2020eea2cf8bf85c915ebf88de6f86cb3a0ee9ca
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122451"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="21011-103">Skype for Business Server でのネットワーク領域の管理</span><span class="sxs-lookup"><span data-stu-id="21011-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="21011-104">*ネットワーク領域は* 、通話受付管理、E9-1-1、およびメディア バイパスの構成で使用されるネットワーク ハブまたはバックボーンです。</span><span class="sxs-lookup"><span data-stu-id="21011-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="21011-105">ネットワーク領域を表示、作成、または変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="21011-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="21011-106">たとえば、1 つの Voice 機能のネットワーク領域を既に作成している場合は、新しいネットワーク領域を作成する必要があります。その他の高度エンタープライズ VoIP機能は、同じネットワーク領域を使用します。</span><span class="sxs-lookup"><span data-stu-id="21011-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="21011-107">ただし、機能固有の設定を適用するために、既存のネットワーク地域定義を変更することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="21011-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="21011-108">たとえば、E9-1-1 のネットワーク領域 (関連付けられたセントラル サイトを必要としない) を作成し、通話受付管理を展開する場合は、ネットワーク領域定義を変更して中央サイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21011-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="21011-109">この記事の手順を使用して、ネットワーク地域情報を表示したり、ネットワーク領域を作成、変更、または削除したりします。</span><span class="sxs-lookup"><span data-stu-id="21011-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="21011-110">ネットワーク地域情報の表示</span><span class="sxs-lookup"><span data-stu-id="21011-110">View network region information</span></span> 


<span data-ttu-id="21011-111">ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="21011-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="21011-112">すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="21011-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="21011-113">このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。</span><span class="sxs-lookup"><span data-stu-id="21011-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="21011-114">Skype for Business Server コントロール パネルを使用して、ネットワーク領域を表示できます。</span><span class="sxs-lookup"><span data-stu-id="21011-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="21011-115">ネットワーク地域には、音声とビデオの接続にインターネットを使用する代替パスを許可するかどうかの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="21011-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="21011-116">このトピックを使用して、既存のネットワーク地域を表示します。</span><span class="sxs-lookup"><span data-stu-id="21011-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="21011-117">Skype for Business Server コントロール パネルを使用してネットワーク地域に関する情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="21011-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="21011-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="21011-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="21011-119">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="21011-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="21011-120">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="21011-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="21011-121">[**地域**] ページで、表示する地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="21011-122">一度に 1 つの地域のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="21011-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="21011-123">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="21011-124">コマンドレットを使用したネットワーク地域Windows PowerShell表示</span><span class="sxs-lookup"><span data-stu-id="21011-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="21011-125">ネットワーク地域の情報を表示するには、Windows PowerShell **Get-CsNetworkRegion コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="21011-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="21011-126">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="21011-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="21011-127">ネットワーク地域情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="21011-127">To view network region information</span></span>

  - <span data-ttu-id="21011-128">すべてのネットワーク地域に関する情報を表示するには、Skype for Business Server 管理シェルに次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="21011-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="21011-129">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21011-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="21011-130">詳細については、[Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink) コマンドレットのヘルプ トピックを参照してください。.</span><span class="sxs-lookup"><span data-stu-id="21011-130">For more information, see the help topic for the [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="21011-131">ネットワーク地域を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="21011-131">Create or modify network regions</span></span> 

<span data-ttu-id="21011-132">ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="21011-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="21011-133">すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="21011-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="21011-134">このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。</span><span class="sxs-lookup"><span data-stu-id="21011-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="21011-135">Skype for Business Server コントロール パネルを使用して、ネットワーク領域を構成できます。</span><span class="sxs-lookup"><span data-stu-id="21011-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="21011-136">ネットワーク地域には、オーディオとビデオの接続でインターネット経由の代替パスを許可するかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="21011-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="21011-137">Skype for Business Server コントロール パネルから、ネットワーク領域を作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="21011-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="21011-138">ネットワーク地域を作成および変更するには、このトピックを参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="21011-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="21011-139">ネットワーク地域を作成するには</span><span class="sxs-lookup"><span data-stu-id="21011-139">To create a network region</span></span>

1.  <span data-ttu-id="21011-140">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="21011-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="21011-141">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="21011-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="21011-142">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="21011-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="21011-143">[**地域**] ページで [**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="21011-144">[**新しい地域**] ページで、[**名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="21011-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="21011-145">この値は、Skype for Business Server 展開内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="21011-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="21011-146">[**セントラル サイト**] ドロップダウン リストで、このネットワーク地域に対応するセントラル サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="21011-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="21011-p106">既定では、[**オーディオ代替パスを有効にする**] チェック ボックスはオンになっています。このフィールドで、プライマリ パスに適当な帯域幅がない場合に音声通話を代替パスにルーティングするかどうかを設定します。インターネットへの負荷分散を無効する必要がある場合にのみ、このチェック ボックスをオフにします。いずれかの通話をインターネット通話にする場合は、帯域幅設定に関係なく、このチェック ボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="21011-p106">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="21011-p107">既定では、[**ビデオ代替パスを有効にする**] チェック ボックスはオンになっています。このフィールドで、プライマリ パスに適当な帯域幅がない場合にビデオ通話を代替パスにルーティングするかどうかを設定します。インターネットへの負荷分散を無効する必要がある場合にのみ、このチェック ボックスをオフにします。いずれかの通話をインターネット通話にする場合は、帯域幅設定に関係なく、このチェック ボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="21011-p107">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="21011-155">(オプション) [**説明**] フィールドに値を入力して、名前だけでは表現できないこの地域に関する詳細を設定します。</span><span class="sxs-lookup"><span data-stu-id="21011-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="21011-156">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-156">Click **Commit**.</span></span>

<span data-ttu-id="21011-157">[**関連付けられているサイト**] テーブルは、ネットワーク地域の作成では使用しません。</span><span class="sxs-lookup"><span data-stu-id="21011-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="21011-158">サイトを作成または変更するときに、サイトと地域を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="21011-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="21011-159">詳細については、「サイトの [通話受付管理の管理」を参照してください](managing-call-admission-control-for-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="21011-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="21011-160">ネットワーク地域を変更するには</span><span class="sxs-lookup"><span data-stu-id="21011-160">To modify a network region</span></span>

1.  <span data-ttu-id="21011-161">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="21011-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="21011-162">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="21011-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="21011-163">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="21011-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="21011-164">[**地域**] ページで、変更する地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="21011-165">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="21011-166">[**編集 地域**] ページで、オーディオとビデオの代替パスを有効または無効に切り替えたり、説明を変更したりできます。詳細については、このトピック前半の「ネットワーク地域を作成するには」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21011-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="21011-167">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-167">Click **Commit**.</span></span>

<span data-ttu-id="21011-p109">このページでは [**関連付けられているサイト**] を変更できません。関連付けられているサイトの一覧は参考のために表示されています。これにより、地域設定を変更するとどのサイトが影響を受けるか確認することができます。</span><span class="sxs-lookup"><span data-stu-id="21011-p109">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="21011-170">既存のネットワーク領域を削除する</span><span class="sxs-lookup"><span data-stu-id="21011-170">Delete existing network regions</span></span> 

<span data-ttu-id="21011-171">ネットワーク地域は、複数の地理的な領域にまたがるネットワークのさまざまな部分を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="21011-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="21011-172">すべてのネットワーク地域は、セントラル サイトと関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="21011-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="21011-173">このセントラル サイトは、通話受付管理 (CAC) 帯域幅ポリシー サービスが実行されているデータ センター サイトです。</span><span class="sxs-lookup"><span data-stu-id="21011-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="21011-174">Skype for Business Server コントロール パネルを使用して、ネットワーク領域を構成できます。</span><span class="sxs-lookup"><span data-stu-id="21011-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="21011-175">ネットワーク地域には、オーディオとビデオの接続でインターネット経由の代替パスを許可するかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="21011-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="21011-176">Skype for Business Server コントロール パネルから、ネットワーク領域を作成、変更、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="21011-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="21011-177">既存のネットワーク地域を削除するには、このトピックを参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="21011-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="21011-178">ネットワーク地域を削除するには</span><span class="sxs-lookup"><span data-stu-id="21011-178">To delete a network region</span></span>

1.  <span data-ttu-id="21011-179">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="21011-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="21011-180">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="21011-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="21011-181">左側のナビゲーション バーで、[ネットワーク構成] **をクリックし**、[地域] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="21011-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="21011-182">[**地域**] ページで、削除する地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="21011-p111">一度に複数の地域を削除できます。これを実行するには、Ctrl キーを押しながら複数の地域を選択します。また、すべての地域を選択するには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-p111">You can delete more than one region at a time. To do this, press CTRL and select multiple regions while holding down the CTRL key. Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="21011-186">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="21011-187">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="21011-188">ネットワーク地域がネットワーク サイトに関連付けられている場合は、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="21011-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="21011-189">サイトに関連付けられている領域を削除しようとすると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21011-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="21011-190">地域がサイトに関連付けられているかどうかを確認するには、その地域を選択して [**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21011-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="21011-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="21011-191">See Also</span></span>

[<span data-ttu-id="21011-192">ネットワーク地域ルートの管理</span><span class="sxs-lookup"><span data-stu-id="21011-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="21011-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="21011-193">New-CsNetworkRegion</span></span>](/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="21011-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="21011-194">Set-CsNetworkRegion</span></span>](/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="21011-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="21011-195">Remove-CsNetworkRegion</span></span>](/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="21011-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="21011-196">Get-CsNetworkRegion</span></span>](/powershell/module/skype/Get-CsNetworkRegionLink)