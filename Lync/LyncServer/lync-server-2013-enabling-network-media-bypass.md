---
title: 'Lync Server 2013: ネットワークメディアバイパスの有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4caab36c57c3c8901bd0691e5623f232879bd03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528524"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="98ae5-102">Lync Server 2013 でのネットワークメディアバイパスの有効化</span><span class="sxs-lookup"><span data-stu-id="98ae5-102">Enabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98ae5-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="98ae5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="98ae5-104">メディアバイパスの設定は、Microsoft Lync Server 2013 の展開全体でグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="98ae5-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="98ae5-105">メディアバイパスは、呼び出しが仲介サーバーをバイパスすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="98ae5-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="98ae5-106">メディアバイパスを使用するタイミングの詳細については、「計画」セクションの「 [Lync Server 2013 でのメディアバイパスの計画](lync-server-2013-planning-for-media-bypass.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98ae5-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="98ae5-107">Lync Server コントロールパネルからメディアバイパスを有効にし、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="98ae5-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="98ae5-108">メディアバイパスを有効にして構成するには</span><span class="sxs-lookup"><span data-stu-id="98ae5-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="98ae5-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="98ae5-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="98ae5-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="98ae5-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="98ae5-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98ae5-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="98ae5-112">左側のナビゲーション バーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98ae5-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="98ae5-p103">[**グローバル**] ページで [**グローバル**] 構成をクリックします。存在する構成は必ず 1 つのみで、必ずグローバルという名前です。</span><span class="sxs-lookup"><span data-stu-id="98ae5-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="98ae5-115">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="98ae5-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="98ae5-116">[ **グローバル設定の編集** ] ページで、[ **メディアバイパスを有効にする** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="98ae5-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="98ae5-117">以下のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98ae5-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="98ae5-118">**常にバイパス**    すべての呼び出しでメディアバイパスを試行するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98ae5-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="98ae5-119">通話受付管理 (CAC) が有効になっている場合、このオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="98ae5-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="98ae5-120">CAC が有効になっていない場合は、次の状況でこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="98ae5-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="98ae5-121">帯域幅を制御する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="98ae5-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="98ae5-122">バイパスが発生するタイミングを特定するために、詳細に設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="98ae5-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="98ae5-123">ゲートウェイとクライアントの間には、完全な接続があります。</span><span class="sxs-lookup"><span data-stu-id="98ae5-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="98ae5-124">**サイトと地域の構成**     を使用するCAC が有効になっている場合、このオプションは既定でオンになっており、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="98ae5-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="98ae5-125">このオプションが選択されている場合、ネットワーク構成サイトと地域を使用して、メディアバイパスがいつ可能になるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="98ae5-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="98ae5-126">このオプションを選択した場合は、マップされていないサイトのバイパスを有効にするかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="98ae5-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="98ae5-127">帯域幅制限を持たない同じ地域に関連付けられた1つ以上の大規模なサイト (たとえば、大規模な中央サイト) を所有しており、さらに帯域幅制限がある同じ地域に関連付けられたブランチサイトがある場合にのみ、[ **非マッピングサイトのバイパスを有効に** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="98ae5-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="98ae5-128">非マッピングサイトのバイパスを有効にすると、すべてのサイトに関連付けられているすべてのサブネットを指定する必要がなく、ブランチサイトに関連付けられたサブネットのみを指定するので、構成は簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="98ae5-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="98ae5-129">CAC が有効になっている場合は、[マップされてい **ないサイトのバイパスを有効に** する] チェックボックスをオンにしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="98ae5-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="98ae5-130">[**確定**] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="98ae5-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98ae5-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="98ae5-131">See Also</span></span>


[<span data-ttu-id="98ae5-132">Lync Server 2013 でのネットワークメディアバイパスの無効化</span><span class="sxs-lookup"><span data-stu-id="98ae5-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="98ae5-133">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="98ae5-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="98ae5-134">Lync Server 2013 でのメディアバイパスの計画</span><span class="sxs-lookup"><span data-stu-id="98ae5-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

