---
title: 'Lync Server 2013: ユーザーを別のプールに移動する'
description: 'Lync Server 2013: ユーザーを別のプールに移動します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21012e0df7567a79bca018d194878c85b8653ae4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566393"
---
# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="d9fd6-103">Lync Server 2013 でユーザーを別のプールに移動する</span><span class="sxs-lookup"><span data-stu-id="d9fd6-103">Move users to another pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d9fd6-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d9fd6-104">

<span> </span></span></span>

<span data-ttu-id="d9fd6-105">_**トピックの最終更新日:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="d9fd6-105">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="d9fd6-106">Lync Server コントロールパネルを使用して、ユーザーを特定のサーバーまたはプールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-106">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d9fd6-107">Lync Server 2010 以前のバージョンを実行しているソースプールから、複雑な Active Directory 環境にある Lync Server 2013 移行先プールにある既存のユーザーをすべて移動すると、Active Directory のレプリケーションが遅くなることがあります。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-107">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="d9fd6-108">これを避けるために、検索フィルターを使用して、Lync Server 2010 またはそれ以前のバージョンを実行しているプールからユーザーを移動したり、Lync Server 管理シェルを使用してユーザーをコマンドレットで移動したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-108">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="d9fd6-109">また、フィルター機能は Lync Server 2013 ユーザーと連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-109">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="d9fd6-110">選択したユーザーを別のサーバーまたはプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="d9fd6-110">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="d9fd6-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9fd6-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9fd6-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d9fd6-114">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d9fd6-115">[**ユーザーの検索**] ボックスに、検索するユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全部または最初の一部を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="d9fd6-116">表の一覧で、特定のユーザーまたは複数のユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-116">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="d9fd6-117">[**アクション**] メニューの [**選択したユーザーをプールに移動する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-117">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="d9fd6-118">[**ユーザーの移動**] の [**移動先レジストラ プール**] で、ユーザーの移動先のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-118">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="d9fd6-119">(オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制移動**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-119">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="d9fd6-120">[ <STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先などの関連付けられたユーザーデータは移動されません。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-120">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="d9fd6-121">サーバー間またはプール間ですべてのユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="d9fd6-121">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="d9fd6-122">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9fd6-123">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9fd6-124">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d9fd6-125">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d9fd6-126">[**アクション**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-126">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="d9fd6-127">[**ユーザーの移動**] の [**移動元レジストラー プール**] で、移動するユーザー アカウントが入っているプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-127">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="d9fd6-128">[**移動先レジストラ プール**] で、ユーザーの移動先のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-128">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="d9fd6-129">(オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-129">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="d9fd6-130">[ <STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先などの関連付けられたユーザーデータは移動されません。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-130">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="d9fd6-131">フィルターを使用してユーザーをプール間で移動するには</span><span class="sxs-lookup"><span data-stu-id="d9fd6-131">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="d9fd6-132">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9fd6-133">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d9fd6-134">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d9fd6-135">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-135">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d9fd6-136">[ **ユーザー検索**] で、[ **検索**] をクリックし、[ **フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-136">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="d9fd6-137">検索条件で [**レジストラー プール**] を選択し、[**が次の値に等しい**] を選択して、[**現在のプールの FQDN**] を選択し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-137">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="d9fd6-138">[**アクション**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-138">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9fd6-139">既存のユーザーセットにフィルターが適用されている場合、[ <STRONG>すべてのユーザーをプールに移動</STRONG> ] オプションは、すべてのユーザーでは <STRONG><EM>なく、</EM></STRONG> フィルター処理されたユーザーのサブセットのコンテキストになります。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-139">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="d9fd6-140">[**ユーザーの移動**] の [**移動元レジストラー プール**] で、移動するユーザー アカウントが入っているプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-140">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="d9fd6-141">[**移動先レジストラー プール**] で、ユーザーの移動先のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-141">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="d9fd6-142">(オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-142">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="d9fd6-143">[ <STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先などの関連付けられたユーザーデータは移動されません。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-143">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="d9fd6-144">Windows PowerShell コマンドレットを使用してユーザーをあるプールから別のプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="d9fd6-144">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="d9fd6-145">Windows PowerShell コマンドの実行方法 (ローカルまたはリモート) に応じて、次のようにして、適切な Lync Server 2013 管理役割のメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-145">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="d9fd6-146">ローカルコンピューター上でコマンドを実行している場合 (たとえば、フロントエンドサーバーに直接ログオンしている場合) は、Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Delegate setup permissions In Lync server 2013](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-146">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="d9fd6-147">他のコンピューターでリモートでコマンドを実行している場合 (たとえば、コンピューターにログオンして、Standard Edition フロントエンドサーバーでリモートでコマンドを実行する場合)、CsUserAdministrator の役割または CsAdministrator の役割に割り当てられているユーザーアカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-147">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d9fd6-148">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d9fd6-149">単一のユーザーを移動するには、Move-CsUser コマンドレットを次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-149">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="d9fd6-150">この場合、移動するユーザーは Pilar Ackerman で、現在割り当てられているホーム プールから、プール pool01.contoso.net に移動します。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-150">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="d9fd6-151">大量のユーザーを移動するには、フィルターと **Get-CsUser** コマンドレットを使用し、ユーザーの結果セットを **Move-CsUser** に渡します。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-151">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="d9fd6-152">**Get-CsUser** と **Move-CsUser** を組み合わせたコマンドを実行すると、たとえば、次のような結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="d9fd6-152">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9fd6-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9fd6-153">See Also</span></span>


[<span data-ttu-id="d9fd6-154">Lync Server 2013 でユーザーアカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="d9fd6-154">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="d9fd6-155"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d9fd6-155"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

