---
title: 'Lync Server 2013: 通話受付制御を有効にする'
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
ms.openlocfilehash: 1776cc173d7ddec50aae34e8316844d14f67b009
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="ec481-102">Lync Server 2013 で通話受付制御を有効にする</span><span class="sxs-lookup"><span data-stu-id="ec481-102">Enable call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec481-103">_**最終更新日:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ec481-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ec481-104">通話受付管理展開のネットワーク設定を構成したら、帯域幅ポリシーを反映させるために CAC を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec481-104">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>

<span data-ttu-id="ec481-105">詳細については、次のコマンドレットの Lync Server 管理シェルに関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec481-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="ec481-106">Get-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="ec481-106">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)

  - [<span data-ttu-id="ec481-107">Set-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="ec481-107">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)

  - [<span data-ttu-id="ec481-108">Remove-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="ec481-108">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)

<div>

## <a name="to-enable-call-admission-control-by-using-management-shell"></a><span data-ttu-id="ec481-109">管理シェルを使用して通話受付制御を有効にするには</span><span class="sxs-lookup"><span data-stu-id="ec481-109">To enable call admission control by using Management Shell</span></span>

1.  <span data-ttu-id="ec481-110">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec481-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ec481-p101">Set-CsNetworkConfiguration コマンドレットを実行して、ネットワークの CAC を有効にします。たとえば、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec481-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    <span data-ttu-id="ec481-113">ネットワークの CAC を無効にする場合は、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="ec481-113">If you want to disable CAC in your network, run the following:</span></span>
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

</div>

<div>

## <a name="to-enable-call-admission-control-by-using-lync-server-control-panel"></a><span data-ttu-id="ec481-114">Lync Server コントロールパネルを使用して通話受付制御を有効にするには</span><span class="sxs-lookup"><span data-stu-id="ec481-114">To enable call admission control by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ec481-115">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ec481-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ec481-116">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ec481-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="ec481-117">左側のナビゲーション バーで [**ネットワーク構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec481-117">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="ec481-118">[**グローバル**] ナビゲーション ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec481-118">Click the **Global** navigation button.</span></span>

4.  <span data-ttu-id="ec481-119">一覧で [**グローバル**] をクリックし、[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec481-119">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="ec481-120">[**グローバル設定の編集**] ページの [**通話受付管理の有効化**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ec481-120">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ec481-121">展開全体で通話受付管理を無効にする場合は、このチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ec481-121">If you want to disable call admission control throughout your deployment, clear this check box.</span></span>

    
    </div>

6.  <span data-ttu-id="ec481-122">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec481-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

