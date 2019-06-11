---
title: 'Lync Server 2013: ユーザーごとの音声ポリシーを割り当てる'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e74bebc202a9e8d9fbc7b925c14bbe030e4c577
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848799"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="8a4f5-102">Lync Server 2013 でユーザーごとの音声ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8a4f5-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="8a4f5-103">グローバルおよびサイトレベルのボイスポリシーは、エンタープライズ Voip が有効になっているすべての Lync Server 2013 ユーザーアカウントに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="8a4f5-104">Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell を使用して、特定のユーザーに音声ポリシーを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="8a4f5-105">このトピックの手順を使用して、ユーザーごとのポリシーを Lync Server ユーザーに明示的に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="8a4f5-106">Lync Server コントロールパネルを使用してユーザー固有のボイスポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8a4f5-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8a4f5-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8a4f5-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8a4f5-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8a4f5-110">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="8a4f5-111">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="8a4f5-112">[**ボイスポリシー**] で**Lync Server ユーザーを編集**するには、適用するユーザーポリシーを選びます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="8a4f5-113"><STRONG> &lt;自動&gt; </STRONG>設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8a4f5-114">Windows PowerShell コマンドレットを使用してユーザーごとの音声ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="8a4f5-114">Assigning a Per-User Voice Policy by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="8a4f5-115">ユーザーごとの音声ポリシーを割り当てるには、Windows PowerShell と**Grant-CsVoicePolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="8a4f5-116">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8a4f5-117">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="8a4f5-118">ユーザーごとの音声ポリシーを1人のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8a4f5-118">To assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="8a4f5-119">次のコマンドでは、ユーザーごとのボイスポリシー RedmondVoicePolicy が Ken Myer に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="8a4f5-120">ユーザーごとの音声ポリシーを複数のユーザーに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="8a4f5-120">To assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="8a4f5-121">このコマンドを実行すると、ユーザーごとのボイスポリシー FinanceVoicePolicy が、Active Directory の Finance OU にアカウントを持つすべてのユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="8a4f5-122">このコマンドで使用される OU パラメーターの詳細については、「[ユーザーの取得](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))」コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a><span data-ttu-id="8a4f5-123">ユーザーごとの音声ポリシーを割り当て解除するには</span><span class="sxs-lookup"><span data-stu-id="8a4f5-123">To unassign a per-user voice policy</span></span>

  - <span data-ttu-id="8a4f5-124">次のコマンドは、以前 Ken Myer に割り当てられていたユーザーごとの音声ポリシーを割り当て解除します。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="8a4f5-125">ユーザー単位の PIN ポリシーが割り当て解除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="8a4f5-126">サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-126">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="8a4f5-127">詳細については、「 [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a4f5-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a4f5-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a4f5-128">See Also</span></span>


[<span data-ttu-id="8a4f5-129">Lync Server 2013 でエンタープライズ Voip のユーザーを無効にする</span><span class="sxs-lookup"><span data-stu-id="8a4f5-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="8a4f5-130">Lync Server 2013 管理シェル</span><span class="sxs-lookup"><span data-stu-id="8a4f5-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

