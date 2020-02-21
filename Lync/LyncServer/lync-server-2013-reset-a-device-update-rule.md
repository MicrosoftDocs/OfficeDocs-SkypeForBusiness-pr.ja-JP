---
title: 'Lync Server 2013: デバイス更新ルールをリセットする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa5bd589a6368e99401f2f84d702756d595f9be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="f8836-102">Lync Server 2013 でのデバイス更新ルールのリセット</span><span class="sxs-lookup"><span data-stu-id="f8836-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8836-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f8836-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f8836-104">テストデバイスで更新プログラムが動作しないようにするには、デバイス更新ルールをリセットします。これにより、ルールの保留状態が削除され、テストデバイスから更新プログラムがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="f8836-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="f8836-105">デバイス更新ルールを削除するには、Lync Server コントロールパネルまたは Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="f8836-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8836-106">既に承認されている (つまり、ロールアウトされた) ルールをアンインストールするには、それを復元します。</span><span class="sxs-lookup"><span data-stu-id="f8836-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="f8836-107">詳細については、「 <A href="lync-server-2013-restore-a-device-update-rule.md">Lync Server 2013 でのデバイス更新ルールの復元</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8836-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="f8836-108">Lync Server コントロールパネルを使用してデバイス更新ルールをリセットするには</span><span class="sxs-lookup"><span data-stu-id="f8836-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f8836-109">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f8836-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f8836-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f8836-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8836-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8836-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8836-112">左側のナビゲーションバーで [**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8836-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="f8836-113">[**デバイスの更新**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f8836-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f8836-114">1つのルールをリセットするには、リセットするルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8836-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="f8836-115">すべてのルールをリセットするには、[**編集**] メニューの [**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8836-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="f8836-116">1つのブランドのすべてのルールをリセットするには、[**ブランド**] 列メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="f8836-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="f8836-117">[**アクション**] をクリックし、[**保留中の更新の取り消し**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8836-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f8836-118">取り消したデバイス更新ルールをロールアウトしたくない場合は、それらを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f8836-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="f8836-119">詳細については、「 <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule In Lync Server 2013</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8836-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f8836-120">Windows PowerShell コマンドレットを使用してデバイス更新ルールをリセットする</span><span class="sxs-lookup"><span data-stu-id="f8836-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f8836-121">デバイス更新ルールは、Windows PowerShell と**get-csdeviceupdaterule**コマンドレットを使用してリセットすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f8836-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="f8836-122">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="f8836-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8836-123">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8836-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="f8836-124">サーバー上の特定のデバイス更新ルールをリセットするには</span><span class="sxs-lookup"><span data-stu-id="f8836-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="f8836-125">次のコマンドは、d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com のデバイス更新ルールをリセットします。</span><span class="sxs-lookup"><span data-stu-id="f8836-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="f8836-126">サーバー上のすべてのデバイス更新ルールをリセットするには</span><span class="sxs-lookup"><span data-stu-id="f8836-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="f8836-127">このコマンドは、Web サーバー atl-cs-001.litwareinc.com 上のすべてのデバイス更新ルールをリセットします。</span><span class="sxs-lookup"><span data-stu-id="f8836-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="f8836-128">特定のブランドを持つすべてのデバイス更新ルールをリセットするには</span><span class="sxs-lookup"><span data-stu-id="f8836-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="f8836-129">この例では、Microsoft と同等のブランドを持つ、組織全体のすべてのデバイス更新がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="f8836-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="f8836-130">詳細については、 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8836-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8836-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8836-131">See Also</span></span>


[<span data-ttu-id="f8836-132">Lync Server 2013 でのデバイス更新ルールの承認</span><span class="sxs-lookup"><span data-stu-id="f8836-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

