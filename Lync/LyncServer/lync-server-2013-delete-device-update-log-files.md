---
title: 'Lync Server 2013: デバイス更新ログファイルを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c684978445f727dc155fade59654ff6e2866f084
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="77c81-102">Lync Server 2013 でデバイス更新ログファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="77c81-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77c81-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="77c81-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="77c81-104">デバイス更新 Web サービスは、ログファイルの広範なコレクションを保持します。</span><span class="sxs-lookup"><span data-stu-id="77c81-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="77c81-105">このコレクションには、サービス自体によって実行された監査ログとクライアントデバイスからアップロードされたログファイルの両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="77c81-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="77c81-106">サーバーがデバイス更新 Web サービスログでいっぱいにならないようにするには、一定の期間、使用されていたログファイルを消去する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77c81-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="77c81-107">この日数は、更新アクティビティと組織内のクライアントデバイスの数に基づいて、および Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="77c81-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="77c81-108">Lync Server コントロールパネルを使用してデバイス更新ログを消去するには</span><span class="sxs-lookup"><span data-stu-id="77c81-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="77c81-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="77c81-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="77c81-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="77c81-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="77c81-111">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスログの構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77c81-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="77c81-112">[**デバイスログの構成**] ページで、変更する構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="77c81-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="77c81-113">[**ログ設定の編集**] ダイアログボックスで、[**ログファイルを保持する日数 (1-365)**] に日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="77c81-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="77c81-114">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77c81-114">Click **Commit**.</span></span> <span data-ttu-id="77c81-115">指定した日数を超えてサーバー上に存在するすべてのファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="77c81-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="77c81-116">この設定は、変更するまでこの構成に適用されます。</span><span class="sxs-lookup"><span data-stu-id="77c81-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="77c81-117">Windows PowerShell コマンドレットを使用してデバイスの更新ログを消去する</span><span class="sxs-lookup"><span data-stu-id="77c81-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="77c81-118">デバイス更新ログは、Windows PowerShell と、ユーザーの**クリアな Deviceupdatelog**コマンドレットを使用してクリアできます。</span><span class="sxs-lookup"><span data-stu-id="77c81-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="77c81-119">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="77c81-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77c81-120">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c81-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="77c81-121">1台のサーバーでデバイス更新ログを消去するには</span><span class="sxs-lookup"><span data-stu-id="77c81-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="77c81-122">次のコマンドは、Web サーバー atl-cs-001.litwareinc.com のデバイス更新ログをクリアします。</span><span class="sxs-lookup"><span data-stu-id="77c81-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="77c81-123">10日以上経過しているすべてのログエントリ (DaysBack パラメーターで指定された値) はログから削除されます。</span><span class="sxs-lookup"><span data-stu-id="77c81-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="77c81-124">すべてのデバイス更新ログを消去するには</span><span class="sxs-lookup"><span data-stu-id="77c81-124">To clear all device update logs</span></span>

  - <span data-ttu-id="77c81-125">このコマンドを実行すると、組織で現在使用されているすべてのデバイス更新ログから古いエントリ (この例では、10日以上経過したエントリ) が削除されます。</span><span class="sxs-lookup"><span data-stu-id="77c81-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="77c81-126">詳細については、「 [CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77c81-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

