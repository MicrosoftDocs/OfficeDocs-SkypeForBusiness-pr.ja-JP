---
title: 'Lync Server 2013: モビリティポリシーを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b4246569ad7d66788cef507488b78567b6b892f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="2da49-102">Lync Server 2013 でのモビリティポリシーの作成または変更</span><span class="sxs-lookup"><span data-stu-id="2da49-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2da49-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2da49-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2da49-104">モバイル ユーザーがインスタント メッセージング (IM)、プレゼンス、連絡先などの Lync 機能をサポートしているモバイル デバイスを使用できるよう、モビリティ ポリシーを作成または変更できます。</span><span class="sxs-lookup"><span data-stu-id="2da49-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="2da49-105">Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルからモビリティポリシーを作成または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2da49-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="2da49-106">Lync Server コントロールパネルを使用してモビリティポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="2da49-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2da49-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2da49-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2da49-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2da49-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2da49-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2da49-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2da49-110">左側のナビゲーション バーで [**クライアント**] をクリックし、[**モビリティ ポリシー**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2da49-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="2da49-111">[**モビリティポリシー** ] ページで、[**新規**] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2da49-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="2da49-112">サイト モビリティ ポリシーを作成するには、[**サイト ポリシー**] をクリックし、サイトをクリックし、[**OK**] をクリックし、既定の設定を確認してから必要に応じて変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="2da49-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="2da49-113">ユーザー モビリティ ポリシーを作成するには、[**ユーザー ポリシー**] をクリックし、名前を入力し、既定の設定を確認してから必要に応じて変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="2da49-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="2da49-114">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2da49-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="2da49-115">Lync Server コントロールパネルを使用してモビリティポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="2da49-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2da49-116">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2da49-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2da49-117">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2da49-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2da49-118">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2da49-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2da49-119">左側のナビゲーション バーで [**クライアント**] をクリックし、[**モビリティ ポリシー**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2da49-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="2da49-120">[**モビリティポリシー** ] ページで、既存のモビリティポリシーのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2da49-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="2da49-121">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2da49-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="2da49-122">設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="2da49-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="2da49-123">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2da49-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2da49-124">Windows PowerShell コマンドレットを使用して外部アクセスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2da49-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2da49-125">Windows PowerShell と**get-csmobilitypolicy**コマンドレットを使用して、モビリティポリシー (サイトスコープまたはユーザーごとのスコープで) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2da49-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="2da49-126">加えて、**Set-CsMobilityPolicy** コマンドレットを使って、グローバル ポリシーを含む任意の既存のポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="2da49-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="2da49-127">これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="2da49-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2da49-128">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="2da49-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="2da49-129">サイトスコープでモビリティポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="2da49-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="2da49-130">このコマンドは、Redmond サイトのために新しいモビリティ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2da49-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="2da49-131">前のコマンドでパラメーターが指定されていない (必須の Identity パラメーターを除く) ので、ポリシーはすべてのプロパティで既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2da49-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="2da49-132">ユーザーごとのスコープでモビリティポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="2da49-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="2da49-133">ユーザーごとのスコープでモビリティ ポリシーを作成するには、ポリシーに固有の Identity を指定します。</span><span class="sxs-lookup"><span data-stu-id="2da49-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="2da49-134">モビリティポリシーの作成時に単一のプロパティ値を変更するには</span><span class="sxs-lookup"><span data-stu-id="2da49-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="2da49-p105">異なるプロパティ値を使用するポリシーを作成するには、適切なパラメーターおよびパラメーター値を含めます。たとえば、このコマンドは [勤務先から通話] を無効にするモビリティ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2da49-p105">To create policies that use different property values, include the appropriate parameter and parameter value. For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="2da49-137">モビリティポリシーの作成時に複数のプロパティ値を変更するには</span><span class="sxs-lookup"><span data-stu-id="2da49-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="2da49-p106">複数のプロパティ値は、複数のパラメーターを含めることによって変更できます。たとえば、このコマンドはモビリティと [勤務先から通話] の両方を無効にするポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2da49-p106">Multiple property values can be modified by including multiple parameters. For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="2da49-140">詳細については、[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) および [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2da49-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2da49-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="2da49-141">See Also</span></span>


[<span data-ttu-id="2da49-142">Lync Server 2013 でのモビリティポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="2da49-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

