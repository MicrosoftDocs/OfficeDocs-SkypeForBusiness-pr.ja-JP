---
title: 'Lync Server 2013: qoe (Quality of Experience) の有効化'
description: 'Lync Server 2013: qoe (Quality of Experience) を有効にします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43746227395477596ff5e39809cf819c110287ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547873"
---
# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="e951f-103">Lync Server 2013 の [qoe (Quality of Experience)] を有効にする</span><span class="sxs-lookup"><span data-stu-id="e951f-103">Enable Quality of Experience in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e951f-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e951f-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e951f-105">QoE (Quality of Experience) は、メディアの品質と、通話およびセッションに関係する参加者、デバイス名、ドライバー、IP アドレス、およびエンドポイントの種類についての情報を示す数値データを記録します。</span><span class="sxs-lookup"><span data-stu-id="e951f-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="e951f-106">詳細については、「計画」のドキュメントの「 [planning for monitoring In Lync Server 2013](lync-server-2013-planning-for-monitoring.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e951f-106">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="e951f-107">組織全体または組織内の各サイトで QoE を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e951f-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e951f-108">QoE を有効にするには、まず、監視を構成して、監視バック エンド データベースに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e951f-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="e951f-109">詳細については、「 <A href="lync-server-2013-deploying-monitoring.md">Lync Server 2013 での監視の展開</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e951f-109">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="e951f-110">Lync Server コントロールパネルを使用して QoE を有効にするには</span><span class="sxs-lookup"><span data-stu-id="e951f-110">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e951f-111">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e951f-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e951f-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="e951f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e951f-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e951f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e951f-114">左側のナビゲーション バーで [**監視およびアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e951f-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="e951f-115">[**QoE データ**] ページで、表から該当するコレクションをクリックして、[**操作**]、[**QoE を有効にする**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="e951f-115">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e951f-116">Windows PowerShell コマンドレットを使用して QoE を有効にする</span><span class="sxs-lookup"><span data-stu-id="e951f-116">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e951f-117">QoE を有効にするには、Windows PowerShell と、 **-CsQoEConfiguration の設定** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e951f-117">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="e951f-118">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e951f-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e951f-119">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="e951f-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="e951f-120">1 つの場所に対して QoE を有効にするには</span><span class="sxs-lookup"><span data-stu-id="e951f-120">To enable QoE for a single location</span></span>

  - <span data-ttu-id="e951f-121">QoE を有効にするには、EnableQoE パラメーターを True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="e951f-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="e951f-122">1 つの場所に対して QoE を無効にするには</span><span class="sxs-lookup"><span data-stu-id="e951f-122">To disable QoE for a single location</span></span>

  - <span data-ttu-id="e951f-p105">QoE を無効にするには、EnableQoE パラメーターを False ($False) に設定します。これによって監視がアンインストールされることはありません。QoE データの収集と保存が停止されるだけです。</span><span class="sxs-lookup"><span data-stu-id="e951f-p105">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="e951f-126">複数の場所の QoE を 1 つのコマンドで有効にするには</span><span class="sxs-lookup"><span data-stu-id="e951f-126">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="e951f-127">このコマンドを実行すると、組織内で現在使用されているすべての QoE 構成設定に対して QoE が有効になります。</span><span class="sxs-lookup"><span data-stu-id="e951f-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="e951f-128">詳細については、「 [-CsQoEConfiguration 設定](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e951f-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e951f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="e951f-129">See Also</span></span>


[<span data-ttu-id="e951f-130">Lync Server 2013 での監視の計画</span><span class="sxs-lookup"><span data-stu-id="e951f-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="e951f-131">Lync Server 2013 での監視の展開</span><span class="sxs-lookup"><span data-stu-id="e951f-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

