---
title: 'Lync Server 2013: ユーザー単位の場所のポリシーの割り当て'
description: 'Lync Server 2013: ユーザー単位の場所のポリシーを割り当てます。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81631740e0a6c908c392ccacb6b37d7033d9224c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559883"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="60c36-103">Lync Server 2013 でユーザー単位の場所のポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="60c36-103">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="60c36-104">場所のポリシーは、Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。</span><span class="sxs-lookup"><span data-stu-id="60c36-104">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="60c36-p101">ユーザーは 1 つまたは複数のユーザー単位の場所のポリシーを展開できますが、この展開はオプションです。 また、グローバルレベルの場所のポリシーまたはサブネットレベルの場所のポリシーだけを展開することもできます。 ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。 特定のサブネットレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、Enhanced 9-1-1 (E9-1-1) の設定により、グローバルレベルの場所のポリシーで定義された既定の設定が自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="60c36-p101">Deploying one or more per-user location policies is optional. You can also deploy only a global-level location policy or subnet-level location policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="60c36-109">ユーザー単位の場所のポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーをサーバーに適用して、特定のユーザーが発信する緊急電話に対して適用させる設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="60c36-109">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="60c36-110">利用可能なすべての場所のポリシー設定の一覧については、「 [Lync Server 2013 の場所のポリシーの定義](lync-server-2013-defining-the-location-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c36-110">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="60c36-111">場所のポリシーの作成の詳細については、「 [Create location policies In Lync Server 2013](lync-server-2013-create-location-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c36-111">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="60c36-112">Lync Server コントロールパネルを使用してユーザー単位の場所のポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="60c36-112">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="60c36-113">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="60c36-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="60c36-114">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="60c36-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="60c36-115">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c36-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="60c36-116">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="60c36-117">ユーザーを探すには、次のどちらかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="60c36-117">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="60c36-118">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-118">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="60c36-119">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-119">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="60c36-120">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="60c36-120">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="60c36-121">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-121">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="60c36-122">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="60c36-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="60c36-123">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="60c36-124">選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="60c36-124">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="60c36-125">クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-125">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="60c36-126">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-126">Click **Find**.</span></span>

6.  <span data-ttu-id="60c36-127">検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-127">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="60c36-128">同じユーザー単位の場所のポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックし、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-128">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="60c36-129">[**ポリシーの割り当て**] の [**場所のポリシー**] で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="60c36-129">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="60c36-130">[<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使用して複数のポリシーを構成できるので、ダイアログボックスのすべてのポリシーに対して、既定で [ <STRONG> &lt; その &gt; まま保持</STRONG>] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="60c36-130">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="60c36-131">この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="60c36-131">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="60c36-132">Lync Server 2013 でグローバルレベルのポリシーを自動的に選択するか、定義されている場合はサブネットレベルのポリシーを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="60c36-132">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="60c36-133">**New-CsLocationPolicy** コマンドレットを実行して以前に定義したユーザー単位の場所のポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-133">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="60c36-134">割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら、[<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザーの権限やアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="60c36-134">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="60c36-135">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c36-135">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="60c36-136">Lync Server 管理シェルコマンドレットを使用した Per-User の場所ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="60c36-136">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="60c36-137">Grant-CsLocationPolicy コマンドレットを使用して、ユーザー単位の場所のポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="60c36-137">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="60c36-138">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="60c36-138">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="60c36-139">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c36-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="60c36-140">単一のユーザーにユーザー単位の場所のポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="60c36-140">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="60c36-141">以下のコマンドは、ユーザー Ken Myer に、ユーザー単位の場所のポリシー RedmondLocationPolicy を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="60c36-141">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="60c36-142">複数のユーザーにユーザー単位の場所のポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="60c36-142">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="60c36-143">このコマンドは、経理部に属するすべてのユーザーに、ユーザー単位の場所のポリシー AccountingDepartmentLocationPolicy を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="60c36-143">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="60c36-144">このコマンドで使用されている LdapFilter パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c36-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="60c36-145">ユーザー単位の場所のポリシーを割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="60c36-145">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="60c36-p106">以下のコマンドは、ユーザー Ken Myer に以前に割り当てたすべてのユーザー単位の場所のポリシーの割り当てを解除します。ユーザーごとのポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または、存在する場合は、彼のローカル サイト ポリシーを使用して自動的に管理されます。サイト ポリシーはグローバル ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="60c36-p106">The following command unassigns any per-user location policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="60c36-149">詳細については、 [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="60c36-149">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

