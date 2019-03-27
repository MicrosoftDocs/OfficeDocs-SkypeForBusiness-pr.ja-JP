---
title: ネットワークの領域を管理します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 地域 * ネットワークは、ネットワーク ハブまたはバックボーンのコール受付制御、~ 9-1-1、およびメディア バイ パスの構成で使用されています。
ms.openlocfilehash: ea574fe981af679e4d841d786daf04460d1fb7c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877630"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="5ddba-103">Skype for Business Server でのネットワーク領域の管理</span><span class="sxs-lookup"><span data-stu-id="5ddba-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="5ddba-104">*ネットワークの領域*には、ネットワーク ハブまたはバックボーンのコール受付制御、~ 9-1-1、およびメディア バイ パスの構成で使用されているが。</span><span class="sxs-lookup"><span data-stu-id="5ddba-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="5ddba-105">表示、作成、またはネットワークの領域を変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="5ddba-106">たとえば、音声機能の 1 つのネットワーク地域を既に作成した場合する必要はありません新しいネットワーク領域を作成するにはその他の高度なエンタープライズ VoIP 機能では、それらの同じネットワーク領域を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="5ddba-107">ただし、機能固有の設定を適用するために、ネットワーク地域に関する既存の定義に変更を加える必要が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="5ddba-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="5ddba-108">たとえば、E9-1-1 用のネットワーク地域を作成し (この場合は関連付けられた中央サイトは必要ありません)、次に通話受付管理を展開する場合は、中央サイトを指定するためにネットワーク地域の定義を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ddba-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="5ddba-109">ネットワーク領域情報を表示または作成、変更、またはネットワークの領域を削除する、この資料の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="5ddba-110">ネットワーク領域情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-110">View network region information</span></span> 


<span data-ttu-id="5ddba-111">ネットワークの領域は、複数の地理的な分野にわたって、ネットワークのさまざまな部分を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="5ddba-112">各ネットワーク地域は、中央サイトに関連付けられているである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ddba-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="5ddba-113">セントラル サイトは、通話受付制御 (CAC) の帯域幅ポリシー サービスを実行しているデータ センター サイトです。</span><span class="sxs-lookup"><span data-stu-id="5ddba-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="5ddba-114">Skype ビジネス サーバーのコントロール パネルのネットワーク領域を表示するのには使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="5ddba-115">ネットワークの領域には、オーディオとビデオの接続のインターネットを経由する代替パスができるかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="5ddba-116">このトピックを使用すると、既存のネットワークの領域を表示します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="5ddba-117">ビジネス サーバーのコントロール パネルの Skype でのネットワーク領域に関する情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="5ddba-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5ddba-118">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ddba-119">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5ddba-120">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**領域**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="5ddba-121">[**地域**] ページで、表示し地域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="5ddba-122">のみ、一度に 1 つの領域を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="5ddba-123">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5ddba-124">Windows PowerShell コマンドレットを使用してネットワーク地域の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5ddba-125">Windows PowerShell と**Get CsNetworkRegion**コマンドレットを使用してネットワーク地域の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="5ddba-126">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="5ddba-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="5ddba-127">ネットワーク領域情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="5ddba-127">To view network region information</span></span>

  - <span data-ttu-id="5ddba-128">すべてのネットワーク領域に関する情報を表示するのには、Skype のビジネス サーバー管理シェルには、次のコマンドを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="5ddba-129">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="5ddba-130">詳細については、 [Get CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ddba-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="5ddba-131">作成またはネットワークの領域を変更します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-131">Create or modify network regions</span></span> 

<span data-ttu-id="5ddba-132">ネットワークの領域は、複数の地理的な分野にわたって、ネットワークのさまざまな部分を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="5ddba-133">各ネットワーク地域は、中央サイトに関連付けられているである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ddba-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="5ddba-134">セントラル サイトは、通話受付制御 (CAC) の帯域幅ポリシー サービスを実行しているデータ センター サイトです。</span><span class="sxs-lookup"><span data-stu-id="5ddba-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="5ddba-135">ビジネス サーバーのコントロール パネルの Skype を使用するにはネットワークの領域を構成します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="5ddba-136">ネットワークの領域には、オーディオとビデオの接続のインターネットを経由する代替パスができるかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="5ddba-137">ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワークの領域を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="5ddba-138">作成し、ネットワーク地域を変更するには、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="5ddba-139">ネットワークの領域を作成するには</span><span class="sxs-lookup"><span data-stu-id="5ddba-139">To create a network region</span></span>

1.  <span data-ttu-id="5ddba-140">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ddba-141">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5ddba-142">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**領域**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="5ddba-143">[**地域**] ページで [**新規**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="5ddba-144">**新しい地域**] ページで、 **[名前**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="5ddba-145">この値は、ビジネスのサーバーの展開に、Skype 内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ddba-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="5ddba-146">**セントラル サイト**] ドロップダウン リストから、このネットワーク地域の中央サイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="5ddba-147">**オーディオ代替パスを有効にする**] チェック ボックスは既定でチェックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="5ddba-148">かどうかの音声通話経由でルーティングされます代替パス、プライマリ パスで十分な帯域幅が存在しない場合は、このフィールドによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="5ddba-149">インターネットへのオフロードを無効にする必要がある場合にだけは、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="5ddba-150">インターネット通話の呼び出しのいずれかの場合、このチェック ボックスは帯域幅の設定に関係なく、チェックをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ddba-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="5ddba-151">**ビデオの代替パスを有効にする**] チェック ボックスは既定でチェックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="5ddba-152">このフィールドは、プライマリ パスで十分な帯域幅が存在しない場合、ビデオ通話を代替パスを経由ルーティングされるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="5ddba-153">インターネットへのオフロードを無効にする必要がある場合にだけは、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="5ddba-154">インターネット通話の呼び出しのいずれかの場合、このチェック ボックスは帯域幅の設定に関係なく、チェックをする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ddba-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="5ddba-155">(省略可能)表すことのできない、名前だけがこの地域についての詳細情報を提供する [**説明**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="5ddba-156">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-156">Click **Commit**.</span></span>

<span data-ttu-id="5ddba-157">ネットワーク地域を作成するため、**関連付けられたサイト**のテーブルは使用されません。</span><span class="sxs-lookup"><span data-stu-id="5ddba-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="5ddba-158">作成またはサイトを変更する場合は、領域を使用したサイトを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="5ddba-159">詳細については、[サイトの管理の呼び出しの受付制御](managing-call-admission-control-for-sites.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ddba-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="5ddba-160">ネットワーク地域を変更するのには</span><span class="sxs-lookup"><span data-stu-id="5ddba-160">To modify a network region</span></span>

1.  <span data-ttu-id="5ddba-161">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ddba-162">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5ddba-163">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**領域**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="5ddba-164">[**地域**] ページで、変更する領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="5ddba-165">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5ddba-166">[**地域の編集**] ページを有効にする設定を変更することができ、別のパス、オーディオとビデオを無効にして、説明を変更する (詳細については、このトピックで前述した「ネットワーク地域を作成するには」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ddba-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="5ddba-167">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-167">Click **Commit**.</span></span>

<span data-ttu-id="5ddba-168">このページに**関連付けられたサイト**を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5ddba-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="5ddba-169">サイトは影響を受ける領域の設定を変更するときに注意してください、参照に関連付けられているサイトの一覧が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5ddba-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="5ddba-170">既存のネットワーク地域を削除します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-170">Delete existing network regions</span></span> 

<span data-ttu-id="5ddba-171">ネットワークの領域は、複数の地理的な分野にわたって、ネットワークのさまざまな部分を相互接続します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="5ddba-172">各ネットワーク地域は、中央サイトに関連付けられているである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ddba-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="5ddba-173">セントラル サイトは、通話受付制御 (CAC) の帯域幅ポリシー サービスを実行しているデータ センター サイトです。</span><span class="sxs-lookup"><span data-stu-id="5ddba-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="5ddba-174">ビジネス サーバーのコントロール パネルの Skype を使用するにはネットワークの領域を構成します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="5ddba-175">ネットワークの領域には、オーディオとビデオの接続のインターネットを経由する代替パスができるかどうかを決定する設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="5ddba-176">ビジネス サーバーのコントロール パネルの Skype からを作成、変更、またはネットワークの領域を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="5ddba-177">既存のネットワーク地域を削除するのにには、このトピックを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="5ddba-178">ネットワーク地域を削除するには</span><span class="sxs-lookup"><span data-stu-id="5ddba-178">To delete a network region</span></span>

1.  <span data-ttu-id="5ddba-179">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ddba-180">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="5ddba-181">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、**領域**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="5ddba-182">[**地域**] ページで、削除し領域をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="5ddba-183">同時に複数の領域を削除できます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="5ddba-184">これを行うには、CTRL キーを押し、CTRL キーを押しながら複数の領域を選択します。</span><span class="sxs-lookup"><span data-stu-id="5ddba-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="5ddba-185">または、すべての領域を選択するに **[すべて選択**] をクリックして **[編集**] メニューです。</span><span class="sxs-lookup"><span data-stu-id="5ddba-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="5ddba-186">[**編集**] メニューの [**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="5ddba-187">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="5ddba-188">ネットワーク サイトに関連付けられている場合は、ネットワーク地域を削除できません。</span><span class="sxs-lookup"><span data-stu-id="5ddba-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="5ddba-189">サイトに関連付けられている領域を削除しようとすると、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5ddba-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="5ddba-190">領域がサイトに関連付けられているかどうか、地域を選択し、[**編集**] メニュー**の詳細を表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ddba-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="5ddba-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ddba-191">See Also</span></span>

[<span data-ttu-id="5ddba-192">ネットワーク地域ルートの管理</span><span class="sxs-lookup"><span data-stu-id="5ddba-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="5ddba-193">新しい-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="5ddba-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="5ddba-194">セット CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="5ddba-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="5ddba-195">削除 CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="5ddba-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="5ddba-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="5ddba-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
