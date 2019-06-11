---
title: 'Lync Server 2013: ネットワークメディアのバイパスを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff18c69d6d257a520d2413bff266c97879d4963e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="29e12-102">Lync Server 2013 でネットワークメディアのバイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="29e12-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29e12-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="29e12-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="29e12-104">メディアバイパスの設定は、Microsoft Lync Server 2013 の展開でグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="29e12-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="29e12-105">メディアのバイパスでは、仲介サーバーを経由せずに通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="29e12-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="29e12-106">メディアのバイパスを使用する場合の詳細については、「計画」セクションの「 [Lync Server 2013 でのメディアのバイパスの計画](lync-server-2013-planning-for-media-bypass.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e12-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="29e12-107">Lync Server コントロールパネルでメディアのバイパスを有効にして構成することができます。</span><span class="sxs-lookup"><span data-stu-id="29e12-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="29e12-108">メディアバイパスを有効にして構成するには</span><span class="sxs-lookup"><span data-stu-id="29e12-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="29e12-109">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="29e12-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="29e12-110">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="29e12-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="29e12-111">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="29e12-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="29e12-112">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29e12-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="29e12-113">[**グローバル**] ページで、[**グローバル**構成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29e12-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="29e12-114">構成は常に1つだけであり、常に Global という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="29e12-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="29e12-115">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29e12-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="29e12-116">[**グローバル設定の編集**] ページで、[**メディアバイパスを有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="29e12-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="29e12-117">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="29e12-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="29e12-118">**[常にスキップ**   ] このチェックボックスをオンにすると、すべての通話でメディアのバイパスが試行されます。</span><span class="sxs-lookup"><span data-stu-id="29e12-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="29e12-119">通話受付制御 (CAC) が有効になっている場合、このオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="29e12-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="29e12-120">CAC が有効になっていない場合は、次のような場合にこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="29e12-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="29e12-121">帯域幅の調整は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29e12-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="29e12-122">何度も設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="29e12-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="29e12-123">ゲートウェイとクライアントの間には完全な接続があります。</span><span class="sxs-lookup"><span data-stu-id="29e12-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="29e12-124">**サイトと地域の構成**   を使用する CAC が有効になっている場合、このオプションは既定でオンになっており、変更できません。</span><span class="sxs-lookup"><span data-stu-id="29e12-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="29e12-125">このオプションが選択されている場合は、メディアのバイパスを可能にするかどうかを判断するためにネットワーク構成サイトと領域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="29e12-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="29e12-126">このオプションを選択すると、マップされていないサイトに対しては、[バイパス] を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="29e12-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="29e12-127">帯域幅の制約のない1つ以上の大規模なサイト (たとえば、大規模なセントラルサイトなど) があり、それに関連付けられたブランチサイトがある場合にのみ、[**非マッピングサイトに対してバイパスを有効に**する] チェックボックスをオンにします。帯域幅の制約がある同じ地域。</span><span class="sxs-lookup"><span data-stu-id="29e12-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="29e12-128">非マッピングサイトに対してバイパスを有効にすると、すべてのサイトに関連付けられているすべてのサブネットを指定する必要がなく、ブランチサイトに関連付けられているサブネットのみを指定しているため、構成が効率化されます。</span><span class="sxs-lookup"><span data-stu-id="29e12-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="29e12-129">CAC が有効になっている場合は、[**非マッピングサイトに対してバイパスを有効に**する] チェックボックスをオンにしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="29e12-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="29e12-130">[**コミット**] をクリックして変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="29e12-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29e12-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="29e12-131">See Also</span></span>


[<span data-ttu-id="29e12-132">Lync Server 2013 でネットワークメディアのバイパスを無効にする</span><span class="sxs-lookup"><span data-stu-id="29e12-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="29e12-133">Lync Server 2013 のグローバルメディアバイパスオプション</span><span class="sxs-lookup"><span data-stu-id="29e12-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="29e12-134">Lync Server 2013 でのメディア バイパスの計画</span><span class="sxs-lookup"><span data-stu-id="29e12-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

