---
title: 'Lync Server 2013: コンピューター上で実行されているサービスの状態を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95c633079e45eba40bd59c7666c752c2ef68b498
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518394"
---
# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="9c640-102">Lync Server 2013 でコンピューター上で実行されているサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="9c640-102">View the status of services running on a computer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c640-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="9c640-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="9c640-104">Lync server 2013 コントロールパネルを使用して、Lync Server トポロジ内の特定のコンピューターで実行されているすべてのサービスを表示し、各サービスの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9c640-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="9c640-105">コンピューターで実行されているサービスの状態を表示するには</span><span class="sxs-lookup"><span data-stu-id="9c640-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="9c640-106">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9c640-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9c640-107">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="9c640-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9c640-108">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c640-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9c640-109">左側のナビゲーション バーで [**トポロジ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c640-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="9c640-110">[**状態**] ページで、必要に応じてリストを並べ替えまたは検索して対象のコンピューターを見つけ、そのコンピューター名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c640-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="9c640-111">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c640-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="9c640-112">コンピューターで実行されているサービスの最新状態を表示するには、[**サービス状態の取得**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c640-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="9c640-113">コンピューターで実行されている特定のサービスの一覧および各サービスの状態を表示するには、[**プロパティ**] をクリックし、[**閉じる**] をクリックして一覧に戻ります。</span><span class="sxs-lookup"><span data-stu-id="9c640-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9c640-114">Windows PowerShell コマンドレットを使用してサービスの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="9c640-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9c640-115">また、Windows PowerShell と **Get-CsWindowsService** コマンドレットを使用して、サービスの状態を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c640-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="9c640-116">このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="9c640-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9c640-117">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c640-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="9c640-118">サービス状態を表示するには</span><span class="sxs-lookup"><span data-stu-id="9c640-118">To view service status</span></span>

  - <span data-ttu-id="9c640-119">コンピューターのサービス状態を表示するには、Lync Server 管理シェルで次のようなコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9c640-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="9c640-120">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="9c640-120">This command returns information similar to the following:</span></span>
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

<span data-ttu-id="9c640-121">詳細については、「 [get-help](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c640-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c640-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c640-122">See Also</span></span>


[<span data-ttu-id="9c640-123">Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="9c640-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

