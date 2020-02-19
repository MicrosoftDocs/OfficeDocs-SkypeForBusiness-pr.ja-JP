---
title: 'Lync Server 2013: ユーザー単位のダイヤルプランポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd4d46e2cd41c972258a84a1e8fb34549dc8b4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134443"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="2730e-102">Lync Server 2013 でのユーザー単位のダイヤルプランポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="2730e-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="2730e-103">エンタープライズ Voip またはダイヤルイン会議のユーザーのいずれかのユーザーアカウント構成を完了するには、ユーザーにダイヤルプランを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2730e-103">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="2730e-104">既存のユーザーごとのダイヤルプランが明示的に割り当てられていない場合、ユーザーアカウントはグローバルダイヤルプランを自動的に使用するか、存在する場合はサイトレベルのダイヤルプランを使用します。</span><span class="sxs-lookup"><span data-stu-id="2730e-104">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="2730e-105">エンタープライズ Voip が有効になっているすべてのユーザーに対してグローバルまたはサイトのダイヤルプランを使用する場合は、このセクションを省略できます。</span><span class="sxs-lookup"><span data-stu-id="2730e-105">If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="2730e-106">Lync Server 2013 コントロールパネルを使用してダイヤルプランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="2730e-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="2730e-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2730e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2730e-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2730e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2730e-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2730e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2730e-110">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2730e-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="2730e-111">**[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2730e-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="2730e-112">表で、ダイヤルプランを割り当てるユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2730e-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="2730e-113">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2730e-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="2730e-114">[**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2730e-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="2730e-115">[**ダイヤルプランポリシー**] をクリックし、目的のダイヤルプランを選択します。</span><span class="sxs-lookup"><span data-stu-id="2730e-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="2730e-116">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2730e-116">Click **Commit**.</span></span>

<span data-ttu-id="2730e-117">ダイヤルプランの構成の詳細については、トピック「 [Lync Server 2013 でのダイヤルプランの構成](lync-server-2013-configuring-dial-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2730e-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2730e-118">Windows PowerShell コマンドレットを使用してユーザーごとのダイヤルプランを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2730e-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2730e-119">Windows PowerShell と**get-csdialplan**コマンドレットを使用して、ユーザーごとのダイヤルプランを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2730e-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="2730e-120">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="2730e-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2730e-121">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="2730e-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="2730e-122">ユーザー単位のダイヤルプランを1人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="2730e-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="2730e-123">次のコマンドは、ユーザーごとのダイヤルプラン RedmondDialPlan をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2730e-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="2730e-124">複数のユーザーにユーザー単位のダイヤルプランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="2730e-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="2730e-125">このコマンドを実行すると、ユーザーごとのダイヤルプラン RedmondDialPlan が Redmond の市区町村で働くすべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2730e-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="2730e-126">このコマンドで使用されている LdapFilter パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2730e-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="2730e-127">ユーザーごとのダイヤルプランの割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="2730e-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="2730e-128">次のコマンドを実行すると、既に Ken Myer に割り当てられているユーザーごとのダイヤルプランは割り当てから解放されます。</span><span class="sxs-lookup"><span data-stu-id="2730e-128">The following command unassigns any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="2730e-129">ユーザーごとのダイヤルプランの割り当てが解除されると、Ken Myer はグローバルダイヤルプラン、自分のローカルサイトのダイヤルプラン (存在する場合)、またはレジストラーまたは PSTN ゲートウェイに割り当てられているサービススコープのダイヤルプランを使用して、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="2730e-129">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="2730e-130">サービススコープのダイヤルプランは、任意のサイトダイヤルプランより優先され、サイトのダイヤルプランはグローバルダイヤルプランより優先されます。</span><span class="sxs-lookup"><span data-stu-id="2730e-130">A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="2730e-131">詳細については、 [get-csdialplan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2730e-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="2730e-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="2730e-132">See Also</span></span>


[<span data-ttu-id="2730e-133">Lync Server 2013 でのダイヤルプランの構成</span><span class="sxs-lookup"><span data-stu-id="2730e-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="2730e-134">Lync Server 2013 に対して有効になっているユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="2730e-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

