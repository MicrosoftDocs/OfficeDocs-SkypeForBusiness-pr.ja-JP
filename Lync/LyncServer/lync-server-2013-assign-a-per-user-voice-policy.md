---
title: 'Lync Server 2013: ユーザー単位の音声ポリシーの割り当て'
description: 'Lync Server 2013: ユーザー単位の音声ポリシーを割り当てます。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ea0b171e10302b4c466187c54324cc2548e821
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563563"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="4241f-103">Lync Server 2013 でユーザーごとの音声ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4241f-103">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="4241f-104">エンタープライズ Voip が有効になっているすべての Lync Server 2013 ユーザーアカウントに対して、グローバルおよびサイトレベルの音声ポリシーが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4241f-104">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="4241f-105">また、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルのいずれかを使用して、特定のユーザーに音声ポリシーを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="4241f-105">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="4241f-106">このトピックの手順を使用して、ユーザーごとのポリシーを Lync Server ユーザーに明示的に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4241f-106">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="4241f-107">Lync Server コントロールパネルを使用してユーザー固有の音声ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="4241f-107">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4241f-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4241f-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4241f-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4241f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4241f-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4241f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4241f-111">左側のナビゲーション バーで [**ユーザー**] をクリックし、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="4241f-111">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="4241f-112">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4241f-112">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="4241f-113">[ **Lync Server ユーザーの編集** ] の [ **音声ポリシー**] で、適用するユーザーポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="4241f-113">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="4241f-114">[ <STRONG> &lt; 自動 &gt; </STRONG> ] 設定では、既定のサーバーまたはグローバルポリシーの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="4241f-114">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assign-per-user-voice-policies"></a><span data-ttu-id="4241f-115">ユーザー単位の音声ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="4241f-115">Assign per-user voice policies</span></span>

<span data-ttu-id="4241f-116">Windows PowerShell と **set-csvoicepolicy** コマンドレットを使用して、ユーザーごとの音声ポリシーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4241f-116">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="4241f-117">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="4241f-117">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4241f-118">リモートの Windows PowerShell を使用して Lync Server に接続する方法については、この Lync Server Windows PowerShell ブログ投稿: [クイックスタート: リモート PowerShell を使用して Microsoft Lync server 2010 を管理](https://go.microsoft.com/fwlink/p/?linkId=255876)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4241f-118">To learn about using remote Windows PowerShell to connect to Lync Server, read this Lync Server Windows PowerShell blog post: [Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span>

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="4241f-119">ユーザー単位の音声ポリシーを1人のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4241f-119">Assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="4241f-120">次のコマンドは、ユーザーごとの音声ポリシー RedmondVoicePolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4241f-120">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="4241f-121">ユーザーごとの音声ポリシーを複数のユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4241f-121">Assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="4241f-122">このコマンドは、Active Directory 内の Finance OU にアカウントを持つすべてのユーザーに、ユーザーごとの音声ポリシー FinanceVoicePolicy を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="4241f-122">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="4241f-123">このコマンドで使用されている OU パラメーターの詳細については、「 [Get-help user](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) コマンドレットのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4241f-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a><span data-ttu-id="4241f-124">ユーザー単位の音声ポリシーの割り当て解除</span><span class="sxs-lookup"><span data-stu-id="4241f-124">Unassign a per-user voice policy</span></span>

  - <span data-ttu-id="4241f-125">次のコマンドは、既に Ken Myer に割り当てられているユーザーごとの音声ポリシーを割り当てません。</span><span class="sxs-lookup"><span data-stu-id="4241f-125">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="4241f-126">ユーザーごとのポリシーの割り当てを解除された後の Ken Myer は、グローバル ポリシーまたは存在する場合はローカル サイト ポリシーを使用して、自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="4241f-126">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="4241f-127">サイト ポリシーの方がグローバル ポリシーより優先されます。</span><span class="sxs-lookup"><span data-stu-id="4241f-127">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="4241f-128">詳細については、 [set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4241f-128">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="4241f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="4241f-129">See Also</span></span>


[<span data-ttu-id="4241f-130">Lync Server 2013 でのエンタープライズ Voip のユーザーの無効化</span><span class="sxs-lookup"><span data-stu-id="4241f-130">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="4241f-131">Lync Server 2013 管理シェル</span><span class="sxs-lookup"><span data-stu-id="4241f-131">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

