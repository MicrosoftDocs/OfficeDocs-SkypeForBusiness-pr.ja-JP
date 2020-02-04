---
title: 'Lync Server 2013: 既存のクライアントバージョンポリシーを削除する'
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
ms.openlocfilehash: 99936b495075034e6eae3f90e6dd95325bf6e2be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="e76a0-102">Lync Server 2013 で既存のクライアントバージョンポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="e76a0-102">Delete an existing client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e76a0-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e76a0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e76a0-104">以前に構成されたクライアントのバージョンポリシーを削除する場合は、Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell から削除できます。</span><span class="sxs-lookup"><span data-stu-id="e76a0-104">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="e76a0-105">Lync Server コントロールパネルを使用してクライアントのバージョンポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="e76a0-105">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e76a0-106">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e76a0-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e76a0-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e76a0-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e76a0-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e76a0-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e76a0-109">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンポリシー** ] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e76a0-109">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="e76a0-110">[**クライアントのバージョンポリシー** ] ページで、削除するクライアントのバージョンポリシーまたはポリシーを選択し、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e76a0-110">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e76a0-111">Windows PowerShell コマンドレットを使用してクライアントのバージョンポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="e76a0-111">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e76a0-112">クライアントのバージョンポリシーは、ユーザーの**削除**と削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e76a0-112">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="e76a0-113">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e76a0-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e76a0-114">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="e76a0-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="e76a0-115">特定のクライアントバージョンポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="e76a0-115">To remove a specific client version policy</span></span>

  - <span data-ttu-id="e76a0-116">このコマンドは、Redmond サイトに適用されているクライアントのバージョンポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e76a0-116">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="e76a0-117">サイトのスコープに適用されているすべてのクライアントバージョンポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="e76a0-117">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="e76a0-118">このコマンドは、サイト範囲で構成されているすべてのクライアントバージョンポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e76a0-118">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="e76a0-119">特定のユーザーエージェントが含まれていないクライアントのバージョンポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="e76a0-119">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="e76a0-120">このコマンドを実行すると、Windows Phone Lync (WPLync) ユーザーエージェントのルールが含まれていないクライアントのバージョンポリシーがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="e76a0-120">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="e76a0-121">詳細については、「 [CsClientVersionPolicy の削除](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e76a0-121">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

