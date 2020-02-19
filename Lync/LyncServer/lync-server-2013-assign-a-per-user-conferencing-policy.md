---
title: 'Lync Server 2013: ユーザー単位の会議ポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47419dfde4bf41b0edfccb2bce23393f04c49a3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134453"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="b8925-102">Lync Server 2013 でユーザー単位の会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b8925-102">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="b8925-103">会議ポリシーは、Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。</span><span class="sxs-lookup"><span data-stu-id="b8925-103">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="b8925-p101">ユーザーは 1 つまたは複数のユーザー単位の会議ポリシーを展開できますが、この展開はオプションです。また、グローバルレベルの会議ポリシーまたはサイトレベルの会議ポリシーだけを展開することもできます。ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。特定のサイトレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、会議のユーザー権限やアクセス許可により、グローバルレベルの会議ポリシーで定義された既定の設定が自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b8925-p101">Deploying one or more per-user conferencing policies is optional. You can also deploy only a global-level conferencing policy or site-level conferencing policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects. Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="b8925-108">ユーザー単位の会議ポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーを割り当て、特定のユーザーが開催する会議に対してサーバーが許可するユーザー権限とアクセス許可を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8925-108">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="b8925-109">利用可能なすべての電話会議ポリシー設定の一覧については、「 [Lync Server 2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8925-109">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="b8925-110">会議ポリシーの作成の詳細については、「 [Lync Server 2013 で会議ポリシーを作成または変更する](lync-server-2013-create-or-modify-a-conferencing-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8925-110">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="b8925-111">ユーザー単位の会議ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="b8925-111">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="b8925-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b8925-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b8925-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b8925-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b8925-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8925-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b8925-115">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b8925-116">ユーザーを探すには、次のどちらかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8925-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="b8925-117">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="b8925-118">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="b8925-119">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="b8925-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="b8925-120">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="b8925-121">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8925-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="b8925-122">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="b8925-123">選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="b8925-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b8925-124">クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="b8925-125">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-125">Click **Find**.</span></span>

6.  <span data-ttu-id="b8925-126">検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="b8925-127">同じユーザー単位の会議ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックし、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-127">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="b8925-128">[**ポリシーの割り当て**] の [**会議ポリシー**] で、次のどちらかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8925-128">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="b8925-129">[<STRONG>ポリシーの割り当て</STRONG>] で構成できるポリシーが複数あるため、ダイアログボックス内のすべてのポリシーに対して、既定で [ <STRONG> &lt;&gt;そのまま保持</STRONG>] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="b8925-129">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="b8925-130">この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="b8925-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="b8925-131">[ \*\* \<自動\> \*\* ] を選択すると、Lync Server 2013 でグローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のいずれかを自動的に選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b8925-131">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="b8925-132">[**会議ポリシー**] ページであらかじめ定義した、ユーザー単位の会議ポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-132">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="b8925-133">割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="b8925-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="b8925-134">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8925-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b8925-135">Windows PowerShell コマンドレットを使用したユーザー単位の会議ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="b8925-135">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b8925-136">ユーザー単位の会議ポリシーは、Windows PowerShell と Get-csconferencingpolicy コマンドレットを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b8925-136">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="b8925-137">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="b8925-137">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b8925-138">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8925-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="b8925-139">ユーザー単位の会議ポリシーを1人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="b8925-139">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="b8925-140">次のコマンドは、ユーザー単位の会議ポリシー RedmondConferencingPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b8925-140">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="b8925-141">ユーザー単位の会議ポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="b8925-141">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="b8925-142">次のコマンドは、ユーザー単位の会議ポリシー HRConferencingPolicy を "Human Resources/人事" 部門に勤務するすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b8925-142">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="b8925-143">このコマンドで使用されている LdapFilter パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8925-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="b8925-144">ユーザー単位の会議ポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="b8925-144">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="b8925-p106">次のコマンドは、以前に Ken Myer に割り当てたユーザー単位の会議ポリシーのすべての割り当てを解除します。ユーザー単位のポリシーが割り当て解除された後、Ken Myer は自動的にグローバル ポリシーを使用して管理されるか、存在する場合には自身のローカル サイト ポリシーを使用して管理されます。サイト ポリシーはグローバル ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="b8925-p106">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="b8925-148">詳細については、 [get-csconferencingpolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8925-148">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8925-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8925-149">See Also</span></span>


[<span data-ttu-id="b8925-150">Lync Server 2013 での会議ポリシーの作成または変更</span><span class="sxs-lookup"><span data-stu-id="b8925-150">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="b8925-151">Lync Server 2013 でのユーザー単位のポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="b8925-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

