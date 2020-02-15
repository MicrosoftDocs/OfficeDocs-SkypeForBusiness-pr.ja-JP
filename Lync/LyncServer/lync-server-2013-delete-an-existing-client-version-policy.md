---
title: 'Lync Server 2013: 既存のクライアントバージョンポリシーの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e18cf2aa76ada1d3ab42d16f68d902ad3a41eae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="52eee-102">Lync Server 2013 で既存のクライアントバージョンポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="52eee-102">Delete an existing client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52eee-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="52eee-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="52eee-104">以前に構成されたクライアントバージョンポリシーを削除する場合は、Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="52eee-104">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="52eee-105">Lync Server コントロールパネルを使用してクライアントバージョンポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="52eee-105">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="52eee-106">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="52eee-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="52eee-107">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="52eee-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="52eee-108">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52eee-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="52eee-109">左側のナビゲーションバーで [**クライアント**] をクリックし、[**クライアントバージョンポリシー** ] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="52eee-109">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="52eee-110">[**クライアントバージョンポリシー** ] ページで、削除するクライアントバージョンポリシーまたはポリシーを選択し、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="52eee-110">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="52eee-111">Windows PowerShell コマンドレットを使用してクライアントバージョンポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="52eee-111">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="52eee-112">クライアントバージョンポリシーを削除するには、 **-CsClientVersionPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="52eee-112">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="52eee-113">このコマンドレットは、Lync Server 2013 管理シェルから実行するか、Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="52eee-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="52eee-114">リモート Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Microsoft Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)を使用したリモート PowerShell の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="52eee-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="52eee-115">特定のクライアントバージョンポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="52eee-115">To remove a specific client version policy</span></span>

  - <span data-ttu-id="52eee-116">このコマンドは、Redmond サイトに適用されているクライアントバージョンポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="52eee-116">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="52eee-117">サイトスコープに適用されているすべてのクライアントバージョンポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="52eee-117">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="52eee-118">このコマンドは、サイトスコープで構成されているすべてのクライアントバージョンポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="52eee-118">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="52eee-119">特定のユーザーエージェントを含まないクライアントバージョンポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="52eee-119">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="52eee-120">このコマンドは、Windows Phone Lync (WPLync) ユーザーエージェントのルールが含まれていないクライアントバージョンポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="52eee-120">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="52eee-121">詳細については、「 [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) 」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="52eee-121">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

