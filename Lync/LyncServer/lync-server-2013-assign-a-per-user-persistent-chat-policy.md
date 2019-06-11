---
title: 'Lync Server 2013: ユーザーごとの常設チャットポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 081e6724f5df2389a8ef89e83b2df91b49a1b991
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848803"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="0755c-102">Lync Server 2013 でユーザーごとの常設チャットポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0755c-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="0755c-103">ユーザーごとの常設チャットポリシーは、Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使って割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="0755c-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="0755c-104">常設チャットサーバーのユーザーポリシーの作成について詳しくは、「 [Lync server 2013 で常設チャットのユーザーポリシーを作成](lync-server-2013-create-a-user-policy-for-persistent-chat.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0755c-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="0755c-105">Lync Server コントロールパネルを使用して、ユーザーごとの常設チャットポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="0755c-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0755c-106">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0755c-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0755c-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0755c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0755c-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0755c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0755c-109">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="0755c-110">ユーザーを探すには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="0755c-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="0755c-111">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か先頭部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="0755c-112">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックして、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得してから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="0755c-113">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="0755c-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="0755c-114">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="0755c-115">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="0755c-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="0755c-116">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="0755c-117">選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="0755c-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="0755c-118">クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="0755c-119">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-119">Click **Find**.</span></span>

6.  <span data-ttu-id="0755c-120">検索結果のユーザーをクリックして、[**アクション**] をクリックしてから、[**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="0755c-121">複数のユーザーに同一の常設チャットポリシーを適用する場合は、検索結果で複数のユーザーを選択し、[<STRONG>アクション</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="0755c-122">[**ポリシーの割り当て**] の [**常設チャットポリシー**] で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0755c-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="0755c-123">[<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使って構成できる複数のポリシーがあるため、ダイアログボックスのすべてのポリシーで既定で [ <STRONG> &lt;その&gt;まま</STRONG>実行する] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="0755c-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="0755c-124">この設定を変更しないで、以前にユーザーに割り当てたポリシーを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="0755c-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="0755c-125">[ \*\* \<自動\> \*\* ] を選択して、Lync Server 2013 でグローバルレベルポリシーを自動的に選ぶか、定義されている場合はサイトレベルポリシーを自動的に選択するように設定します。</span><span class="sxs-lookup"><span data-stu-id="0755c-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="0755c-126">[**常設チャットポリシー** ] ページで以前に定義した、ユーザーごとの常設チャットポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="0755c-127">割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="0755c-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="0755c-128">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0755c-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0755c-129">Windows PowerShell コマンドレットを使用して、ユーザーごとの常設チャットポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0755c-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0755c-130">また、 **Grant-CsPersistentChatPolicy**コマンドレットを使用して、ユーザーごとの常設チャットポリシーを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="0755c-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="0755c-131">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="0755c-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0755c-132">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0755c-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="0755c-133">ユーザーごとの常設チャットポリシーを1人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="0755c-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="0755c-134">次のコマンドを実行すると、ユーザーごとの常設チャットポリシー RedmondPersistentChatPolicy が Ken Myer に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0755c-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="0755c-135">ユーザーごとの常設チャットポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="0755c-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="0755c-136">このコマンドは、IT 部門で利用するすべてのユーザーに、ユーザーごとの常設チャットポリシー RedmondUsersPersistentChatPolicy を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0755c-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="0755c-137">このコマンドで使用される LdapFilter パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0755c-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="0755c-138">ユーザーごとの常設チャットポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="0755c-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="0755c-139">次のコマンドでは、以前に Ken Myer に割り当てられている各ユーザーの常設チャットポリシーは割り当て解除されます。</span><span class="sxs-lookup"><span data-stu-id="0755c-139">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="0755c-140">ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="0755c-140">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="0755c-141">サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="0755c-141">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="0755c-142">詳細については、「 [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0755c-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="0755c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="0755c-143">See Also</span></span>


[<span data-ttu-id="0755c-144">Lync Server 2013 で常設チャット用のユーザー ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="0755c-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

