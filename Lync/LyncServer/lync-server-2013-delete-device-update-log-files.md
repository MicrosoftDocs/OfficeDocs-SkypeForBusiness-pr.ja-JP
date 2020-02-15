---
title: 'Lync Server 2013: デバイス更新ログファイルの削除'
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
ms.openlocfilehash: 4f5b8ed6d087bb7b80ba93aead7c3ab530c82000
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="c2917-102">Lync Server 2013 でのデバイス更新ログファイルの削除</span><span class="sxs-lookup"><span data-stu-id="c2917-102">Delete Device Update log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2917-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c2917-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c2917-104">デバイス更新 Web サービスは、ログファイルの広範なコレクションを保持します。</span><span class="sxs-lookup"><span data-stu-id="c2917-104">The Device Update Web service keeps an extensive collection of log files.</span></span> <span data-ttu-id="c2917-105">このコレクションには、サービス自体によって実行された監査ログと、クライアントデバイスからアップロードされたログファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c2917-105">This collection includes both audit logs conducted by the service itself and log files uploaded from client devices.</span></span> <span data-ttu-id="c2917-106">サーバーがデバイス更新 Web サービスのログにいっぱいにならないようにするには、特定の日数になっていたログファイルを消去することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c2917-106">To prevent the server from filling up with Device Update Web service logs, you’ll probably want to clear it of log files that have been around for a certain number of days.</span></span> <span data-ttu-id="c2917-107">この日数は、更新アクティビティと、組織内のクライアントデバイス数、および Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="c2917-107">Set this number of days based on update activity and the number of client devices in your organization, and by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a><span data-ttu-id="c2917-108">Lync Server コントロールパネルを使用してデバイス更新ログをクリアするには</span><span class="sxs-lookup"><span data-stu-id="c2917-108">To clear the device update log by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c2917-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c2917-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c2917-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2917-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="c2917-111">左側のナビゲーション バーで **[クライアント]** をクリックし、**[デバイス ログ構成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2917-111">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="c2917-112">**[デバイス ログ構成]** ページで、変更する構成をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2917-112">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="c2917-113">[**ログ設定の編集**] ダイアログボックスの [**ログファイルを保持する日数 (1-365)**] で、日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2917-113">In the **Edit Log Setting** dialog box, in **Number of days to keep log files (1-365)**, specifiy a number of days.</span></span>

5.  <span data-ttu-id="c2917-114">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2917-114">Click **Commit**.</span></span> <span data-ttu-id="c2917-115">指定した日数を超えるまでサーバー上に存在していたすべてのファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c2917-115">All files that have been on the server for more than the specified number of day are deleted.</span></span> <span data-ttu-id="c2917-116">この設定は、変更するまでこの構成に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c2917-116">This setting will apply to this configuration until you change it.</span></span>

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a><span data-ttu-id="c2917-117">Windows PowerShell コマンドレットを使用してデバイス更新ログをクリアする</span><span class="sxs-lookup"><span data-stu-id="c2917-117">Clearing the Device Update Log by Using the Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c2917-118">Windows PowerShell を使用してデバイス更新ログをクリアすることができます。また、 **CsDeviceUpdateLog**コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c2917-118">You can clear device update logs by using Windows PowerShell and the **Clear-CsDeviceUpdateLog** cmdlet.</span></span> <span data-ttu-id="c2917-119">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="c2917-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c2917-120">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2917-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a><span data-ttu-id="c2917-121">1台のサーバー上のデバイス更新ログをクリアするには</span><span class="sxs-lookup"><span data-stu-id="c2917-121">To clear device update logs on one server</span></span>

  - <span data-ttu-id="c2917-122">次のコマンドを実行すると、Web サーバー atl-cs-001.litwareinc.com のデバイス更新ログがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="c2917-122">The following command clears the device update log on the Web server atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="c2917-123">10日以上経過したすべてのログエントリ (DaysBack パラメーターで指定された値) はログから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c2917-123">All log entries more than 10 days old (the value specified by the DaysBack parameter) will be removed from the log.</span></span>
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a><span data-ttu-id="c2917-124">すべてのデバイス更新ログをクリアするには</span><span class="sxs-lookup"><span data-stu-id="c2917-124">To clear all device update logs</span></span>

  - <span data-ttu-id="c2917-125">このコマンドは、組織で現在使用されているすべてのデバイス更新ログから古いエントリ (この例では、10日以上経過したエントリ) を削除します。</span><span class="sxs-lookup"><span data-stu-id="c2917-125">This command removes outdated entries (in this example, entries more than 10 days old) from all the device update logs currently in use in your organization.</span></span>
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

<span data-ttu-id="c2917-126">詳細につい[ては、](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) 「」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2917-126">For details, see the Help topic for the [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

