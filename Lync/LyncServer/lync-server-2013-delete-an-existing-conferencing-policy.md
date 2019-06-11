---
title: 'Lync Server 2013: 既存の会議ポリシーを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3571c7b731579c0397da62d2c5805be19dcfa809
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="fa004-102">Lync Server 2013 で既存の会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="fa004-102">Delete an existing conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa004-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fa004-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fa004-104">ユーザーレベルまたはサイトレベルの会議ポリシーを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fa004-104">Follow these steps to delete a user-level or a site-level conferencing policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa004-105">グローバル会議ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="fa004-105">You cannot delete the global conferencing policy.</span></span>



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a><span data-ttu-id="fa004-106">サイトまたはユーザーの会議ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="fa004-106">To delete a site or user conferencing policy</span></span>

1.  <span data-ttu-id="fa004-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fa004-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fa004-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fa004-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fa004-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa004-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fa004-110">左側のナビゲーションバーで、[**会議**] をクリックし、[**会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa004-110">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="fa004-111">電話会議ポリシーのリストで、削除するサイト ポリシーまたはユーザー ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa004-111">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fa004-112">Windows PowerShell コマンドレットを使用して会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="fa004-112">Removing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fa004-113">Lync Server 管理シェルと**set-csconferencingpolicy**コマンドレットを使用して、会議のポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="fa004-113">You can delete conferencing policies by using Lync Server Management Shell and the **Remove-CsConferencingPolicy** cmdlet.</span></span> <span data-ttu-id="fa004-114">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa004-114">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fa004-115">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa004-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a><span data-ttu-id="fa004-116">指定した会議ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="fa004-116">To remove a specified conferencing policy</span></span>

  - <span data-ttu-id="fa004-117">次のコマンドは、Identity が RedmondConferencingPolicy の電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa004-117">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="fa004-118">ユーザーごとのスコープに適用されたすべての会議ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="fa004-118">To remove all of the conferencing policies applied to the per-user scope</span></span>

  - <span data-ttu-id="fa004-119">次のコマンドは、ユーザーごとのスコープで構成されているすべての会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fa004-119">The following command removes all the conferencing policies configured at the per-user scope:</span></span>
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a><span data-ttu-id="fa004-120">外部ユーザーによるレコーディングを許可するすべての会議ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="fa004-120">To remove all of the conferencing polices that allow recording by external users</span></span>

  - <span data-ttu-id="fa004-121">次のコマンドでは、外部ユーザーが会議を記録できるようにする会議ポリシーがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="fa004-121">The following command deletes any conferencing policies that allow external users to record the conference:</span></span>
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

<span data-ttu-id="fa004-122">詳細については、「 [Remove-set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa004-122">For details, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

