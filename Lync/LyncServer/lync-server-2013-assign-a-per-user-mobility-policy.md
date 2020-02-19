---
title: 'Lync Server 2013: ユーザー単位のモビリティポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b9a5a1bf5132fb78086fdd424714e03af2caab5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134423"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="849f4-102">Lync Server 2013 でユーザー単位のモビリティポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="849f4-102">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="849f4-103">モビリティポリシーは、Lync Server コントロールパネルまたは Lync Server 管理シェルで構成できるユーザーアカウントの個別の設定の1つです。</span><span class="sxs-lookup"><span data-stu-id="849f4-103">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="849f4-104">Lync Server コントロールパネルを使用してユーザー単位のモビリティポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="849f4-104">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="849f4-105">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="849f4-105">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="849f4-106">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="849f4-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="849f4-107">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849f4-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="849f4-108">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-108">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="849f4-109">ユーザーを探すには、次のどちらかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="849f4-109">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="849f4-110">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、またはユーザー アカウントの回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="849f4-111">保存したクエリがある場合は、[**クエリを開く**] アイコンをクリックし、[**開く**] ダイアログ ボックスを使用してそのクエリ (.usf ファイル) を取得して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-111">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="849f4-112">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="849f4-112">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="849f4-113">[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-113">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="849f4-114">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="849f4-114">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="849f4-115">[**次の値に等しい**] ドロップダウン リストで、演算子 (例: [**次の値に等しい**]、[**次の値に等しくない**]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-115">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="849f4-116">選択したユーザー プロパティによっては、検索結果のフィルターに使用する条件を入力するか、ドロップダウン リストの矢印をクリックして指定します。</span><span class="sxs-lookup"><span data-stu-id="849f4-116">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="849f4-117">クエリにその他の検索句を追加するには、[<STRONG>フィルターの追加</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-117">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="849f4-118">[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-118">Click **Find**.</span></span>

6.  <span data-ttu-id="849f4-119">検索結果のユーザーをクリックし、[**アクション**] をクリックして、[**ポリシーの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-119">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="849f4-120">同じユーザー単位のモビリティ ポリシーを複数のユーザーに適用する場合は、検索結果で複数のユーザーを選択して、[<STRONG>アクション</STRONG>] をクリックし、[<STRONG>ポリシーの割り当て</STRONG>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-120">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="849f4-121">[**ポリシーの割り当て**] の [**モビリティ ポリシー**] で、次のどちらかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="849f4-121">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="849f4-122">[<STRONG>ポリシーの割り当て</STRONG>] で構成できるポリシーが複数あるため、ダイアログボックス内のすべてのポリシーに対して、既定で [ <STRONG> &lt;&gt;そのまま保持</STRONG>] が選択されています。</span><span class="sxs-lookup"><span data-stu-id="849f4-122">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="849f4-123">この設定を変更しない場合は、以前にユーザーに割り当てたポリシーを使用して続行します。</span><span class="sxs-lookup"><span data-stu-id="849f4-123">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="849f4-124">[ \*\* \<自動\> \*\* ] を選択すると、Lync Server 2013 でグローバルレベルのポリシーまたはサイトレベルのポリシー (定義されている場合) のいずれかを自動的に選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="849f4-124">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="849f4-125">[**モビリティ ポリシー**] ページであらかじめ定義した、ユーザー単位のモビリティ ポリシーの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-125">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="849f4-126">割り当てるポリシーの決定に役立てるために、ポリシー名をクリックしたら [<STRONG>表示</STRONG>] をクリックして、ポリシーで定義されているユーザー権限やアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="849f4-126">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="849f4-127">終了したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="849f4-127">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="849f4-128">Windows PowerShell コマンドレットを使用したユーザー単位のモビリティポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="849f4-128">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="849f4-129">Windows PowerShell と**get-csmobilitypolicy**コマンドレットを使用して、ユーザー単位のモビリティポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="849f4-129">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="849f4-130">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="849f4-130">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="849f4-131">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="849f4-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="849f4-132">ユーザー単位のモビリティ ポリシーを単一のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="849f4-132">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="849f4-133">次のコマンドは、ユーザー単位のモビリティ ポリシー RedmondMobilityPolicy をユーザー「Ken Myer」に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="849f4-133">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="849f4-134">ユーザー単位のモビリティ ポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="849f4-134">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="849f4-135">次のコマンドは、ユーザー単位のモビリティ ポリシー RedmondMobilityPolicy を、ポリシー NorthAmericaMobilityPolicy が現在割り当てられているすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="849f4-135">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="849f4-136">このコマンドで使用されるフィルターパラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849f4-136">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="849f4-137">ユーザー単位のモビリティ ポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="849f4-137">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="849f4-p105">次のコマンドは、Ken Myer に割り当てられたユーザー単位のモビリティ ポリシーを割り当て解除します。ユーザー単位のポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="849f4-p105">The following command unassigns any per-user mobility policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="849f4-141">詳細については、「[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="849f4-141">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="849f4-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="849f4-142">See Also</span></span>


[<span data-ttu-id="849f4-143">Lync Server 2013 でのモビリティポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="849f4-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

