---
title: 'Lync Server 2013: デバイス更新ルールを削除する'
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
ms.openlocfilehash: 8d367c507ea2e8871231248b1f29d7d033dedbe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="c55ea-102">Lync Server 2013 でデバイス更新ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="c55ea-102">Remove a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c55ea-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c55ea-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c55ea-104">デバイス更新ルールを削除すると、デバイス更新キューから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="c55ea-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="c55ea-105">ルールの削除は、展開内のデバイスやテストデバイスからの更新プログラムのアンインストールとは異なります。</span><span class="sxs-lookup"><span data-stu-id="c55ea-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="c55ea-106">展開から承認済みの更新プログラムをアンインストールするには、デバイス更新ルールを*復元*します。</span><span class="sxs-lookup"><span data-stu-id="c55ea-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="c55ea-107">詳細については、「 [Lync Server 2013 でデバイス更新ルールを復元する](lync-server-2013-restore-a-device-update-rule.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c55ea-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="c55ea-108">テストデバイスから承認されていない更新プログラムをアンインストールするには、それを*リセット*します。</span><span class="sxs-lookup"><span data-stu-id="c55ea-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="c55ea-109">詳細については、「 [Lync Server 2013 でデバイス更新ルールをリセットする](lync-server-2013-reset-a-device-update-rule.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c55ea-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="c55ea-110">Lync Server コントロールパネルまたは Windows PowerShell を使用して、デバイス更新ルールを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c55ea-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="c55ea-111">Lync Server コントロールパネルを使用してデバイス更新ルールを削除するには</span><span class="sxs-lookup"><span data-stu-id="c55ea-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c55ea-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c55ea-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c55ea-113">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c55ea-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c55ea-114">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c55ea-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c55ea-115">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c55ea-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="c55ea-116">[**デバイス更新**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c55ea-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c55ea-117">1つのルールを削除するには、削除するルールを選びます。</span><span class="sxs-lookup"><span data-stu-id="c55ea-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="c55ea-118">すべてのルールを削除するには、[**編集**] メニューをクリックし、[**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c55ea-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="c55ea-119">[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c55ea-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c55ea-120">Windows PowerShell コマンドレットを使用してデバイス更新ルールを削除する</span><span class="sxs-lookup"><span data-stu-id="c55ea-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c55ea-121">デバイス更新ルールは、Windows PowerShell と**CsDeviceUpdateRule**コマンドレットを使用して削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="c55ea-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="c55ea-122">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="c55ea-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c55ea-123">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="c55ea-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="c55ea-124">サーバーから1つのデバイス更新ルールを削除するには</span><span class="sxs-lookup"><span data-stu-id="c55ea-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="c55ea-125">次のコマンドは、atl-cs-001.litwareinc.com 上の Web サーバーから、デバイス更新ルール d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 を削除します。</span><span class="sxs-lookup"><span data-stu-id="c55ea-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="c55ea-126">サーバーからすべてのデバイス更新ルールを削除するには</span><span class="sxs-lookup"><span data-stu-id="c55ea-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="c55ea-127">このコマンドを実行すると、atl-cs-001.litwareinc.com 上の web サーバーからすべてのデバイス更新ルールが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c55ea-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="c55ea-128">詳細については、 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c55ea-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c55ea-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c55ea-129">See Also</span></span>


[<span data-ttu-id="c55ea-130">Lync Server 2013 でデバイス更新ルールを承認する</span><span class="sxs-lookup"><span data-stu-id="c55ea-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

