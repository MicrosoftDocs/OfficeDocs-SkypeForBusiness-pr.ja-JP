---
title: Skype 会議ブロードキャスト用にネットワークをセットアップする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Skype for Business Online の Skype 会議ブロードキャスト機能について学習します。この機能を使用すると、最大 10,000 人のオンライン ユーザーに会議やイベントをスケジュール、作成、ブロードキャストできます。
ms.openlocfilehash: da27110313765bb50df92e3bafb6f09ceae5f301
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237553"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="ed11e-103">Skype 会議ブロードキャスト用にネットワークをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ed11e-103">Set up your network for Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="ed11e-104">[会議[ブロードキャスト] Skypeを有効Skype、](enable-skype-meeting-broadcast.md)ネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed11e-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="ed11e-105">社外のユーザー向けウェビナーや他のブロードキャストを開催する場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ed11e-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ed11e-106">Skype for Businessオンラインは 2021 年 7 月 31 日に廃止され、その時点でサービスへのアクセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="ed11e-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="ed11e-107">お客様には、コミュニケーションとチームワークの中核となるMicrosoft Teamsクライアントであるクライアントへのアップグレードを開始Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ed11e-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="ed11e-108">ファイアウォールを構成する経験が十分でない場合は [、Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) パートナーを採用してこの手順を実行することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="ed11e-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="ed11e-109">この手順をスキップし、代わりにフェデレーションに別のビジネスを追加してブロードキャストに招待するには、「ユーザーが外部のユーザーに連絡することを許可する」の手順に従Skype for Business[します](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="ed11e-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="ed11e-110">手順 1: 許可されているドメインを設定する</span><span class="sxs-lookup"><span data-stu-id="ed11e-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="ed11e-111">次 **のいずれかの** 方法を使用して、許可されているドメインを設定します。</span><span class="sxs-lookup"><span data-stu-id="ed11e-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="ed11e-112">**方法 1: 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="ed11e-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="ed11e-113">管理センターに移動し、左側のナビゲーションで [設定Services アドイン] をクリックし、[Skype for Business]  >  **&amp;\*\*\*\*を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ed11e-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="ed11e-114">[**ドメインの例外**]の [外部共有] ページで、[すべてのドメインがブロックされます] を選択し、次のドメインをコンマ (,) で区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="ed11e-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="ed11e-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ed11e-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="ed11e-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ed11e-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="ed11e-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ed11e-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="ed11e-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="ed11e-118">resources.lync.com</span></span>

3. <span data-ttu-id="ed11e-119">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed11e-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="ed11e-120">**方法 2: Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ed11e-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="ed11e-121">[スタート]**メニューの [** ファイル名] を右 **クリックWindows PowerShell** 管理者として **実行] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ed11e-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="ed11e-122">このウィンドウ **Windows PowerShell、** 各行を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ed11e-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="ed11e-123">手順 2: 会議Skype、URL、IP アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="ed11e-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="ed11e-124">セットアップ プロセスの 2 番目の手順では、最初に必要なドメインを追加してから、Skype 会議ブロードキャストを機能するために必要な IP アドレスと URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="ed11e-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="ed11e-125">**必要なエンドポイント URL Skype for Business IP** アドレスを追加するには、 で必要な URL を確認 [します](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。</span><span class="sxs-lookup"><span data-stu-id="ed11e-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="ed11e-126">ハイブリッド展開Skype組織で会議ブロードキャストをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ed11e-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="ed11e-127">Skype for Business Online 組織と Lync Server 2010、Microsoft Lync Server 2013、および Skype for Business Server 2015 のオンプレミス展開を使用し、オンラインとオンプレミスの両方のユーザーを持っている場合は、オンプレミスの組織が Skype for Business Online と通信し、すべてのユーザーが Skype 会議ブロードキャストに参加するために、上記の手順に加えて必要なセットアップ手順もあります。</span><span class="sxs-lookup"><span data-stu-id="ed11e-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="ed11e-128">これらの要件を確認するには、「会議ブロードキャスト用にオンプレミスデプロイを構成[するSkype参照してください](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="ed11e-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed11e-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed11e-129">Related topics</span></span>

[<span data-ttu-id="ed11e-130">Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="ed11e-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="ed11e-131">Office 365 URL および IP アドレス範囲</span><span class="sxs-lookup"><span data-stu-id="ed11e-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="ed11e-132">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="ed11e-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
