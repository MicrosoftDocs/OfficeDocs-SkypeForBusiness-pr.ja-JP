---
title: 'Lync Server 2013: ユーザーごとの場所ポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a387d0f603addea31bd1e3ee6b591e06a26b2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848843"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="96fe0-102">Lync Server 2013 でユーザーごとの場所ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="96fe0-102">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="96fe0-103">場所のポリシーは、Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。</span><span class="sxs-lookup"><span data-stu-id="96fe0-103">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="96fe0-104">1つまたは複数のユーザーごとの場所のポリシーを展開することは任意です。</span><span class="sxs-lookup"><span data-stu-id="96fe0-104">Deploying one or more per-user location policies is optional.</span></span> <span data-ttu-id="96fe0-105">グローバルレベルの場所のポリシーまたはサブネットレベルの場所のポリシーのみを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="96fe0-105">You can also deploy only a global-level location policy or subnet-level location policy.</span></span> <span data-ttu-id="96fe0-106">ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="96fe0-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="96fe0-107">特定のサブネットレベルまたはユーザーごとのポリシーが割り当てられていない場合、9-1-1 (E9) の設定がグローバルレベルのポリシーで定義されているものに自動的に既定で設定されます。</span><span class="sxs-lookup"><span data-stu-id="96fe0-107">Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="96fe0-108">ユーザーごとの場所ポリシーを1つ以上作成したら、このトピックの手順を使用して、特定のユーザーによって設定された緊急通話にサーバーが適用する設定を指定するポリシーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="96fe0-108">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="96fe0-109">利用可能なすべての場所のポリシー設定の一覧については、「 [Lync Server 2013 の位置情報ポリシーを定義](lync-server-2013-defining-the-location-policy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96fe0-109">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="96fe0-110">場所のポリシーの作成について詳しくは、「 [Lync Server 2013 で場所のポリシーを作成](lync-server-2013-create-location-policies.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="96fe0-110">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="96fe0-111">Lync Server コントロールパネルを使用して、ユーザーごとの場所のポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="96fe0-111">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="96fe0-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96fe0-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="96fe0-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="96fe0-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="96fe0-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="96fe0-115">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="96fe0-116">ユーザーを探すには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="96fe0-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="96fe0-117">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="96fe0-118">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="96fe0-119">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="96fe0-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="96fe0-120">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="96fe0-121">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="96fe0-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="96fe0-122">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="96fe0-123">選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="96fe0-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="96fe0-124">クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="96fe0-125">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-125">Click **Find**.</span></span>

6.  <span data-ttu-id="96fe0-126">検索結果のユーザーをクリックして、[**アクション**] をクリックしてから、[**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="96fe0-127">複数のユーザーに同じ1つの場所のポリシーを適用する場合は、検索結果で複数のユーザーを選び、[<STRONG>操作</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-127">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="96fe0-128">[**ポリシーの割り当て**] の [**場所のポリシー**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="96fe0-128">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="96fe0-129">[<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使って構成できる複数のポリシーがあるため、ダイアログボックスのすべてのポリシーで既定で [ <STRONG> &lt;その&gt;まま</STRONG>実行する] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="96fe0-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="96fe0-130">この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="96fe0-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="96fe0-131">[Lync Server 2013 でグローバルレベルポリシー] または [定義されている場合はサブネットレベルポリシー] のいずれかを自動的に選択することを許可します。</span><span class="sxs-lookup"><span data-stu-id="96fe0-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="96fe0-132">**新しい-CsLocationPolicy**コマンドレットを実行して以前に定義した、ユーザーごとの場所ポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-132">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="96fe0-133">割り当てるポリシーを決定するには、ポリシー名をクリックした後、[<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されたユーザー権限とアクセス許可を表示します。</span><span class="sxs-lookup"><span data-stu-id="96fe0-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="96fe0-134">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96fe0-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="96fe0-135">Lync Server Management Shell コマンドレットを使用して、ユーザーごとの場所ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="96fe0-135">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="96fe0-136">Grant-CsLocationPolicy コマンドレットを使用して、ユーザーごとの場所ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="96fe0-136">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="96fe0-137">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="96fe0-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="96fe0-138">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96fe0-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="96fe0-139">ユーザーごとの場所のポリシーを1人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="96fe0-139">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="96fe0-140">次のコマンドを実行すると、ユーザーごとの場所ポリシーの RedmondLocationPolicy がユーザー Ken Myer に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="96fe0-140">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="96fe0-141">ユーザーごとの場所ポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="96fe0-141">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="96fe0-142">このコマンドを実行すると、ユーザーごとの場所のポリシー AccountingDepartmentLocationPolicy が、会計部門で作業するすべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="96fe0-142">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="96fe0-143">このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96fe0-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="96fe0-144">ユーザーごとの場所ポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="96fe0-144">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="96fe0-145">次のコマンドは、以前に Ken Myer に割り当てられているユーザーごとの場所ポリシーを割り当て解除します。</span><span class="sxs-lookup"><span data-stu-id="96fe0-145">The following command unassigns any per-user location policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="96fe0-146">ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="96fe0-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="96fe0-147">サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="96fe0-147">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="96fe0-148">詳細については、「 [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) 」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="96fe0-148">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

