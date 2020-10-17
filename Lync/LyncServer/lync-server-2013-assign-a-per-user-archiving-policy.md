---
title: 'Lync Server 2013: ユーザー単位のアーカイブポリシーの割り当て'
description: 'Lync Server 2013: ユーザー単位のアーカイブポリシーを割り当てます。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559993"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="85e03-103">Lync Server 2013 でユーザー単位のアーカイブポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="85e03-103">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="85e03-104">アーカイブポリシーは、Lync Server 2013 コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。</span><span class="sxs-lookup"><span data-stu-id="85e03-104">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="85e03-105">1つまたは複数のユーザー単位のアーカイブポリシーの展開はオプションです。</span><span class="sxs-lookup"><span data-stu-id="85e03-105">Deploying one or more per-user archiving policies is optional.</span></span> <span data-ttu-id="85e03-106">また、グローバルレベルのアーカイブポリシーまたはサイトレベルのアーカイブポリシーのみを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="85e03-106">You can also deploy only a global-level archiving policy or site-level archiving policy.</span></span> <span data-ttu-id="85e03-107">ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="85e03-107">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="85e03-108">特定のサイトレベルまたはユーザーごとのポリシーが割り当てられていない場合、グローバルレベルの電話会議ポリシーで定義されているものに自動的にアーカイブ要件が設定されます。</span><span class="sxs-lookup"><span data-stu-id="85e03-108">Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="85e03-109">ユーザーごとのアーカイブポリシーを1つ以上作成した後、このトピックの手順を使用して、特定のユーザーの内部通信、外部通信、またはその両方がサーバーによってアーカイブされるかどうかを適切に指定するポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="85e03-109">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="85e03-110">ユーザー単位のアーカイブポリシーの作成の詳細については、「 [Lync Server 2013 でのアーカイブポリシーの作成」を参照して、特定のサイトまたはユーザーの内部通信または外部通信のアーカイブを有効または無効に](lync-server-2013-create-archiving-policy-sites-users.md)します。</span><span class="sxs-lookup"><span data-stu-id="85e03-110">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="85e03-111">ユーザー単位のアーカイブポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="85e03-111">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="85e03-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="85e03-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="85e03-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="85e03-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="85e03-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85e03-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="85e03-115">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="85e03-116">ユーザーを探すには、次のどちらかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="85e03-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="85e03-117">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="85e03-118">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="85e03-119">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="85e03-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="85e03-120">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="85e03-121">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="85e03-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="85e03-122">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="85e03-123">選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="85e03-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="85e03-124">クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="85e03-125">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-125">Click **Find**.</span></span>

6.  <span data-ttu-id="85e03-126">検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="85e03-127">同じユーザー単位のアーカイブポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択し、[ <STRONG>アクション</STRONG>] をクリックして、[ <STRONG>ポリシーの割り当て</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-127">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="85e03-128">[ **ポリシーの割り当て**] の [ **アーカイブポリシー**] で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="85e03-128">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="85e03-129">[<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使用して複数のポリシーを構成できるので、ダイアログボックスのすべてのポリシーに対して、既定で [ <STRONG> &lt; その &gt; まま保持</STRONG>] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="85e03-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="85e03-130">この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="85e03-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="85e03-131">Lync Server 2013 でグローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のいずれかを自動的に選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="85e03-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="85e03-132">[ **アーカイブポリシー** ] ページで事前に定義した、ユーザー単位のアーカイブポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-132">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="85e03-133">割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら、[<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザーの権限やアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="85e03-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="85e03-134">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85e03-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="85e03-135">Windows PowerShell コマンドレットを使用した Per-User アーカイブポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="85e03-135">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="85e03-136">Windows PowerShell と **grant-csarchivingpolicy** コマンドレットを使用して、ユーザー単位のアーカイブポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="85e03-136">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="85e03-137">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="85e03-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="85e03-138">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="85e03-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="85e03-139">ユーザー単位のアーカイブポリシーを単一のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="85e03-139">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="85e03-140">次のコマンドは、ユーザー単位のアーカイブ ポリシーである RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="85e03-140">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="85e03-141">ユーザー単位のアーカイブポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="85e03-141">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="85e03-142">このコマンドは、ユーザーごとのアーカイブポリシー RedmondArchivingPolicy を、レジストラープール atl-cs-001.litwareinc.com に所属するアカウントを持つすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="85e03-142">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="85e03-143">このコマンドで使用される Filter パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85e03-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="85e03-144">ユーザー単位のアーカイブポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="85e03-144">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="85e03-p106">次のコマンドは、Ken Myer に割り当て済みのユーザーごとのアーカイブポリシーの割り当てを解除します。ユーザーごとのポリシーの割り当てが解除された後、Ken Myer は、グローバル ポリシー (存在する場合はローカル サイト ポリシー) を使用して自動的に管理されます。サイト ポリシーがグローバル ポリシーに優先します。</span><span class="sxs-lookup"><span data-stu-id="85e03-p106">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="85e03-148">詳細については、 [grant-csarchivingpolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="85e03-148">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="85e03-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="85e03-149">See Also</span></span>


[<span data-ttu-id="85e03-150">Lync Server 2013 のアーカイブポリシーを作成して、特定のサイトまたはユーザーの内部通信または外部通信のアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="85e03-150">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="85e03-151">Lync Server 2013 でのユーザー単位のポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="85e03-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

