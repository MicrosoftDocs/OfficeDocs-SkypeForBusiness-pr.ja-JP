---
title: 'Lync Server 2013: ユーザーごとのダイヤルプランポリシーを割り当てる'
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
ms.openlocfilehash: f2bc62981a69b1260ba5f2fbaeabc112553b85f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722967"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="95494-102">Lync Server 2013 でユーザーごとのダイヤルプランポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="95494-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="95494-103">ダイヤルイン会議のエンタープライズボイスまたはユーザーのいずれかのユーザーアカウント構成を完了するには、ユーザーにダイヤルプランを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="95494-103">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="95494-104">既存のユーザーごとのダイヤルプランを明示的に割り当てていない場合、ユーザーアカウントは、グローバルダイヤルプランを自動的に使用するか、存在する場合はサイトレベルのダイヤルプランを使います。</span><span class="sxs-lookup"><span data-stu-id="95494-104">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="95494-105">エンタープライズ Voip が有効になっているすべてのユーザーに対してグローバルまたはサイトのダイヤルプランを使用する場合は、このセクションをスキップできます。</span><span class="sxs-lookup"><span data-stu-id="95494-105">If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="95494-106">Lync Server 2013 コントロールパネルを使用してダイヤルプランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="95494-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="95494-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="95494-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="95494-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="95494-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="95494-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="95494-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="95494-110">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95494-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="95494-111">[**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95494-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="95494-112">表で、ダイヤルプランを割り当てるユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95494-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="95494-113">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95494-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="95494-114">[ **Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ voip**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95494-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="95494-115">[**ダイヤルプランポリシー**] をクリックし、目的のダイヤルプランを選択します。</span><span class="sxs-lookup"><span data-stu-id="95494-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="95494-116">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95494-116">Click **Commit**.</span></span>

<span data-ttu-id="95494-117">ダイヤルプランの設定の詳細については、「 [Lync Server 2013 でダイヤルプランを構成する](lync-server-2013-configuring-dial-plans.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95494-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="95494-118">Windows PowerShell コマンドレットを使用して、ユーザーごとのダイヤルプランを割り当てる</span><span class="sxs-lookup"><span data-stu-id="95494-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="95494-119">Windows PowerShell と**Grant-CsdialPlan**コマンドレットを使用して、ユーザーごとのダイヤルプランを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="95494-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="95494-120">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="95494-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="95494-121">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="95494-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="95494-122">単一のユーザーにユーザー単位のダイヤル プランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="95494-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="95494-123">次のコマンドを実行すると、ユーザーごとのダイヤルプラン RedmondDialPlan が Ken Myer に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="95494-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="95494-124">複数のユーザーにユーザー単位のダイヤル プランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="95494-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="95494-125">このコマンドは、Redmond 市で勤務するすべてのユーザーに、ユーザーごとのダイヤルプラン RedmondDialPlan を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="95494-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="95494-126">このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95494-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="95494-127">ユーザー単位のダイヤル プランの割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="95494-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="95494-128">次のコマンドは、以前に Ken Myer に割り当てられているユーザーごとのダイヤルプランを割り当て解除します。</span><span class="sxs-lookup"><span data-stu-id="95494-128">The following command unassigns any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="95494-129">ユーザーごとのダイヤルプランが割り当てられていない場合、Ken Myer は、グローバルダイヤルプラン、彼のローカルサイトダイヤルプラン (存在する場合)、またはレジストラーまたは PSTN ゲートウェイに割り当てられているサービス範囲ダイヤルプランを使って、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="95494-129">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="95494-130">サービス範囲ダイヤルプランは、どのサイトダイヤルプランよりも優先され、サイトダイヤルプランはグローバルダイヤルプランより優先されます。</span><span class="sxs-lookup"><span data-stu-id="95494-130">A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="95494-131">詳細については、「 [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95494-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="95494-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="95494-132">See Also</span></span>


[<span data-ttu-id="95494-133">Lync Server 2013 でのダイヤル プランの構成</span><span class="sxs-lookup"><span data-stu-id="95494-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="95494-134">Lync Server 2013 で有効になっているユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="95494-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

