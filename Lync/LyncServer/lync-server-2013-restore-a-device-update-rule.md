---
title: 'Lync Server 2013: デバイス更新ルールを復元する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9fc1d493de7126bd9462b0d9b5acf7f8a731035
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="b202b-102">Lync Server 2013 でのデバイス更新ルールの復元</span><span class="sxs-lookup"><span data-stu-id="b202b-102">Restore a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b202b-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b202b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b202b-104">展開内のデバイスからデバイス更新ルールをアンインストールするには、それを復元します。</span><span class="sxs-lookup"><span data-stu-id="b202b-104">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="b202b-105">デバイス更新ルールを復元すると、どちらも更新プログラムがアンインストールされ、そのルールの以前のバージョンが再インストールされます。</span><span class="sxs-lookup"><span data-stu-id="b202b-105">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="b202b-106">デバイス更新ルールを復元するには、Lync Server コントロールパネルまたは Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="b202b-106">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="b202b-107">Lync Server コントロールパネルを使用してデバイス更新ルールを復元するには</span><span class="sxs-lookup"><span data-stu-id="b202b-107">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b202b-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b202b-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b202b-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b202b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b202b-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b202b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b202b-111">左側のナビゲーションバーで [**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b202b-111">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="b202b-112">[**デバイスの更新**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b202b-112">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b202b-113">1つのルールを復元するには、そのルールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b202b-113">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="b202b-114">すべてのルールを復元するには、[**編集**] をクリックし、[**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b202b-114">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="b202b-115">[**アクション**] メニューをクリックし、[**復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b202b-115">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b202b-116">Windows PowerShell コマンドレットを使用してデバイス更新ルールを復元する</span><span class="sxs-lookup"><span data-stu-id="b202b-116">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b202b-117">デバイス更新ルールは、Windows PowerShell と**get-csdeviceupdaterule**コマンドレットを使用して復元することもできます。.</span><span class="sxs-lookup"><span data-stu-id="b202b-117">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="b202b-118">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="b202b-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b202b-119">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="b202b-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="b202b-120">単一のデバイス更新ルールをサーバーに復元するには</span><span class="sxs-lookup"><span data-stu-id="b202b-120">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="b202b-121">次のコマンドは、d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com のデバイス更新ルールを復元します。</span><span class="sxs-lookup"><span data-stu-id="b202b-121">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="b202b-122">サーバー上のすべてのデバイス更新ルールを復元するには</span><span class="sxs-lookup"><span data-stu-id="b202b-122">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="b202b-123">このコマンドは、web サーバー atl-cs-001.litwareinc.com 上のすべてのデバイス更新ルールを復元します。</span><span class="sxs-lookup"><span data-stu-id="b202b-123">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="b202b-124">詳細については、 [get-csdeviceupdaterule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b202b-124">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

