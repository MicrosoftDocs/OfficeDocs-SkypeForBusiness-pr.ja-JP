---
title: 'Lync Server 2013: ユーザーへのアーカイブポリシーの適用'
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
ms.openlocfilehash: 0128d17f3089207eccd94b175057bcbcb5d467f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a><span data-ttu-id="24d52-102">Lync Server 2013 でのユーザーへのアーカイブポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="24d52-102">Applying an Archiving policy to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24d52-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="24d52-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="24d52-104">ユーザーが Lync Server 2013 に対して有効になっており、Lync Server 2013 に所属するユーザーに対してアーカイブ用のユーザーポリシーを1つ以上作成している場合は、それらのユーザーまたはユーザーグループに適切なポリシーを適用することによって、特定のユーザーに対してアーカイブサポートを実装できます。</span><span class="sxs-lookup"><span data-stu-id="24d52-104">If a user has been enabled for Lync Server 2013 and you have created one or more user policies for archiving for users homed on Lync Server 2013, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="24d52-105">たとえば、内部通信のアーカイブをサポートするポリシーを作成する場合、ユーザーの Lync Server 2013 通信のアーカイブをサポートするために、少なくとも1つのユーザーまたはユーザーグループに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="24d52-105">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user’s Lync Server 2013 communications.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24d52-106">展開に対して Microsoft Exchange 統合を有効にした場合、Exchange のインプレース保持ポリシーによって、Exchange 2013 に所属しているユーザーに対してアーカイブを有効にし、そのメールボックスをインプレース保持の対象にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="24d52-106">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="24d52-107">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies For Exchange server integration using The Lync server 2013</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24d52-107">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="24d52-108">アーカイブを有効にするには、その前にアーカイブ構成で適切なオプションをすべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24d52-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="24d52-109">詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24d52-109">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="24d52-110">このトピックの手順を使用して、作成済みのアーカイブ ユーザー ポリシーを、1 つまたは複数のユーザー アカウントまたはユーザー グループに適用します。</span><span class="sxs-lookup"><span data-stu-id="24d52-110">Use the procedure in this topic to apply a previously created Archiving user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a><span data-ttu-id="24d52-111">アーカイブ ユーザー ポリシーをユーザー アカウントに適用するには</span><span class="sxs-lookup"><span data-stu-id="24d52-111">To apply an archiving user policy to a user account</span></span>

1.  <span data-ttu-id="24d52-112">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="24d52-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="24d52-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="24d52-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24d52-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24d52-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24d52-115">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="24d52-115">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="24d52-116">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24d52-116">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="24d52-117">[ **Lync Server ユーザーの編集**] の [**アーカイブポリシー**] で、適用するアーカイブユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="24d52-117">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24d52-118">[ <STRONG> &lt;自動&gt; </STRONG> ] 設定では、既定のサーバーインストールの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="24d52-118">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="24d52-119">これらの設定はサーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="24d52-119">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="24d52-120">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24d52-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="24d52-121">Windows PowerShell コマンドレットを使用したユーザー単位のアーカイブポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="24d52-121">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="24d52-122">ユーザー単位のアーカイブポリシーは、Windows PowerShell と**grant-csarchivingpolicy**コマンドレットを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="24d52-122">Per-user archiving policies can be assigned by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="24d52-123">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="24d52-123">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="24d52-124">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="24d52-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="24d52-125">ユーザー単位のアーカイブポリシーを単一のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="24d52-125">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="24d52-126">次のコマンドは、ユーザー単位のアーカイブ ポリシーである RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="24d52-126">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="24d52-127">ユーザー単位のアーカイブポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="24d52-127">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="24d52-128">次のコマンドは、ユーザーごとのアーカイブ ポリシーである RedmondArchivingPolicy を、レジストラー プール atl-cs-001.litwareinc.com に所属するアカウントを持つすべてのユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="24d52-128">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="24d52-129">このコマンドで使用される Filter パラメーターの詳細については、「 [Get-help user](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24d52-129">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet documentation.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="24d52-130">ユーザー単位のアーカイブポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="24d52-130">To assign a per-user archiving policy</span></span>

  - <span data-ttu-id="24d52-p108">次のコマンドは、Ken Myer に割り当て済みのユーザーごとのアーカイブポリシーの割り当てを解除します。ユーザーごとのポリシーの割り当てが解除された後、Ken Myer は、グローバル ポリシー (存在する場合はローカル サイト ポリシー) を使用して自動的に管理されます。サイト ポリシーがグローバル ポリシーに優先します。</span><span class="sxs-lookup"><span data-stu-id="24d52-p108">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="24d52-134">詳細については、 [grant-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy)コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="24d52-134">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24d52-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="24d52-135">See Also</span></span>


[<span data-ttu-id="24d52-136">Lync Server 2013 での内部および外部通信のアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="24d52-136">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[<span data-ttu-id="24d52-137">Lync Server 2013 でのユーザー単位のポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="24d52-137">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

