---
title: 'Lync Server 2013: デバイス更新ルールを承認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bb464d0845f70012bdd8e70365c8a7993de6b4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="5e997-102">Lync Server 2013 でデバイス更新ルールを承認する</span><span class="sxs-lookup"><span data-stu-id="5e997-102">Approve a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e997-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5e997-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5e997-104">デバイス更新ルールをインポートした後は、テストデバイスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5e997-104">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="5e997-105">テストが成功し、組織に更新プログラムをロールアウトする場合は、Lync Server コントロールパネルまたは Windows PowerShell を使用して承認します。</span><span class="sxs-lookup"><span data-stu-id="5e997-105">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="5e997-106">Lync Server コントロールパネルを使用してデバイス更新ルールを承認するには</span><span class="sxs-lookup"><span data-stu-id="5e997-106">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5e997-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5e997-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5e997-108">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5e997-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5e997-109">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e997-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5e997-110">[**デバイス更新**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5e997-110">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5e997-111">1つのルールを承認するには、そのルールを選びます。</span><span class="sxs-lookup"><span data-stu-id="5e997-111">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="5e997-112">すべてのルールを承認するには、[**編集**] をクリックし、[**すべて選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e997-112">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="5e997-113">[**アクション**] をクリックし、[**承認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e997-113">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5e997-114">Windows PowerShell コマンドレットを使用してデバイス更新ルールを承認する</span><span class="sxs-lookup"><span data-stu-id="5e997-114">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5e997-115">デバイス更新ルールは、Windows PowerShell と**CsDeviceUpdateRule**コマンドレットを使用して承認することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e997-115">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="5e997-116">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="5e997-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e997-117">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e997-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="5e997-118">1つのデバイス更新ルールを承認するには</span><span class="sxs-lookup"><span data-stu-id="5e997-118">To approve a single device update rule</span></span>

  - <span data-ttu-id="5e997-119">次のコマンドは、Web サーバーの atl-cs-001.litwareinc.com で検出されたデバイス更新ルール d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 を承認します。</span><span class="sxs-lookup"><span data-stu-id="5e997-119">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="5e997-120">複数のデバイス更新ルールを承認するには</span><span class="sxs-lookup"><span data-stu-id="5e997-120">To approve multiple device update rules</span></span>

  - <span data-ttu-id="5e997-121">このコマンドは、Microsoft 製デバイスのすべてのデバイス更新ルールを承認します。</span><span class="sxs-lookup"><span data-stu-id="5e997-121">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="5e997-122">詳細については、「[承認-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e997-122">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5e997-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e997-123">See Also</span></span>


[<span data-ttu-id="5e997-124">Lync Server 2013 でデバイス更新ルールをインポートする</span><span class="sxs-lookup"><span data-stu-id="5e997-124">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="5e997-125">Lync Server 2013 でデバイス更新ルールを復元する</span><span class="sxs-lookup"><span data-stu-id="5e997-125">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

