---
title: メディアのバイパスを有効または無効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: この記事の手順を使用して、Skype for Business Server コントロールパネルを使用してメディアのバイパスを有効または無効にします。
ms.openlocfilehash: d1c0a5eb409c6bb5c07c530b4799ab8a53a9fddb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817546"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="f05d9-103">Skype for Business Server でのメディア バイパスの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="f05d9-103">Enabling and disabling media bypass in Skype for Business Server</span></span>

<span data-ttu-id="f05d9-104">この記事の手順を使用して、Skype for Business Server コントロールパネルを使用してメディアのバイパスを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-104">Use the procedures in this article to enable or disable media bypass by using the Skype for Business Server Control Panel.</span></span>

## <a name="enable-network-media-bypass"></a><span data-ttu-id="f05d9-105">ネットワークメディアのバイパスを有効にする</span><span class="sxs-lookup"><span data-stu-id="f05d9-105">Enable network media bypass</span></span> 

<span data-ttu-id="f05d9-106">メディアバイパスの設定は、Skype for Business Server の展開でグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-106">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="f05d9-107">メディアのバイパスでは、仲介サーバーを経由せずに通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-107">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="f05d9-108">メディアのバイパスを使用する場合について詳しくは、「[メディアバイパスの計画](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f05d9-108">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>

<span data-ttu-id="f05d9-109">Skype for Business Server コントロールパネルでメディアのバイパスを有効にして構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-109">You can enable and configure media bypass from the Skype for Business Server Control Panel.</span></span>


### <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="f05d9-110">メディアバイパスを有効にして構成するには</span><span class="sxs-lookup"><span data-stu-id="f05d9-110">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="f05d9-111">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f05d9-112">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f05d9-113">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-113">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="f05d9-114">[**グローバル**] ページで、[**グローバル**構成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-114">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="f05d9-115">構成は常に1つだけであり、常に Global という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="f05d9-115">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="f05d9-116">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="f05d9-117">[**グローバル設定の編集**] ページで、[**メディアバイパスを有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="f05d9-118">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f05d9-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="f05d9-119">**[常にスキップ**   ] このチェックボックスをオンにすると、すべての通話でメディアのバイパスが試行されます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="f05d9-120">通話受付制御 (CAC) が有効になっている場合、このオプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f05d9-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="f05d9-121">CAC が有効になっていない場合は、次のような場合にこのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f05d9-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="f05d9-122">帯域幅の調整は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f05d9-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="f05d9-123">何度も設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f05d9-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="f05d9-124">ゲートウェイとクライアントの間には完全な接続があります。</span><span class="sxs-lookup"><span data-stu-id="f05d9-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="f05d9-125">**サイトと地域の構成**   を使用する CAC が有効になっている場合、このオプションは既定でオンになっており、変更できません。</span><span class="sxs-lookup"><span data-stu-id="f05d9-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="f05d9-126">このオプションが選択されている場合は、メディアのバイパスを可能にするかどうかを判断するためにネットワーク構成サイトと領域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="f05d9-127">このオプションを選択すると、マップされていないサイトに対しては、[バイパス] を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="f05d9-128">帯域幅の制約がない1つ以上の大規模なサイト (たとえば、大規模なセントラルサイトなど) が、帯域幅の制約がある同じ地域に関連付けられている場合にのみ、[**非マッピングサイトに対してバイパスを有効に**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="f05d9-129">非マッピングサイトに対してバイパスを有効にすると、すべてのサイトに関連付けられているすべてのサブネットを指定する必要がなく、ブランチサイトに関連付けられているサブネットのみを指定しているため、構成が効率化されます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="f05d9-130">CAC が有効になっている場合は、[**非マッピングサイトに対してバイパスを有効に**する] チェックボックスをオンにしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="f05d9-131">[**コミット**] をクリックして変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="f05d9-131">Click **Commit** to save your changes.</span></span>


## <a name="disable-network-media-bypass"></a><span data-ttu-id="f05d9-132">ネットワークメディアのバイパスを無効にする</span><span class="sxs-lookup"><span data-stu-id="f05d9-132">Disable network media bypass</span></span>

<span data-ttu-id="f05d9-133">メディアバイパスの設定は、Skype for Business Server の展開でグローバルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-133">Media bypass settings apply globally across a Skype for Business Server deployment.</span></span> <span data-ttu-id="f05d9-134">メディアのバイパスでは、仲介サーバーを経由せずに通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-134">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="f05d9-135">メディアのバイパスを使用する場合について詳しくは、「[メディアバイパスの計画](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f05d9-135">For details about when to use Media bypass, see [Plan for media bypass](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span> <span data-ttu-id="f05d9-136">Skype for Business Server コントロールパネルからメディアのバイパスを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-136">You can disable media bypass from the Skype for Business Server Control Panel.</span></span> 


### <a name="to-disable-media-bypass"></a><span data-ttu-id="f05d9-137">メディアのバイパスを無効にするには</span><span class="sxs-lookup"><span data-stu-id="f05d9-137">To disable media bypass</span></span>

1.  <span data-ttu-id="f05d9-138">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-138">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f05d9-139">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f05d9-139">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f05d9-140">左側のナビゲーションバーで [**ネットワーク構成**] をクリックし、[**グローバル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-140">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="f05d9-141">[**グローバル**] ページで、[**グローバル**構成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-141">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="f05d9-142">構成は常に1つだけであり、常に Global という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="f05d9-142">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="f05d9-143">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-143">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="f05d9-144">[**グローバル設定の編集**] ページで、[**メディアバイパスを有効にする**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="f05d9-144">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="f05d9-145">[**コミット**] をクリックして変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="f05d9-145">Click **Commit** to save your changes.</span></span>

  
