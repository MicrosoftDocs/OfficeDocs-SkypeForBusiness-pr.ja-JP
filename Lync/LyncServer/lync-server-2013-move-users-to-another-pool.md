---
title: 'Lync Server 2013: ユーザーを別のプールに移動する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb716c0b551475a53cacf09be10ffdc039f5db8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="b1ec7-102">Lync Server 2013 でユーザーを別のプールに移動する</span><span class="sxs-lookup"><span data-stu-id="b1ec7-102">Move users to another pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="b1ec7-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="b1ec7-103"></span></span>

<span data-ttu-id="b1ec7-104">_**最終更新日:** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="b1ec7-104">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="b1ec7-105">Lync Server コントロールパネルを使用して、特定のサーバーまたはプールにユーザーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-105">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="b1ec7-106">Lync Server 2010 以前を実行しているソースプールの既存のすべてのユーザーを、複雑な Active Directory 環境の Lync Server 2013 移行先プールに移動すると、Active Directory の複製が遅くなることがあります。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-106">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="b1ec7-107">これを回避するには、検索フィルターを使用して、Lync Server 2010 以前を実行しているプールからユーザーを移動するか、Lync Server 管理シェルを使用してユーザーをコマンドレットで移動できます。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-107">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="b1ec7-108">また、フィルター機能は、Lync Server 2013 ユーザーと連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-108">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="b1ec7-109">選択したユーザーを別のサーバーまたはプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="b1ec7-109">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="b1ec7-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b1ec7-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b1ec7-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b1ec7-113">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b1ec7-114">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、または必要なユーザーアカウントの行の Uniform resource IDENTIFIER (URI) の最初の部分を入力し、[検索] をクリックします。 \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="b1ec7-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="b1ec7-115">表で、リスト内の特定のユーザー (複数可) を選びます。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-115">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="b1ec7-116">[**操作**] メニューの [**選択したユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-116">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="b1ec7-117">[**ユーザーの移動**] で、ユーザーを移動**先のレジストラープール**に移動するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-117">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="b1ec7-118">省略移動先のサーバーまたはプールが利用できない場合は、[**強制**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-118">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="b1ec7-119">[<STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先など、関連付けられたユーザーデータは移動されません。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-119">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="b1ec7-120">1つのサーバーまたはプールから別のサーバーまたはプールにすべてのユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="b1ec7-120">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="b1ec7-121">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b1ec7-122">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b1ec7-123">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b1ec7-124">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-124">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b1ec7-125">[**操作**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-125">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="b1ec7-126">[**ユーザーの移動**] で、**ソースレジストラープール**内で移動するユーザーアカウントが含まれているプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-126">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="b1ec7-127">[**宛先レジスタプール**] で、ユーザーの移動先のプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-127">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="b1ec7-128">省略移動先のサーバーまたはプールが利用できない場合は、[**強制**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-128">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="b1ec7-129">[<STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先など、関連付けられたユーザーデータは移動されません。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-129">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="b1ec7-130">フィルターを使用して1つのプールから別のプールにユーザーを移動するには</span><span class="sxs-lookup"><span data-stu-id="b1ec7-130">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="b1ec7-131">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b1ec7-132">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b1ec7-133">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b1ec7-134">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-134">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b1ec7-135">[**ユーザー検索**] で [**検索**] をクリックし、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-135">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="b1ec7-136">検索条件で、[**レジストラー Pool**]、[指定の**値に等しい**] の順に選択し、[**現在のプールの FQDN**] を選択し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-136">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="b1ec7-137">[**操作**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-137">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b1ec7-138">フィルターが既存のユーザーのセットに適用されている場合、[<STRONG>すべてのユーザーをプールに移動する</STRONG>] オプションは、<STRONG><EM>すべて</EM></STRONG>のユーザーに対してフィルター処理されたユーザーのサブセットのコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-138">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="b1ec7-139">[**ユーザーの移動**] で、**ソースレジストラープール**内で移動するユーザーアカウントが含まれているプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-139">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="b1ec7-140">[**宛先レジストラー pool**] で、ユーザーを移動するプールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-140">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="b1ec7-141">省略移動先のサーバーまたはプールが利用できない場合は、[**強制**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-141">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="b1ec7-142">[<STRONG>強制</STRONG>] を選択すると、ユーザーアカウントは移動されますが、スケジュールされた会議や連絡先など、関連付けられたユーザーデータは移動されません。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-142">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="b1ec7-143">Windows PowerShell コマンドレットを使用してユーザーを別のプールに移動するには</span><span class="sxs-lookup"><span data-stu-id="b1ec7-143">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="b1ec7-144">Windows PowerShell コマンドの実行方法 (ローカルまたはリモート) に応じて、次のようにして、適切な Lync Server 2013 管理者ロールのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-144">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="b1ec7-145">ローカルコンピューターでコマンドを実行している場合 (たとえば、フロントエンドサーバーに直接ログオンしている場合) は、Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているか、または必要なユーザー権限を持つコンピューターにログオンします。「[代理人による Lync Server 2013 の権限の設定](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-145">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="b1ec7-146">他のコンピューターでリモートでコマンドを実行している場合 (たとえば、コンピューターにログオンして、標準エディションのフロントエンドサーバーでコマンドをリモートで実行している場合) は、CsUserAdministrator ロールまたは CsAdministrator に割り当てられているユーザーアカウントからの操作を行います。[役割] は、社内展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-146">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b1ec7-147">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b1ec7-148">1人のユーザーを移動するには、次のように移動-CsUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-148">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="b1ec7-149">ユーザーの移動先がユーザー Pilar Ackerman であり、ユーザーは現在割り当てられているホームプールからプールに移動されます。 pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b1ec7-149">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="b1ec7-150">多数のユーザーを移動するには、ユーザーの**アクセス**コマンドレットを使用してフィルターを実行し、その結果セットのユーザーを**移動**するユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-150">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="b1ec7-151">次のような操作を行うと、ユーザーと**ムーブグループ**のユーザーの組み合わせコマンドが**表示**されます。</span><span class="sxs-lookup"><span data-stu-id="b1ec7-151">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1ec7-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1ec7-152">See Also</span></span>


[<span data-ttu-id="b1ec7-153">Lync Server 2013 でユーザーアカウントのプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="b1ec7-153">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="b1ec7-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b1ec7-154"></span></span></div>

