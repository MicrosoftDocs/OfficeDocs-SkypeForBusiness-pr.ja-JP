---
title: 'Lync Server 2013: 外部ユーザーアクセスに関するグローバルポリシーのリセット'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e925043af26fd6b3226e42309ffa7033c645a2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="a999f-102">Lync Server 2013 での外部ユーザーアクセスに関するグローバルポリシーのリセット</span><span class="sxs-lookup"><span data-stu-id="a999f-102">Reset the global policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a999f-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a999f-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a999f-p101">グローバル ポリシーを完全に削除することはできません。 グローバル ポリシーに対して [**削除**] オプションを使用すると、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定に、グローバル ポリシーがリセットされるだけです。</span><span class="sxs-lookup"><span data-stu-id="a999f-p101">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="a999f-106">グローバル ポリシーを既定の設定にリセットするには</span><span class="sxs-lookup"><span data-stu-id="a999f-106">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="a999f-107">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a999f-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a999f-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a999f-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a999f-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a999f-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a999f-110">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a999f-110">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="a999f-111">[**外部アクセス ポリシー**] タブでグローバル ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a999f-111">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="a999f-p103">削除について確認するメッセージが表示されたら、[**OK**] をクリックします。 ページの先頭に、グローバル ポリシーがリセットされたことを知らせるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a999f-p103">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a999f-114">Windows PowerShell コマンドレットを使用してグローバル外部アクセスポリシーをリセットする</span><span class="sxs-lookup"><span data-stu-id="a999f-114">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a999f-115">グローバル外部アクセスポリシーは、Windows PowerShell と Get-csexternalaccesspolicy コマンドレットを使用してリセットできます。</span><span class="sxs-lookup"><span data-stu-id="a999f-115">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="a999f-116">このコマンドレットは、Lync Server 2013 管理シェルまたはリモートセッション Windows PowerShell から実行できます。</span><span class="sxs-lookup"><span data-stu-id="a999f-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="a999f-117">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="a999f-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="a999f-118">グローバル外部アクセスポリシーをリセットするには</span><span class="sxs-lookup"><span data-stu-id="a999f-118">To reset the global external access policy</span></span>

  - <span data-ttu-id="a999f-119">次のコマンドは、グローバル外部アクセス ポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="a999f-119">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="a999f-120">詳細については、 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a999f-120">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

