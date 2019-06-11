---
title: 'Lync Server 2013: ユーザーごとの PIN ポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c60943ad13bd03de6e4474ec35f2deea1964bad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848802"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="fadee-102">Lync Server 2013 でユーザーごとの PIN ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="fadee-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="fadee-103">ダイヤルイン会議の暗証番号 (PIN) ポリシーは、Lync Server 2013 コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。</span><span class="sxs-lookup"><span data-stu-id="fadee-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="fadee-p101">ユーザーは 1 つまたは複数のユーザー単位の PIN ポリシーを展開できますが、この展開はオプションです。また、グローバルレベルの PIN ポリシーまたはサイトレベルの PIN ポリシーだけを展開することもできます。ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。特定のサイトレベルのポリシーやユーザー単位のポリシーが割り当てられていない場合は、ダイヤルイン会議での PIN の使用に関するユーザーの権限およびアクセス許可により、グローバルレベルの PIN ポリシーで定義された既定の設定が自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="fadee-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="fadee-108">ユーザー単位の PIN ポリシーを 1 つ以上作成した後、このトピックの手順を使用してポリシーを割り当て、特定のユーザーが作成したか、特定のユーザーが使用する PIN にサーバーが課す制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="fadee-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="fadee-109">ユーザーごとのダイヤルイン会議 PIN ポリシーの作成について詳しくは、「 [Lync Server 2013 でのダイヤルイン会議の pin 設定を作成または変更](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fadee-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="fadee-110">ユーザー単位の PIN ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="fadee-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="fadee-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fadee-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fadee-112">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fadee-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fadee-113">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fadee-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fadee-114">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fadee-115">ユーザーを探すには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="fadee-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="fadee-116">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="fadee-117">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="fadee-118">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="fadee-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="fadee-119">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="fadee-120">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="fadee-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="fadee-121">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="fadee-122">選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="fadee-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="fadee-123">クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="fadee-124">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-124">Click **Find**.</span></span>

6.  <span data-ttu-id="fadee-125">検索結果のユーザーをクリックして、[**アクション**] をクリックしてから、[**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="fadee-126">同じユーザー単位の PIN ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックしてから [<STRONG>ポリシーの割り当て</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="fadee-127">[**ポリシーの割り当て**] の [**PIN ポリシー**] で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fadee-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="fadee-128">[<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使って構成できる複数のポリシーがあるため、ダイアログボックスのすべてのポリシーで既定で [ <STRONG> &lt;その&gt;まま</STRONG>実行する] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="fadee-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="fadee-129">この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="fadee-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="fadee-130">[Lync Server 2013 でグローバルレベルポリシー] または [定義されている場合はサイトレベルポリシー] のいずれかを自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="fadee-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="fadee-131">[**PIN ポリシー**] ページであらかじめ定義した、ユーザー単位の PIN ポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="fadee-132">割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="fadee-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="fadee-133">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fadee-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fadee-134">Windows PowerShell コマンドレットを使用してユーザーごとの PIN ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="fadee-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fadee-135">ユーザーごとの PIN ポリシーを割り当てるには、Windows PowerShell と**Grant-CsPinPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fadee-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="fadee-136">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="fadee-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fadee-137">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fadee-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="fadee-138">ユーザー単位の PIN ポリシーを単一のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="fadee-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="fadee-139">次のコマンドは、ユーザー単位の PIN ポリシー RedmondPinPolicy をユーザー「Ken Myer」に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fadee-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="fadee-140">ユーザー単位の PIN ポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="fadee-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="fadee-141">次のコマンドは、ユーザー単位の PIN ポリシー RedmondUsersPinPolicy を Redmond 市で働くすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fadee-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="fadee-142">このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fadee-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="fadee-143">ユーザー単位の PIN ポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="fadee-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="fadee-p106">次のコマンドは、Ken Myer に割り当てられたユーザー単位の PIN ポリシーを割り当て解除します。ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="fadee-p106">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="fadee-147">詳細については、「 [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fadee-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="fadee-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="fadee-148">See Also</span></span>


[<span data-ttu-id="fadee-149">Lync Server 2013 で新しい PIN ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="fadee-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="fadee-150">Lync Server 2013 でのユーザーごとのポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="fadee-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

