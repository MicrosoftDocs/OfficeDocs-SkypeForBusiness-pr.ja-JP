---
title: 'Lync Server 2013: デバイス更新ルールを削除する'
description: 'Lync Server 2013: デバイス更新ルールを削除します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f0ed7436331377200a5b8719cf32a8195179402
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555783"
---
# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="d7085-103">Lync Server 2013 のデバイス更新ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="d7085-103">Remove a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7085-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d7085-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d7085-105">デバイス更新ルールを削除すると、デバイス更新キューから完全に取得されます。</span><span class="sxs-lookup"><span data-stu-id="d7085-105">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="d7085-106">ルールを削除することと、展開内のデバイスから、またはテストデバイスから更新プログラムをアンインストールすることは異なります。</span><span class="sxs-lookup"><span data-stu-id="d7085-106">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="d7085-107">承認済みの更新プログラムを展開からアンインストールするには、デバイス更新ルールを *復元* します。</span><span class="sxs-lookup"><span data-stu-id="d7085-107">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="d7085-108">詳細については、「 [Lync Server 2013 でのデバイス更新ルールの復元](lync-server-2013-restore-a-device-update-rule.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7085-108">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="d7085-109">テストデバイスからまだ承認されていない更新プログラムをアンインストールするには、それを *リセット* します。</span><span class="sxs-lookup"><span data-stu-id="d7085-109">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="d7085-110">詳細については、「 [Lync Server 2013 のデバイス更新ルールをリセットする](lync-server-2013-reset-a-device-update-rule.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7085-110">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="d7085-111">デバイス更新ルールを削除するには、Lync Server コントロールパネルまたは Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7085-111">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="d7085-112">Lync Server コントロールパネルを使用してデバイス更新ルールを削除するには</span><span class="sxs-lookup"><span data-stu-id="d7085-112">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d7085-113">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d7085-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d7085-114">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d7085-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d7085-115">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7085-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d7085-116">左側のナビゲーションバーで [ **クライアント**] をクリックし、[ **デバイスの更新** ] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7085-116">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="d7085-117">[ **デバイスの更新** ] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d7085-117">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="d7085-118">1つのルールを削除するには、削除するルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d7085-118">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="d7085-119">すべてのルールを削除するには、[ **編集** ] メニューをクリックし、[ **すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7085-119">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="d7085-120">[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7085-120">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d7085-121">Windows PowerShell コマンドレットを使用してデバイス更新ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="d7085-121">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d7085-122">デバイス更新ルールは、Windows PowerShell と **get-csdeviceupdaterule** コマンドレットを使用して削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7085-122">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="d7085-123">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="d7085-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d7085-124">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7085-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="d7085-125">サーバーから1つのデバイス更新ルールを削除するには</span><span class="sxs-lookup"><span data-stu-id="d7085-125">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="d7085-126">次のコマンドは、atl-cs-001.litwareinc.com の Web サーバーから 2588-420a-82ac-dc2d9b1222ff9-82ac-82ac-dc2d9b1222ff9 のデバイス更新ルール d5ce3c10 を削除します。</span><span class="sxs-lookup"><span data-stu-id="d7085-126">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="d7085-127">サーバーからすべてのデバイス更新ルールを削除するには</span><span class="sxs-lookup"><span data-stu-id="d7085-127">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="d7085-128">このコマンドは、atl-cs-001.litwareinc.com 上の web サーバーからすべてのデバイス更新ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7085-128">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="d7085-129">詳細については、 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7085-129">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d7085-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7085-130">See Also</span></span>


[<span data-ttu-id="d7085-131">Lync Server 2013 でのデバイス更新ルールの承認</span><span class="sxs-lookup"><span data-stu-id="d7085-131">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

