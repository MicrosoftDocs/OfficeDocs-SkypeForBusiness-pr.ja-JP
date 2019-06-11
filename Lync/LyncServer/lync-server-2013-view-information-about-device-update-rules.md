---
title: 'Lync Server 2013: デバイス更新ルールに関する情報を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d873cbd80e599313b60a57cfc28eb9752d85ef66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="d6921-102">Lync Server 2013 でのデバイス更新ルールに関する情報を確認する</span><span class="sxs-lookup"><span data-stu-id="d6921-102">View information about Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6921-103">_**最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d6921-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d6921-104">更新が適用されるデバイスの種類、モデル、およびブランドを含む、既にインポートされているデバイス更新ルールについての詳細を表示します。更新プログラムのバージョンと種類更新プログラムのロケールとプール。</span><span class="sxs-lookup"><span data-stu-id="d6921-104">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="d6921-105">インポートされたすべてのデバイス更新ルール (承認待ち、展開済み、承認済み)、リコール (復元)、および使用しないことを決定したもの (リセット) に関する情報を利用できます。</span><span class="sxs-lookup"><span data-stu-id="d6921-105">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="d6921-106">Lync Server コントロールパネルまたは Windows PowerShell から、この情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d6921-106">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6921-107">仕分けルールのインポート、承認、リセット、復元、および削除を行う方法の詳細については、「 <A href="lync-server-2013-device-update-rules.md">Lync Server 2013 のデバイス更新ルール</A>」に記載されているトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6921-107">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="d6921-108">Lync Server コントロールパネルを使用してデバイス更新ルールを表示するには</span><span class="sxs-lookup"><span data-stu-id="d6921-108">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d6921-109">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d6921-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d6921-110">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d6921-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d6921-111">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d6921-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d6921-112">左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイスの更新**] ナビゲーションボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6921-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="d6921-113">インポートしたルールは、[**デバイスの更新**] ページに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6921-113">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d6921-114">Windows PowerShell コマンドレットを使用したデバイス更新ルールの表示</span><span class="sxs-lookup"><span data-stu-id="d6921-114">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d6921-115">すべてのデバイス更新ルールに関する詳細情報は、Windows PowerShell と**CsDeviceUpdateRule**コマンドレットを使用して表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="d6921-115">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="d6921-116">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="d6921-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6921-117">リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6921-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="d6921-118">すべてのデバイス更新ルールを表示するには</span><span class="sxs-lookup"><span data-stu-id="d6921-118">To view all your device update rules</span></span>

  - <span data-ttu-id="d6921-119">次のコマンドは、組織で使用するように構成されているすべてのデバイス更新規則に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="d6921-119">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="d6921-120">このコマンドは、デバイス更新ルールごとに、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="d6921-120">The command returns information similar to the following for each of your device update rules:</span></span>
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="d6921-121">特定の web サーバーですべてのデバイス更新ルールを表示するには</span><span class="sxs-lookup"><span data-stu-id="d6921-121">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="d6921-122">特定のコンピューターでデバイス更新ルールを表示するには、フィルターパラメーターの後にサーバー Id とワイルドカード文字 (\*) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6921-122">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="d6921-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d6921-123">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="d6921-124">詳細については、 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6921-124">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

