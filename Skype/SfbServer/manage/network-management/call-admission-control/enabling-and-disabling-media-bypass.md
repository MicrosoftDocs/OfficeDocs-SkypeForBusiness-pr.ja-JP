---
title: メディアのバイパスを有効または無効にします。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ビジネス サーバーのコントロール パネルの Skype を使用してメディア バイ パスを無効にするを有効またはこの資料の手順を使用します。
ms.openlocfilehash: eebbc111f0d205be8dced9ec8ddb5150deff8119
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874288"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="38a62-103">Skype for Business Server でのメディア バイパスの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="38a62-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="38a62-104">ビジネス サーバーのコントロール パネルの Skype を使用してメディア バイ パスを無効にするを有効またはこの資料の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="38a62-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="38a62-105">ネットワーク メディアのバイパスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="38a62-105">Enable network media bypass</span></span> 

<span data-ttu-id="38a62-106">メディア バイ パスの設定は、Skype ビジネス サーバーの展開の間でグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="38a62-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="38a62-107">メディア バイ パスでは、仲介サーバーをバイパスする呼び出しを許可します。</span><span class="sxs-lookup"><span data-stu-id="38a62-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="38a62-108">使用する場合の詳細については、メディアはバイパス、[バイパス メディアの計画](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38a62-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="38a62-109">有効にして、ビジネス サーバーのコントロール パネルの Skype からのメディア バイ パスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="38a62-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="38a62-110">メディアのバイパスを有効にして構成するには</span><span class="sxs-lookup"><span data-stu-id="38a62-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="38a62-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="38a62-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="38a62-112">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="38a62-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="38a62-113">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a62-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="38a62-114">[**グローバル**] ページで、[**グローバル**構成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a62-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="38a62-115">常に 1 つだけの構成では、およびグローバルの名前には常にします。</span><span class="sxs-lookup"><span data-stu-id="38a62-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="38a62-116">[**編集**] メニュー**の詳細の表示**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a62-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="38a62-117">**グローバル設定の編集**] ページで、[**メディア バイ パスを有効にする**] チェック ボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a62-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="38a62-118">次のオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="38a62-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="38a62-119">**常にバイパス**   のすべての呼び出しでメディアをしようとするには、このオプションを省略] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38a62-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="38a62-120">このオプションは呼受付制御 (CAC) が有効になっている場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="38a62-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="38a62-121">CAC が有効でない場合は、以下の状況でこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="38a62-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="38a62-122">帯域幅の制御の必要性はありません。</span><span class="sxs-lookup"><span data-stu-id="38a62-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="38a62-123">バイパスが発生する必要がありますを決定するのには詳細な構成の必要はありません。</span><span class="sxs-lookup"><span data-stu-id="38a62-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="38a62-124">ゲートウェイとクライアント間の完全な接続があります。</span><span class="sxs-lookup"><span data-stu-id="38a62-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="38a62-125">**サイトと領域の構成を使用して、**   場合の CAC が有効になっている場合、このオプションがデフォルトで選択されて、変更できません。</span><span class="sxs-lookup"><span data-stu-id="38a62-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="38a62-126">このオプションを選択すると、ネットワーク構成サイトと地域は、メディアのバイパスが可能な場合の決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="38a62-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="38a62-127">このオプションを選択すると、マップされていないサイトのバイパスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="38a62-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="38a62-128">サイトがある 1 つ以上大きい同じ領域に関連付けられている帯域幅の制約 (たとえば、大規模なセントラル サイト) ではありませんを使用してもいくつかのブランチ サイトに関連付けられている場合にのみ、**マップされていないサイトのバイパスを有効にする**] チェック ボックスをクリックします帯域幅の制約が同じ地域です。</span><span class="sxs-lookup"><span data-stu-id="38a62-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="38a62-129">有効にすると、マップされていないサイトのバイパス、すべてのサイトに関連付けられているすべてのサブネットを指定する必要があるのではなく、ブランチ サイトに関連付けられているサブネットだけを指定するための構成の効率が高まります。</span><span class="sxs-lookup"><span data-stu-id="38a62-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="38a62-130">CAC が有効になっている場合は、**マップされていないサイトのバイパスを有効にする**] チェック ボックスを選択しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38a62-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="38a62-131">**コミット**して変更を保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a62-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="38a62-132">ネットワーク メディアのバイパスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="38a62-132">Disable network media bypass</span></span>

<span data-ttu-id="38a62-133">メディア バイ パスの設定は、Skype ビジネス サーバーの展開の間でグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="38a62-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="38a62-134">メディア バイ パスでは、仲介サーバーをバイパスする呼び出しを許可します。</span><span class="sxs-lookup"><span data-stu-id="38a62-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="38a62-135">使用する場合の詳細については、メディアはバイパス、[バイパス メディアの計画](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38a62-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="38a62-136">ビジネス サーバーのコントロール パネルの Skype からのメディア バイ パスを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="38a62-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="38a62-137">メディア バイ パスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="38a62-137">To disable media bypass</span></span>

1.  <span data-ttu-id="38a62-138">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="38a62-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="38a62-139">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="38a62-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="38a62-140">左側のナビゲーション ・ バーでは、**ネットワーク構成**をクリックし、し、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a62-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="38a62-141">[**グローバル**] ページで、[**グローバル**構成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a62-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="38a62-142">常に 1 つだけの構成では、およびグローバルの名前には常にします。</span><span class="sxs-lookup"><span data-stu-id="38a62-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="38a62-143">[**編集**] メニュー**の詳細の表示**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a62-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="38a62-144">[**グローバル設定の編集**] ページで、[**メディア バイ パスを有効にする**] チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="38a62-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="38a62-145">**コミット**して変更を保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38a62-145">Click **Commit** to save your changes.</span></span>

  
