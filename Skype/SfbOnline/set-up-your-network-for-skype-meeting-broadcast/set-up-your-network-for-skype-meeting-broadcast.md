---
title: "Skype 会議メディアのネットワークをセットアップします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: "For Business Online できるようにするには、スケジュール、作成、ブロードキャスト会議またはイベントをオンライン参加者に向けた最高 10,000 人の Skype の Skype 会議メディアの機能について説明します。"
ms.openlocfilehash: 9dab3a7e74b9f69a3df6bd06c3ad868d109343fe
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="89477-103">Skype 会議メディアのネットワークをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="89477-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="89477-p101">Skype 会議メディアの[Skype 会議メディアを有効に](enable-skype-meeting-broadcast.md)した後に、ネットワークを構成する必要があります。組織外のユーザーのウェビナーとその他のブロードキャストを保持する場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="89477-p101">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network. Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>
  
<span data-ttu-id="89477-106">ファイアウォールの設定に経験豊富な場合は、この手順を行うには[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)を雇うを検討してください。</span><span class="sxs-lookup"><span data-stu-id="89477-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="89477-107">この手順をスキップして、代わりに、それらをブロードキャストに招待できるように、フェデレーションを別のビジネスを追加、[ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="89477-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>
  
## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="89477-108">手順 1: 許可ドメインを設定します。</span><span class="sxs-lookup"><span data-stu-id="89477-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="89477-109">許可ドメインを設定するには、 **1 つ**の次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="89477-109">Use **one** of the following methods to set up allowed domains:</span></span>
  
### 

 <span data-ttu-id="89477-110">**方法 1: Office 365 管理センターを使用します。**</span><span class="sxs-lookup"><span data-stu-id="89477-110">**Method 1: Use the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="89477-111">**Office 365 管理センター**に移動し、左側のナビゲーションで [**設定**] をクリックして > **サービス&amp;アドイン**、[ **Skype for Business**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="89477-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>
    
2. <span data-ttu-id="89477-112">[**外部共有**] ページの [**ドメインの例外****を除くすべてのドメインがブロック**を選択し、[コンマ (,) で、次のドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="89477-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>
    
  - <span data-ttu-id="89477-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="89477-113">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="89477-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="89477-114">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="89477-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="89477-115">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="89477-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="89477-116">resources.lync.com</span></span>
    
3. <span data-ttu-id="89477-117">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="89477-117">Click **Save**.</span></span>
    
### 

 <span data-ttu-id="89477-118">**方法 2: Windows PowerShell を使用します。**</span><span class="sxs-lookup"><span data-stu-id="89477-118">**Method 2: Use Windows PowerShell**</span></span>
  
- <span data-ttu-id="89477-p102">**[スタート] メニュー**で、 **Windows PowerShell**を右クリックし、[**管理者として実行**] をクリックします。**Windows PowerShell**ウィンドウで、それぞれの行を入力し、[Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="89477-p102">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**. In the **Windows PowerShell** window, type each line and press Enter.</span></span>
    
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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="89477-121">手順 2: 追加の Skype 会議メディア ドメインの Url と IP アドレス</span><span class="sxs-lookup"><span data-stu-id="89477-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="89477-122">セットアップ中に、2 番目の手順では、最初に必要なし、IP アドレスと Url を操作する Skype 会議メディアに必要な追加のドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="89477-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>
  
- <span data-ttu-id="89477-123">**必要な Skype for Business Online のエンドポイントの Url を追加してどのプレゼンスを表示して IP アドレスが必要な**[次のとおり](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)です。</span><span class="sxs-lookup"><span data-stu-id="89477-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required**[here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="89477-124">ハイブリッド展開や組織で Skype 会議メディアを設定します。</span><span class="sxs-lookup"><span data-stu-id="89477-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="89477-p103">場合はで実行する必要がありますその他のセットアップ手順、Skype for Business Online の組織とを設置型の Lync Server 2010、Microsoft Lync Server 2013 では、Skype for Business Server 2015 とオンライン ユーザーの両方があるがあり内部設置型。Skype for Business Online 通信を許可するすべてのユーザーを作成し、[Skype 会議メディアに参加できるように、内部設置型の組織を有効にするのには、上記に追加します。このような要件とは何を表示するには、 [Skype 会議メディアのオンプレミス展開の構成](https://go.microsoft.com/fwlink/?LinkId=617070)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89477-p103">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all of your users to be able to create and join a Skype Meeting Broadcast. To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="89477-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="89477-127">Related topics</span></span>

[<span data-ttu-id="89477-128">Skype 会議メディアを有効にします。</span><span class="sxs-lookup"><span data-stu-id="89477-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)
  
[<span data-ttu-id="89477-129">Office 365 の Url と IP アドレス範囲</span><span class="sxs-lookup"><span data-stu-id="89477-129">Office 365 URLs and IP address ranges</span></span>](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="89477-130">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="89477-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

