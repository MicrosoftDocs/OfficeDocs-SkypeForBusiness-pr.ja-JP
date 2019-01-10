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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: ビジネス オンライン スケジュール、生産、およびブロードキャストの会議、またはイベントを 10,000 の出席者に大規模なオンライン ユーザーを対象にできるようにするには、Skype の Skype 会議のブロードキャスト機能について説明します。
ms.openlocfilehash: b29ec51ddcb672f6727f7bc43958872962245ebb
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2019
ms.locfileid: "27788977"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="ceedb-103">Skype 会議ブロードキャスト用にネットワークをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ceedb-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="ceedb-104">Skype 会議のブロードキャストの[Skype 会議のブロードキャストを有効に](enable-skype-meeting-broadcast.md)した後、ネットワークを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceedb-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="ceedb-105">人、組織外からのウェビナー、他のブロードキャストを保持したい場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ceedb-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="ceedb-106">ファイアウォールの構成に慣れていない場合は、[マイクロソフトのパートナー](https://go.microsoft.com/fwlink/?linkid=391089)に依頼してこの手順を実行することを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="ceedb-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="ceedb-107">この手順を省略し、代わりに、ブロードキャストに招待するため、フェデレーションに別のビジネスを追加、[ビジネス ユーザー向けの外部の Skype に連絡を許可する](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ceedb-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="ceedb-108">手順 1: を許可するドメインを設定します。</span><span class="sxs-lookup"><span data-stu-id="ceedb-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="ceedb-109">許可するドメインを設定するには、 **1 つ**の次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="ceedb-109">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="ceedb-110">**方法 1: Office 365 の管理ページを使用します。**</span><span class="sxs-lookup"><span data-stu-id="ceedb-110">**Method 1: Use the Office 365 admin center**</span></span>

1. <span data-ttu-id="ceedb-111">**Office 365 管理センター**に移動し、左側のナビゲーションでは、[**設定**] をクリックして > **サービス&amp;アドイン**、し、**ビジネスの Skype**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceedb-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="ceedb-112">[**ドメインの例外**の下にある**外部の共有**] ページ**を除くすべてのドメインがブロックされます**がを選択し、コンマ (,) で、次のドメインを入力してください。</span><span class="sxs-lookup"><span data-stu-id="ceedb-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="ceedb-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ceedb-113">noammeetings.lync.com</span></span>

   - <span data-ttu-id="ceedb-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ceedb-114">emeameetings.lync.com</span></span>

   - <span data-ttu-id="ceedb-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="ceedb-115">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="ceedb-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="ceedb-116">resources.lync.com</span></span>

3. <span data-ttu-id="ceedb-117">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ceedb-117">Click **Save**.</span></span>

## #

 <span data-ttu-id="ceedb-118">**方法 2: Windows PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="ceedb-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="ceedb-119">[**スタート] メニュー**から**Windows PowerShell**を右クリックし、**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ceedb-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="ceedb-120">**Windows PowerShell**ウィンドウで、各明細行を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ceedb-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="ceedb-121">手順 2: 追加の Skype 会議のブロードキャスト ドメイン、Url、および IP アドレス</span><span class="sxs-lookup"><span data-stu-id="ceedb-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="ceedb-122">セットアップ プロセスでは、2 番目の手順では、まず必要し、し、IP アドレスと動作する Skype 会議のブロードキャストに必要な Url を追加するドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="ceedb-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="ceedb-123">**オンライン ビジネスのエンドポイントの Url に必要な Skype を追加しどれを見ることによって IP アドレスが必要**[ここで](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)ください。</span><span class="sxs-lookup"><span data-stu-id="ceedb-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="ceedb-124">ハイブリッド展開および組織で Skype 会議のブロードキャストを設定します。</span><span class="sxs-lookup"><span data-stu-id="ceedb-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="ceedb-125">場合は、他のセットアップで実行する必要がありますが、オンライン ビジネスの組織と、設置型展開の Lync Server 2010、Microsoft Lync Server 2013、および Skype、Skype ビジネス サーバー 2015 のとオンライン両方のユーザーが存在している設置ビジネス オンラインの Skype で通信し、Skype の会議のブロードキャストに参加するすべてのユーザーを許可する設置型の組織を有効にするのには、上記に追加します。</span><span class="sxs-lookup"><span data-stu-id="ceedb-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="ceedb-126">それらの要件とはどのようなものを表示するには、 [Skype 会議のブロードキャスト用の設置型展開の構成](https://go.microsoft.com/fwlink/?LinkId=617070)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceedb-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ceedb-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ceedb-127">Related topics</span></span>

[<span data-ttu-id="ceedb-128">Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="ceedb-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="ceedb-129">Office 365 URL および IP アドレス範囲</span><span class="sxs-lookup"><span data-stu-id="ceedb-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="ceedb-130">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="ceedb-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



