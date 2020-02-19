---
title: 'Lync Server 2013: 通話受付管理の有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call admission control
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48184650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e181c0fbc4c3794d14b364f6fd2affa4e4358f4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="72f91-102">Lync Server 2013 で通話受付管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="72f91-102">Enable call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72f91-103">_**トピックの最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="72f91-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="72f91-104">通話受付管理展開のネットワーク設定を構成したら、帯域幅ポリシーを反映させるために CAC を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72f91-104">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="72f91-105">詳細については、以下のコマンドレットの Lync Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="72f91-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="72f91-106">Get-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="72f91-106">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="72f91-107">Get-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="72f91-107">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="72f91-108">Get-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="72f91-108">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="72f91-109">管理シェルを使用して通話受付管理を有効にするには</span><span class="sxs-lookup"><span data-stu-id="72f91-109">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="72f91-110">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="72f91-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="72f91-p101">Set-CsNetworkConfiguration コマンドレットを実行して、ネットワークの CAC を有効にします。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="72f91-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="72f91-113">ネットワークの CAC を無効にする場合は、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="72f91-113">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="72f91-114">Lync Server コントロール パネルを使用して通話受付管理を有効にするには</span><span class="sxs-lookup"><span data-stu-id="72f91-114">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="72f91-115">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="72f91-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="72f91-116">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72f91-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="72f91-117">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72f91-117">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="72f91-118">[**グローバル**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="72f91-118">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="72f91-119">一覧で [**グローバル**] をクリックし、[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72f91-119">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="72f91-120">[**グローバル設定の編集**] ページの [**通話受付管理の有効化**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="72f91-120">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72f91-121">展開全体で通話受付管理を無効にする場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="72f91-121">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="72f91-122">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72f91-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

