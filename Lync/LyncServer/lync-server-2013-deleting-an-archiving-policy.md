---
title: 'Lync Server 2013: アーカイブポリシーを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 926cc7e45fe3e57c189b01ff92da49342506dc2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="6a8e9-102">Lync Server 2013 でアーカイブポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="6a8e9-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a8e9-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6a8e9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6a8e9-104">ユーザーポリシーまたはサイトポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="6a8e9-105">グローバルポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-105">The global policy cannot be removed.</span></span> <span data-ttu-id="6a8e9-106">グローバルポリシーを削除しようとすると、Lync Server 2013 によってポリシーが自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6a8e9-107">展開に対して Microsoft Exchange の統合を有効にしている場合、exchange 2013 を使っているユーザーに対してアーカイブが有効になっているかどうかが exchange のポリシーによって制御され、メールボックスがインプレースホールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="6a8e9-108">詳細については、展開ドキュメントで<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server との統合を使用する場合の「Lync server 2013 でアーカイブするためのポリシーを設定する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="6a8e9-109">アーカイブのユーザーまたはサイトのポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="6a8e9-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="6a8e9-110">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6a8e9-111">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6a8e9-112">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6a8e9-113">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="6a8e9-114">アーカイブ ポリシーのリストで、削除するユーザー ポリシーまたはサイト ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="6a8e9-115">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6a8e9-116">Windows PowerShell コマンドレットを使用してアーカイブポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="6a8e9-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6a8e9-117">Windows PowerShell と**CsArchivingPolicy**コマンドレットを使用して、アーカイブポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="6a8e9-118">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6a8e9-119">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="6a8e9-120">指定したアーカイブポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="6a8e9-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="6a8e9-121">例として、 **CsArchivingPolicy を削除**すると、id サイト: レドモンドのポリシーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-121">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="6a8e9-122">サイトの範囲で構成されたポリシーが削除されると、サイトポリシーによって以前管理されていたユーザーは、その代わりにグローバルアーカイブポリシーによって自動的に管理されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-122">Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead.</span></span> <span data-ttu-id="6a8e9-123">次のコマンドは、Redmond サイトに適用されているアーカイブを削除します。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-123">The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="6a8e9-124">ユーザーごとのスコープに適用されているすべてのアーカイブポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="6a8e9-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="6a8e9-125">このコマンドは、ユーザーごとのスコープに適用されたすべてのアーカイブポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="6a8e9-126">内部アーカイブを無効にするアーカイブポリシーをすべて削除するには</span><span class="sxs-lookup"><span data-stu-id="6a8e9-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="6a8e9-127">このコマンドでは、内部アーカイブが無効になっているすべてのアーカイブ ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="6a8e9-128">詳細については、 [CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a8e9-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6a8e9-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a8e9-129">See Also</span></span>


[<span data-ttu-id="6a8e9-130">Lync Server 2013 での内部および外部通信のアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="6a8e9-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

