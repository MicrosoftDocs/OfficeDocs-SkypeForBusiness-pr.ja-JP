---
title: 'Lync Server 2013: 通話受付管理の有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1482ce09ff4501deb4c3acbb5df77d014b314ffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="13545-102">Lync Server 2013 での通話受付管理の有効化</span><span class="sxs-lookup"><span data-stu-id="13545-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13545-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="13545-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="13545-104">通話受付管理 (CAC) は、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができる地域、サイト、およびサブネットで構成されるネットワークです。</span><span class="sxs-lookup"><span data-stu-id="13545-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="13545-105">CAC ネットワークの構成後、CAC を有効にして、帯域幅制限を強制的に適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13545-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="13545-106">これを行うには、Lync Server コントロールパネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="13545-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="13545-107">Lync Server コントロールパネルから CAC を有効にするには</span><span class="sxs-lookup"><span data-stu-id="13545-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="13545-108">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="13545-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="13545-109">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="13545-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="13545-110">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13545-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="13545-111">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13545-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="13545-112">[**グローバル**] ページで [**グローバル**] 構成をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13545-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="13545-113">Microsoft Lync Server 2013 の展開に対して構成できるネットワークは1つだけなので、リストに複数のネットワーク構成が存在することはありません。</span><span class="sxs-lookup"><span data-stu-id="13545-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="13545-114">グローバル構成の名前は変更できません。</span><span class="sxs-lookup"><span data-stu-id="13545-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="13545-115">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13545-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="13545-116">[**グローバル設定の編集**] ページの [**通話受付管理の有効化**] チェック ボックスをオンにして、[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13545-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="13545-p104">[**確定**] をクリックすると、構成のテストが実行されます。 [**グローバル設定の編集**] ダイアログ ボックスが閉じ、再び、[**グローバル**] ページが表示されます。 ネットワーク構成で、ネットワークの正しい動作を妨げるエラーまたは不整合 (たとえば、すべての地域が他のすべての地域に地域間ルート経由でそれぞれ接続される必要があるがそうなっていない場合) が検出されると、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="13545-p104">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="13545-p105">ネットワーク構成に変更を加えた場合は、グローバル構成を開き [**確定**] をクリックすることで、検証チェックを再度実行できます。 最初に、CAC を無効にする必要はありません。 チェック ボックスをオンのままにして、[**確定**] をクリックしてください。 これは、構成に変更を加えていない場合も含め、いつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="13545-p105">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13545-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="13545-123">See Also</span></span>


[<span data-ttu-id="13545-124">Lync Server 2013 での通話受付管理の概要</span><span class="sxs-lookup"><span data-stu-id="13545-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="13545-125">Lync Server 2013 での通話受付管理の計画</span><span class="sxs-lookup"><span data-stu-id="13545-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="13545-126">Lync Server 2013 で通話受付管理を構成する</span><span class="sxs-lookup"><span data-stu-id="13545-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="13545-127">Get-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="13545-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="13545-128">Get-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="13545-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="13545-129">Get-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="13545-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

