---
title: 'Lync Server 2013: 既存の会議ポリシーの削除'
description: 'Lync Server 2013: 既存の会議ポリシーを削除します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b64e51acc6e6dc91b938244da28057b01957069
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572833"
---
# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="89ebc-103">Lync Server 2013 で既存の会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="89ebc-103">Delete an existing conferencing policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89ebc-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="89ebc-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="89ebc-105">ユーザーレベルまたはサイトレベルの会議ポリシーを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="89ebc-105">Follow these steps to delete a user-level or a site-level conferencing policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89ebc-106">グローバル電話会議ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="89ebc-106">You cannot delete the global conferencing policy.</span></span>



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a><span data-ttu-id="89ebc-107">サイトまたはユーザーの電話会議ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="89ebc-107">To delete a site or user conferencing policy</span></span>

1.  <span data-ttu-id="89ebc-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="89ebc-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="89ebc-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="89ebc-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="89ebc-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ebc-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="89ebc-111">左側のナビゲーション バーで [**会議**] をクリックし、[**電話会議ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89ebc-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="89ebc-112">電話会議ポリシーの一覧で、削除するサイトポリシーまたはユーザーポリシーをクリックし、[ **編集**] をクリックして、[ **削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89ebc-112">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="89ebc-113">Windows PowerShell コマンドレットを使用して電話会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="89ebc-113">Removing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="89ebc-114">Lync Server 管理シェルと **get-csconferencingpolicy** コマンドレットを使用して、会議ポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="89ebc-114">You can delete conferencing policies by using Lync Server Management Shell and the **Remove-CsConferencingPolicy** cmdlet.</span></span> <span data-ttu-id="89ebc-115">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="89ebc-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="89ebc-116">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ebc-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a><span data-ttu-id="89ebc-117">指定した電話会議ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="89ebc-117">To remove a specified conferencing policy</span></span>

  - <span data-ttu-id="89ebc-118">次のコマンドは、ID RedmondConferencingPolicy を持つ電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="89ebc-118">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="89ebc-119">ユーザーごとのスコープに適用されているすべての電話会議ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="89ebc-119">To remove all of the conferencing policies applied to the per-user scope</span></span>

  - <span data-ttu-id="89ebc-120">次のコマンドは、ユーザーごとのスコープで構成されているすべての電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="89ebc-120">The following command removes all the conferencing policies configured at the per-user scope:</span></span>
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a><span data-ttu-id="89ebc-121">外部ユーザーによる記録を許可するすべての電話会議ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="89ebc-121">To remove all of the conferencing polices that allow recording by external users</span></span>

  - <span data-ttu-id="89ebc-122">次のコマンドは、外部ユーザーに会議の記録を許可するすべての電話会議ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="89ebc-122">The following command deletes any conferencing policies that allow external users to record the conference:</span></span>
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

<span data-ttu-id="89ebc-123">詳細については、「 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ebc-123">For details, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

