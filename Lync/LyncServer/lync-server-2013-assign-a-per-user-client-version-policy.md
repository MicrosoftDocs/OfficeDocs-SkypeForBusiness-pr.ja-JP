---
title: 'Lync Server 2013: ユーザーごとのクライアントバージョンポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b84c4550d44a09e786d09d093e64cbc1901d91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134463"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="1a4da-102">Lync Server 2013 でユーザーごとのクライアントバージョンポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1a4da-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="1a4da-103">クライアントバージョンポリシーは、Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定の1つです。</span><span class="sxs-lookup"><span data-stu-id="1a4da-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="1a4da-104">1 つ以上のユーザーごとのクライアント バージョン ポリシーを展開するかどうかはオプションです。</span><span class="sxs-lookup"><span data-stu-id="1a4da-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="1a4da-105">グローバル レベルのクライアント バージョン ポリシーのみを展開するか、サイト レベルやプール レベルのクライアント バージョン ポリシーを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a4da-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="1a4da-106">ユーザー単位のポリシーを展開する場合は、ポリシーをユーザー、グループ、または連絡先オブジェクトに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a4da-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="1a4da-107">特定のサイトレベル、プールレベル、またはユーザーごとのポリシーが割り当てられていない場合、Lync Server 2013 で登録できる既定のクライアントは、グローバルレベルのクライアントバージョンポリシーで定義されています。</span><span class="sxs-lookup"><span data-stu-id="1a4da-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="1a4da-108">ユーザーごとのクライアントバージョンポリシーを1つ以上作成した後、このトピックの手順を使用して、Lync Server への登録を許可するクライアントのバージョンを指定するポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1a4da-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="1a4da-109">ユーザーごとのクライアントバージョンポリシーの作成の詳細については、「 [Lync Server 2013 へのログオンに使用できるクライアントアプリケーションを指定](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a4da-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="1a4da-110">ユーザーごとのクライアント バージョン ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="1a4da-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="1a4da-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a4da-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1a4da-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a4da-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a4da-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a4da-114">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="1a4da-115">ユーザーを探すには、次のどちらかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a4da-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="1a4da-116">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="1a4da-117">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="1a4da-118">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="1a4da-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="1a4da-119">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="1a4da-120">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a4da-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="1a4da-121">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="1a4da-122">選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="1a4da-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="1a4da-123">クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="1a4da-124">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-124">Click **Find**.</span></span>

6.  <span data-ttu-id="1a4da-125">検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="1a4da-126">同じユーザーごとのクライアント バージョン ポリシーを複数のユーザーに適用する場合は、検索結果から複数のユーザーを選択し、[<STRONG>アクション</STRONG>] をクリックして、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="1a4da-127">[**ポリシーの割り当て**] の [**クライアント バージョン ポリシー**] の下で、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1a4da-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="1a4da-128">[<STRONG>ポリシーの割り当て</STRONG>] ダイアログボックスを使用して複数のポリシーを構成できるので、ダイアログボックスのすべてのポリシーに対して、既定で [ <STRONG> &lt;&gt;そのまま保持</STRONG>] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="1a4da-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="1a4da-129">この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="1a4da-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="1a4da-130">Lync Server で、グローバルレベルのポリシーまたは定義されている場合は、サイトレベルのポリシーまたはプールレベルのポリシーのいずれかを自動的に選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="1a4da-131">[**クライアント バージョン ポリシー**] ページで前に定義したユーザーごとのクライアント バージョン ポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="1a4da-132">割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="1a4da-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="1a4da-133">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a4da-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1a4da-134">Windows PowerShell コマンドレットを使用してユーザーごとのクライアントバージョンポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1a4da-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1a4da-135">Grant-CsClientVersionPolicy コマンドレットを使ってユーザーごとのクライアント バージョン ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1a4da-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="1a4da-136">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a4da-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1a4da-137">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a4da-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="1a4da-138">単一のユーザーにユーザーごとのクライアント バージョン ポリシーを割り当てるには
</span><span class="sxs-lookup"><span data-stu-id="1a4da-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="1a4da-139">次のコマンドでは、RedmondClientVersionPolicy というユーザーごとのクライアント バージョン ポリシーをユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1a4da-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="1a4da-140">複数のユーザーにユーザーごとのクライアント バージョン ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="1a4da-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="1a4da-141">このコマンドでは、RedmondVoicePolicy という音声ポリシーを現在割り当てられているすべてのユーザーに、RedmondClientVersionPolicy というユーザーごとのクライアント バージョン ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1a4da-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="1a4da-142">このコマンドで使用される Filter パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a4da-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="1a4da-143">ユーザーごとのクライアント バージョン ポリシーの割り当てを解除するには</span><span class="sxs-lookup"><span data-stu-id="1a4da-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="1a4da-p106">次のコマンドは、以前に Ken Myer に割り当てられたすべてのユーザーごとのクライアント バージョン ポリシーを解除します。ユーザーごとのポリシーが解除された後、Ken Myer はグローバル ポリシー、ローカル サイト ポリシー (存在する場合)、またはレジストラーに割り当てられたサービス スコープ ポリシーによって自動的に管理されることになります。サービス スコープ ポリシーはサイト ポリシーより優先され、サイト ポリシーはグローバル ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="1a4da-p106">The following command unassigns any per-user client version policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar. A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="1a4da-147">詳細については、 [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a4da-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a4da-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a4da-148">See Also</span></span>


[<span data-ttu-id="1a4da-149">Lync Server 2013 でのユーザー単位のポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="1a4da-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="1a4da-150">Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="1a4da-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

