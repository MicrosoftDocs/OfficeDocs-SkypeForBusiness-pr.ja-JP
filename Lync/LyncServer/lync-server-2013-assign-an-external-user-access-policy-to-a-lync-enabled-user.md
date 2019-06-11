---
title: 'Lync Server 2013: Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec487f8aacdc26f910f30a0864ecead1fdb1a745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a><span data-ttu-id="2c52e-102">Lync Server 2013 での Lync が有効なユーザーに対する外部ユーザー アクセス ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="2c52e-102">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c52e-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2c52e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2c52e-104">ユーザーが Lync Server 用に有効になっている場合は、特定のユーザーに適切なポリシーを適用して、Lync Server のコントロールパネルで SIP フェデレーション、XMPP フェデレーション、リモートユーザーアクセス、およびパブリックインスタントメッセージング (IM) 接続を構成できます。</span><span class="sxs-lookup"><span data-stu-id="2c52e-104">If a user has been enabled for Lync Server, you can configure SIP federation, XMPP federation, remote user access, and public instant messaging (IM) connectivity in the Lync Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="2c52e-105">たとえば、リモートユーザーアクセスをサポートするポリシーを作成した場合、ユーザーがリモートの場所から Lync Server に接続し、リモートの場所から内部ユーザーと共同作業する前に、ユーザーにそのポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c52e-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Lync Server from a remote location and collaborate with internal users from the remote location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c52e-106">外部ユーザーのアクセスをサポートするには、サポートする外部ユーザーアクセスの種類ごとにサポートを有効にし、その使用を制御するために適切なポリシーとその他のオプションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c52e-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="2c52e-107">詳細については、「展開ドキュメントの<A href="lync-server-2013-configuring-support-for-external-user-access.md">Lync server 2013 での外部ユーザーアクセスのサポートの構成</A>」または「操作のドキュメントで<A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">lync server 2013 へのフェデレーションと外部アクセスを管理する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c52e-107">For details, see <A href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</A> in the Deployment documentation or <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Managing federation and external access to Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="2c52e-108">このトピックの手順を使用して、以前に作成した外部ユーザーアクセスポリシーを1つ以上のユーザーアカウントに適用します。</span><span class="sxs-lookup"><span data-stu-id="2c52e-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="2c52e-109">ユーザーアカウントに外部ユーザーポリシーを適用するには</span><span class="sxs-lookup"><span data-stu-id="2c52e-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="2c52e-110">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="2c52e-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2c52e-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="2c52e-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2c52e-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c52e-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2c52e-113">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c52e-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="2c52e-114">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2c52e-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2c52e-115">[**外部アクセスポリシー**] の [ **Lync Server ユーザーの編集**] で、適用するユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2c52e-115">In **Edit Lync Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c52e-116"><STRONG> &lt;自動&gt; </STRONG>設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="2c52e-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2c52e-117">Windows PowerShell コマンドレットを使用して、ユーザーごとの外部アクセスポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2c52e-117">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2c52e-118">ユーザーごとの外部アクセスポリシーは、Windows PowerShell と Grant-CsExternalAccessPolicy コマンドレットを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2c52e-118">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="2c52e-119">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="2c52e-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2c52e-120">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c52e-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="2c52e-121">ユーザーごとの外部アクセスポリシーを1人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="2c52e-121">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="2c52e-122">このコマンドを実行すると、ユーザーごとの外部アクセスポリシー RedmondExternalAccessPolicy が Ken Myer に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2c52e-122">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="2c52e-123">ユーザーごとの外部アクセスポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="2c52e-123">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="2c52e-124">このコマンドによって、Active Directory の米国 OU にアカウントを持つすべてのユーザーに、ユーザーごとの外部アクセスポリシー USAExternalAccessPolicy が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2c52e-124">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="2c52e-125">このコマンドで使用される OU パラメーターの詳細については、「[ユーザーの取得](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)」コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c52e-125">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="2c52e-126">ユーザーごとの外部アクセスポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="2c52e-126">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="2c52e-127">このコマンドは、前に Ken Myer に割り当てられているユーザーごとの外部アクセスポリシーを割り当て解除します。</span><span class="sxs-lookup"><span data-stu-id="2c52e-127">This command unassigns any per-user external access policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="2c52e-128">ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="2c52e-128">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="2c52e-129">サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2c52e-129">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="2c52e-130">詳細については、「 [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c52e-130">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

