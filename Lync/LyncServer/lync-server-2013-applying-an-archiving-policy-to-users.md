---
title: 'Lync Server 2013: アーカイブポリシーをユーザーに適用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1cf0db76b888b9774a16f7a6353ccf1b399eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a><span data-ttu-id="97a1e-102">Lync Server 2013 のユーザーにアーカイブポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="97a1e-102">Applying an Archiving policy to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97a1e-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="97a1e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="97a1e-104">ユーザーが Lync Server 2013 用に有効になっていて、Lync Server 2013 を使用しているユーザーのアーカイブ用に1つ以上のユーザーポリシーを作成している場合、これらのユーザーまたはユーザーグループに適切なポリシーを適用することで、特定のユーザーのアーカイブサポートを実装できます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-104">If a user has been enabled for Lync Server 2013 and you have created one or more user policies for archiving for users homed on Lync Server 2013, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="97a1e-105">たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合、ユーザーの Lync Server 2013 通信のアーカイブをサポートするために、少なくとも1人のユーザーまたはユーザーグループに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-105">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user’s Lync Server 2013 communications.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97a1e-106">展開に対して Microsoft Exchange の統合を有効にしている場合、Exchange 2013 を使っているユーザーに対してアーカイブが有効になっているかどうか、およびそのメールボックスがインプレースホールドに組み込まれているかどうかを Exchange のインプレースホールドポリシーで制御します。</span><span class="sxs-lookup"><span data-stu-id="97a1e-106">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="97a1e-107">詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97a1e-107">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="97a1e-108">アーカイブを有効にする前に、アーカイブ構成ですべての適切なオプションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97a1e-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="97a1e-109">詳細については、「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 でアーカイブ構成オプションを管理</A>する」を参照してください。この操作のドキュメントでは、組織、サイト、プールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="97a1e-109">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="97a1e-110">このトピックの手順を使用して、以前に作成したアーカイブユーザーポリシーを1つ以上のユーザーアカウントまたはユーザーグループに適用します。</span><span class="sxs-lookup"><span data-stu-id="97a1e-110">Use the procedure in this topic to apply a previously created Archiving user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a><span data-ttu-id="97a1e-111">ユーザーアカウントにアーカイブユーザーポリシーを適用するには</span><span class="sxs-lookup"><span data-stu-id="97a1e-111">To apply an archiving user policy to a user account</span></span>

1.  <span data-ttu-id="97a1e-112">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="97a1e-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="97a1e-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="97a1e-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97a1e-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="97a1e-115">左側のナビゲーション バーで [**ユーザー**] をクリックして、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="97a1e-115">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="97a1e-116">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97a1e-116">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="97a1e-117">[**アーカイブポリシー**] の [ **Lync Server ユーザーの編集**] で、適用するアーカイブユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="97a1e-117">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="97a1e-118"><STRONG> &lt;自動&gt; </STRONG>設定では、既定のサーバーインストール設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-118">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="97a1e-119">これらの設定はサーバーにより自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-119">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="97a1e-120">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97a1e-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="97a1e-121">Windows PowerShell コマンドレットを使用して、ユーザーごとのアーカイブポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="97a1e-121">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="97a1e-122">ユーザーごとのアーカイブポリシーは、Windows PowerShell と**Grant-CsArchivingPolicy**コマンドレットを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-122">Per-user archiving policies can be assigned by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="97a1e-123">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-123">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="97a1e-124">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="97a1e-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="97a1e-125">ユーザーごとのアーカイブポリシーを1人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="97a1e-125">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="97a1e-126">次のコマンドは、ユーザー単位のアーカイブ ポリシー RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-126">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="97a1e-127">ユーザーごとのアーカイブポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="97a1e-127">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="97a1e-128">このコマンドを実行すると、ユーザーごとのアーカイブポリシー RedmondArchivingPolicy が、レジストラー pool atl-cs-001.litwareinc.com に所属するアカウントを持つすべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-128">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="97a1e-129">このコマンドで使用される Filter パラメーターの詳細については、「 [CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97a1e-129">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet documentation.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="97a1e-130">ユーザーごとのアーカイブポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="97a1e-130">To assign a per-user archiving policy</span></span>

  - <span data-ttu-id="97a1e-131">次のコマンドは、Ken Myer に以前割り当てられていたユーザーごとのアーカイブポリシーを割り当て解除します。</span><span class="sxs-lookup"><span data-stu-id="97a1e-131">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="97a1e-132">ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-132">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="97a1e-133">サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="97a1e-133">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="97a1e-134">詳細については、「 [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy)コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97a1e-134">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="97a1e-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="97a1e-135">See Also</span></span>


[<span data-ttu-id="97a1e-136">Lync Server 2013 での内部および外部通信のアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="97a1e-136">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[<span data-ttu-id="97a1e-137">Lync Server 2013 でのユーザーごとのポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="97a1e-137">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

