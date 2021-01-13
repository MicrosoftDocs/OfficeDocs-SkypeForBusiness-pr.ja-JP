---
title: メディア バイパスの有効化と無効化
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事の手順を使用して、Skype for Business Server コントロール パネルを使用してメディア バイパスを有効または無効にします。
ms.openlocfilehash: cb8bb06c0e15d39733e92f26867917bb4f8e6989
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816497"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="41598-103">Skype for Business Server でのメディア バイパスの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="41598-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="41598-104">この記事の手順を使用して、Skype for Business Server コントロール パネルを使用してメディア バイパスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="41598-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="41598-105">ネットワーク メディア バイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="41598-105">Enable network media bypass</span></span> 

<span data-ttu-id="41598-106">メディア バイパス設定は、Skype for Business Server 展開全体でグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="41598-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="41598-107">メディア バイパスを使用すると、通話は仲介サーバーをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="41598-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="41598-108">メディア バイパスを使用する場合の詳細については、「メディア バイパスを計画 [する」を参照してください](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="41598-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="41598-109">Skype for Business Server コントロール パネルからメディア バイパスを有効にして構成できます。</span><span class="sxs-lookup"><span data-stu-id="41598-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="41598-110">メディア バイパスを有効にして構成するには</span><span class="sxs-lookup"><span data-stu-id="41598-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="41598-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="41598-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="41598-112">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="41598-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="41598-113">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[グローバル] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="41598-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="41598-p102">[**グローバル**] ページで [**グローバル**] 構成をクリックします。存在する構成は必ず 1 つのみで、必ずグローバルという名前です。</span><span class="sxs-lookup"><span data-stu-id="41598-p102">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="41598-116">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41598-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="41598-117">[グローバル設定 **の編集] ページで** 、[メディア バイパスを **有効にする] チェック ボックス** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="41598-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="41598-118">以下のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="41598-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="41598-119">**常にバイパスする**   すべての通話でメディア バイパスを試行するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="41598-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="41598-120">通話受付管理 (CAC) が有効な場合、このオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="41598-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="41598-121">CAC が有効になっていない場合は、次の状況でこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="41598-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="41598-122">帯域幅を制御する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="41598-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="41598-123">バイパスが発生する必要がある場合を判断するために、詳細に設定された構成を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="41598-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="41598-124">ゲートウェイとクライアントの間には完全な接続があります。</span><span class="sxs-lookup"><span data-stu-id="41598-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="41598-125">**サイトと地域の構成を使用する**   CAC が有効な場合、このオプションは既定で選択され、変更できません。</span><span class="sxs-lookup"><span data-stu-id="41598-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="41598-126">このオプションを選択すると、ネットワーク構成サイトと地域を使用して、メディア バイパスが可能な場合を判断します。</span><span class="sxs-lookup"><span data-stu-id="41598-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="41598-127">このオプションを選択した場合は、マップされていないサイトのバイパスを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="41598-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="41598-128">帯域幅の制約を持たしていない同じ地域に関連付けられた 1 つ以上の大規模なサイト (大規模なセントラル サイトなど) と、帯域幅の制約がある同じ地域に関連付けられているブランチ サイトがある場合にのみ、[マップされていないサイトのバイパスを有効にする] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="41598-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="41598-129">マップされていないサイトのバイパスを有効にした場合、すべてのサイトに関連付けられたすべてのサブネットを指定する必要がなされるのではなく、ブランチ サイトに関連付けられたサブネットのみを指定するから、構成が効率化されます。</span><span class="sxs-lookup"><span data-stu-id="41598-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="41598-130">CAC が有効な場合は、[マップされていないサイトのバイパスを有効にする] チェック ボックスをオンにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41598-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="41598-131">[**確定**] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="41598-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="41598-132">ネットワーク メディア バイパスを無効にする</span><span class="sxs-lookup"><span data-stu-id="41598-132">Disable network media bypass</span></span>

<span data-ttu-id="41598-133">メディア バイパス設定は、Skype for Business Server 展開全体でグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="41598-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="41598-134">メディア バイパスを使用すると、通話は仲介サーバーをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="41598-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="41598-135">メディア バイパスを使用する場合の詳細については、「メディア バイパスを計画 [する」を参照してください](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="41598-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="41598-136">Skype for Business Server コントロール パネルからメディア バイパスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="41598-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="41598-137">メディア バイパスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="41598-137">To disable media bypass</span></span>

1.  <span data-ttu-id="41598-138">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="41598-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="41598-139">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="41598-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="41598-140">左側のナビゲーション バーで、[ネットワーク構成] **をクリック** し、[グローバル] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="41598-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="41598-p106">[**グローバル**] ページで [**グローバル**] 構成をクリックします。存在する構成は必ず 1 つのみで、必ずグローバルという名前です。</span><span class="sxs-lookup"><span data-stu-id="41598-p106">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="41598-143">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41598-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="41598-144">[**グローバル設定の編集**] ページの [**メディア バイパスを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="41598-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="41598-145">[**確定**] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="41598-145">Click **Commit** to save your changes.</span></span>

  
