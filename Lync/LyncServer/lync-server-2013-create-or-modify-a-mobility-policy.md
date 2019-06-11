---
title: 'Lync Server 2013: モバイル機能ポリシーを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d3f03735048ab4354db9653554b6227bb7399e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="e2b2b-102">Lync Server 2013 でモバイル機能ポリシーを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="e2b2b-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2b2b-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e2b2b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e2b2b-104">モバイルユーザーがインスタントメッセージング (IM)、プレゼンス、連絡先などの Lync 機能に対してサポートされているモバイルデバイスを使用できるようにするには、モビリティーポリシーを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e2b2b-105">Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell からモバイルポリシーを作成または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="e2b2b-106">Lync Server コントロールパネルを使用してモビリティポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e2b2b-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e2b2b-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e2b2b-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e2b2b-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e2b2b-110">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**モビリティポリシー** ] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="e2b2b-111">[**モビリティポリシー** ] ページで、[**新規**] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="e2b2b-112">サイトモビリティポリシーを作成するには、[**サイトポリシー**] をクリックし、サイトをクリックし、[ **OK**] をクリックして既定の設定を確認し、必要に応じて変更を行います。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="e2b2b-113">ユーザーモビリティポリシーを作成するには、[**ユーザーポリシー**] をクリックし、名前を入力して、既定の設定を確認し、必要に応じて変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="e2b2b-114">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="e2b2b-115">Lync Server コントロールパネルを使用してモビリティポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="e2b2b-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e2b2b-116">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e2b2b-117">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e2b2b-118">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e2b2b-119">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**モビリティポリシー** ] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="e2b2b-120">[**モビリティポリシー** ] ページで、既存のモバイルポリシーのいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="e2b2b-121">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e2b2b-122">いずれかの設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="e2b2b-123">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e2b2b-124">Windows PowerShell コマンドレットを使用した外部アクセスポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="e2b2b-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e2b2b-125">Windows PowerShell と**set-csmobilitypolicy**コマンドレットを使用して、モバイルポリシー (サイトのスコープまたはユーザーごとのスコープ) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="e2b2b-126">さらに、 **Set-set-csmobilitypolicy**コマンドレットを使用して、グローバルポリシーを含む既存のポリシーを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="e2b2b-127">これらのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e2b2b-128">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="e2b2b-129">サイトのスコープでモビリティポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e2b2b-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="e2b2b-130">このコマンドを実行すると、Redmond サイトの新しいモビリティポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="e2b2b-131">パラメーター (必須の Identity パラメーター以外) は前のコマンドで指定されているため、ポリシーではすべてのプロパティに既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="e2b2b-132">ユーザーごとのスコープでモバイルポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e2b2b-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="e2b2b-133">ユーザーごとのスコープでモバイルポリシーを作成するには、ポリシーの一意の Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="e2b2b-134">モバイル機能ポリシーを作成するときに1つのプロパティの値を変更するには</span><span class="sxs-lookup"><span data-stu-id="e2b2b-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="e2b2b-135">異なるプロパティ値を使うポリシーを作成するには、適切なパラメーターとパラメーター値を含めます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-135">To create policies that use different property values, include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="e2b2b-136">たとえば、次のコマンドは、勤務先からの通話を無効にするモビリティーポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-136">For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="e2b2b-137">モバイル機能ポリシーを作成するときに複数のプロパティ値を変更するには</span><span class="sxs-lookup"><span data-stu-id="e2b2b-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="e2b2b-138">複数のパラメーターを含めることにより複数のプロパティ値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-138">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="e2b2b-139">たとえば、次のコマンドは、機動性と通話の両方を無効にするポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-139">For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="e2b2b-140">詳細については、 [set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)および[set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2b2b-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2b2b-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2b2b-141">See Also</span></span>


[<span data-ttu-id="e2b2b-142">Lync Server 2013 でのモビリティ ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="e2b2b-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

