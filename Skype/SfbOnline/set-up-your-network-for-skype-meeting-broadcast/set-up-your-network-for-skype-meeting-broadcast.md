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
f1keywords: None
ms.custom:
- SMB
description: Skype for Business Online の Skype 会議ブロードキャスト機能について説明します。この機能を使用すると、最大1万人までの会議やイベントのスケジュール、作成、ブロードキャストを行うことができます。
ms.openlocfilehash: 443810772eeb8bf11721825b06b6a87ccb2c97c8
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792922"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="22c1e-103">Skype 会議ブロードキャスト用にネットワークをセットアップする</span><span class="sxs-lookup"><span data-stu-id="22c1e-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="22c1e-104">Skype[会議ブロードキャスト](enable-skype-meeting-broadcast.md)の Skype 会議ブロードキャストを有効にしたら、ネットワークを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22c1e-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="22c1e-105">社外の人に対して、ウェビナーやその他のブロードキャストを保留にする場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="22c1e-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="22c1e-106">ファイアウォールの設定が整っていない場合は、この手順を実行するために[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を採用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="22c1e-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="22c1e-107">この手順をスキップして、別のビジネスをフェデレーションに追加して、ブロードキャストに招待できるようにするには、「[ユーザーが外部の Skype For business ユーザーに連絡](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)できるようにする」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="22c1e-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="22c1e-108">手順 1: 許可したドメインをセットアップする</span><span class="sxs-lookup"><span data-stu-id="22c1e-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="22c1e-109">許可したドメインをセットアップするには、次の**いずれか**の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="22c1e-109">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="22c1e-110">**方法 1: 管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="22c1e-110">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="22c1e-111">管理センターに移動し、左のナビゲーションで [**設定** > **サービス&amp;アドイン**] をクリックして、[ **Skype for business**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="22c1e-111">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="22c1e-112">[**外部共有**] ページの [**ドメインの例外**] で、[すべてのドメインを**ブロックする**] を選択し、次のドメインをカンマ (,) で区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="22c1e-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="22c1e-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="22c1e-113">noammeetings.lync.com</span></span>

   - <span data-ttu-id="22c1e-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="22c1e-114">emeameetings.lync.com</span></span>

   - <span data-ttu-id="22c1e-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="22c1e-115">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="22c1e-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="22c1e-116">resources.lync.com</span></span>

3. <span data-ttu-id="22c1e-117">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22c1e-117">Click **Save**.</span></span>

## #

 <span data-ttu-id="22c1e-118">**方法 2: Windows PowerShell を使用する**</span><span class="sxs-lookup"><span data-stu-id="22c1e-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="22c1e-119">[**スタート] メニュー**で、[ **Windows PowerShell** ] を右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22c1e-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="22c1e-120">**Windows PowerShell**ウィンドウで、各行を入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="22c1e-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="22c1e-121">手順 2: Skype 会議ブロードキャストのドメイン、Url、IP アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="22c1e-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="22c1e-122">セットアッププロセスの2番目の手順では、最初に必要なドメインを追加してから、Skype 会議ブロードキャストを使用するために必要な IP アドレスと Url を追加します。</span><span class="sxs-lookup"><span data-stu-id="22c1e-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="22c1e-123">必要なものを確認**して、必要な Skype For Business Online エンドポイント url と IP アドレスを追加**する[こちらをご覧](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)ください。</span><span class="sxs-lookup"><span data-stu-id="22c1e-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="22c1e-124">ハイブリッド展開と組織で Skype 会議ブロードキャストをセットアップする</span><span class="sxs-lookup"><span data-stu-id="22c1e-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="22c1e-125">Skype for Business Online の組織と、Lync server 2010、Microsoft Lync Server 2013、および Skype for Business Server 2015 のオンプレミスの展開と、両方のユーザーがオンラインとオンプレミスの両方を使用している場合は、別のセットアップ手順を実行する必要があります。上のものに加えて、オンプレミスの組織が Skype for Business Online と通信できるようにし、すべてのユーザーが Skype 会議ブロードキャストに参加できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="22c1e-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="22c1e-126">これらの要件については、「 [Skype 会議ブロードキャスト用にオンプレミス展開を構成](https://go.microsoft.com/fwlink/?LinkId=617070)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22c1e-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="22c1e-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="22c1e-127">Related topics</span></span>

[<span data-ttu-id="22c1e-128">Skype 会議ブロードキャストを有効にする</span><span class="sxs-lookup"><span data-stu-id="22c1e-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="22c1e-129">Office 365 の URL と IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="22c1e-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="22c1e-130">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="22c1e-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



