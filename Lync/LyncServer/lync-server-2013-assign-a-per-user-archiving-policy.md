---
title: 'Lync Server 2013: ユーザーごとのアーカイブポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82b2398002a1c2536c9a57b18f9276a9d138903
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840758"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="f2ea5-102">Lync Server 2013 でユーザーごとのアーカイブポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f2ea5-102">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="f2ea5-103">アーカイブポリシーは、Lync Server 2013 コントロールパネルで構成できるユーザーアカウントの個々の設定の1つです。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-103">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="f2ea5-104">1つまたは複数のユーザーごとのアーカイブポリシーの展開は任意です。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-104">Deploying one or more per-user archiving policies is optional.</span></span> <span data-ttu-id="f2ea5-105">グローバルレベルのアーカイブポリシーまたはサイトレベルのアーカイブポリシーのみを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-105">You can also deploy only a global-level archiving policy or site-level archiving policy.</span></span> <span data-ttu-id="f2ea5-106">ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="f2ea5-107">特定のサイトレベルまたはユーザーごとのポリシーが割り当てられていない場合、グローバルレベルの会議ポリシーで定義されているアーカイブ要件が自動的に既定になります。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-107">Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="f2ea5-108">ユーザーごとのアーカイブポリシーを1つ以上作成したら、このトピックの手順を使用して、特定のユーザーの内部通信、外部通信、またはその両方がサーバーによってアーカイブされるかどうかを適切に指定するポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-108">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="f2ea5-109">ユーザーごとのアーカイブポリシーを作成する方法の詳細については、「 [Lync Server 2013 でアーカイブポリシーを作成する」を参照して、特定のサイトまたはユーザーに対する内部または外部の通信のアーカイブを有効または無効に](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)します。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-109">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="f2ea5-110">ユーザーごとのアーカイブポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="f2ea5-110">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="f2ea5-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2ea5-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f2ea5-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f2ea5-114">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="f2ea5-115">ユーザーを探すには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="f2ea5-116">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="f2ea5-117">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="f2ea5-118">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="f2ea5-119">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="f2ea5-120">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="f2ea5-121">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="f2ea5-122">選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="f2ea5-123">クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="f2ea5-124">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-124">Click **Find**.</span></span>

6.  <span data-ttu-id="f2ea5-125">検索結果のユーザーをクリックして、[**アクション**] をクリックしてから、[**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="f2ea5-126">ユーザーごとの同じアーカイブポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択し、[<STRONG>アクション</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-126">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="f2ea5-127">[**ポリシーの割り当て**] の [**アーカイブポリシー**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-127">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="f2ea5-128">[<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使って構成できる複数のポリシーがあるため、ダイアログボックスのすべてのポリシーで既定で [ <STRONG> &lt;その&gt;まま</STRONG>実行する] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="f2ea5-129">この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="f2ea5-130">[Lync Server 2013 でグローバルレベルポリシー] または [定義されている場合はサイトレベルポリシー] のいずれかを自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="f2ea5-131">[**アーカイブポリシー** ] ページで以前に定義したユーザーごとのアーカイブポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-131">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="f2ea5-132">割り当てるポリシーを決定するには、ポリシー名をクリックした後、[<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されたユーザー権限とアクセス許可を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-132">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="f2ea5-133">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f2ea5-134">Windows PowerShell コマンドレットを使用して、ユーザーごとのアーカイブポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f2ea5-134">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f2ea5-135">ユーザーごとのアーカイブポリシーを割り当てるには、Windows PowerShell と**Grant-CsArchivingPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-135">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="f2ea5-136">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-136">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f2ea5-137">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="f2ea5-138">ユーザーごとのアーカイブポリシーを1人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="f2ea5-138">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="f2ea5-139">次のコマンドは、ユーザー単位のアーカイブ ポリシー RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-139">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="f2ea5-140">ユーザーごとのアーカイブポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="f2ea5-140">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="f2ea5-141">このコマンドを実行すると、ユーザーごとのアーカイブポリシー RedmondArchivingPolicy が、レジストラー pool atl-cs-001.litwareinc.com をホームに持つアカウントを持つすべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-141">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="f2ea5-142">このコマンドで使用される Filter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="f2ea5-143">ユーザーごとのアーカイブポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="f2ea5-143">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="f2ea5-144">次のコマンドは、Ken Myer に以前割り当てられていたユーザーごとのアーカイブポリシーを割り当て解除します。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-144">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="f2ea5-145">ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="f2ea5-146">サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="f2ea5-147">詳細については、「 [Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/gg398475\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2ea5-147">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2ea5-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2ea5-148">See Also</span></span>


[<span data-ttu-id="f2ea5-149">Lync Server 2013 でアーカイブポリシーを作成して、特定のサイトまたはユーザーの内部または外部の通信のアーカイブを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f2ea5-149">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users</span></span>](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)  


[<span data-ttu-id="f2ea5-150">Lync Server 2013 でのユーザーごとのポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="f2ea5-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

