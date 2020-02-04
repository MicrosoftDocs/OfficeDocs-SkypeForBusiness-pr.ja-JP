---
title: 'Lync Server 2013: 通話受付制御を有効にする'
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
ms.openlocfilehash: b89c9b888dc610d60b2abbcefd4c9c67e9b0572e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="6fcf7-102">Lync Server 2013 での通話受付制御の有効化</span><span class="sxs-lookup"><span data-stu-id="6fcf7-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fcf7-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6fcf7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6fcf7-104">通話受付管理 (CAC) は、地域、サイト、およびサブネットで構成されるネットワークで、使用可能な帯域幅に基づいてオーディオおよびビデオ伝送に制限を課すことができます。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="6fcf7-105">CAC ネットワークを構成したら、CAC を有効にして帯域幅の制限を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="6fcf7-106">Lync Server コントロールパネルを使うと、この操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="6fcf7-107">Lync Server コントロールパネルで CAC を有効にするには</span><span class="sxs-lookup"><span data-stu-id="6fcf7-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6fcf7-108">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6fcf7-109">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6fcf7-110">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6fcf7-111">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="6fcf7-112">[**グローバル**] ページで、[**グローバル**構成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6fcf7-113">Microsoft Lync Server 2013 の展開用に1つのネットワークのみを構成できます。そのため、リストには複数のネットワーク構成を設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="6fcf7-114">グローバル構成の名前を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="6fcf7-115">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="6fcf7-116">[**グローバル設定の編集**] ページで、[**通話受付制御を有効にする**] チェックボックスをオンにし、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="6fcf7-117">[**コミット**] をクリックすると、構成のテストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-117">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="6fcf7-118">[**グローバル設定の編集**] ダイアログボックスが閉じ、**グローバル**ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-118">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="6fcf7-119">ネットワーク構成でエラーや不整合が検出された場合、そのエラーや不整合が正常に動作しなくなる場合 (たとえば、すべての地域が相互に接続されているルートを介してすべての地域に接続されていない場合) は、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-119">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="6fcf7-120">ネットワーク構成を変更した場合は、[グローバル構成] を開き、[**コミット**] をクリックして、検証チェックをもう一度実行できます。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-120">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="6fcf7-121">まず、CAC を無効にする必要はありません。チェックボックスをオンのままにして、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-121">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="6fcf7-122">この操作は、構成を変更することなくいつでも行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6fcf7-122">You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fcf7-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fcf7-123">See Also</span></span>


[<span data-ttu-id="6fcf7-124">Lync Server 2013 の通話受付制御の概要</span><span class="sxs-lookup"><span data-stu-id="6fcf7-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="6fcf7-125">Lync Server 2013 での通話受付管理の計画</span><span class="sxs-lookup"><span data-stu-id="6fcf7-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="6fcf7-126">Lync Server 2013 での通話受付制御の構成</span><span class="sxs-lookup"><span data-stu-id="6fcf7-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="6fcf7-127">Get-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="6fcf7-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="6fcf7-128">Set-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="6fcf7-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="6fcf7-129">Remove-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="6fcf7-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

