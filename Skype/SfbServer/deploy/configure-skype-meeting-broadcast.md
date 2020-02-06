---
title: Skype 会議ブロードキャストを使用できるようにオンプレミス展開を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '概要: オンプレミスの Skype for Business Server ハイブリッド展開用に Skype 会議ブロードキャストを構成するために実行する必要のある手順について説明します。'
ms.openlocfilehash: 8bdbb163f5ef867711ce109bc923ba0ec8401ffa
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790945"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="eb940-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="eb940-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="eb940-104">**概要:** オンプレミスの Skype for Business Server ハイブリッド展開用に Skype 会議ブロードキャストを構成するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb940-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="eb940-105">Skype 会議ブロードキャストは、Office 365 の一部であるオンラインサービスです。</span><span class="sxs-lookup"><span data-stu-id="eb940-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="eb940-106">Skype for Business Server をオンプレミスで実行していて、環境で Skype 会議ブロードキャストを使用する場合は、このトピックの構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb940-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="eb940-107">始める前に、お客様の環境が Skype for Business Online とのハイブリッド用に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb940-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="eb940-108">詳細については、「[Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」、および「[Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb940-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="eb940-109">Skype 会議ブロードキャストのハイブリッド環境を構成する</span><span class="sxs-lookup"><span data-stu-id="eb940-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="eb940-110">Skype 会議ブロードキャストの環境を準備するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb940-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="eb940-111">Skype for Business Online のリソースとのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="eb940-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="eb940-112">SIP フェデレーション ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="eb940-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="eb940-113">Skype for Business Online のリソースとのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="eb940-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="eb940-114">Skype for Business Online のリソースとのフェデレーションを有効にするには、SIP フェデレーションプロバイダーの外部アクセスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb940-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="eb940-115">Skype for Business Server コントロールパネルを使用してこれを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eb940-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="eb940-116">Skype for Business Server コントロールパネルを起動し、左側の [**外部アクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb940-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="eb940-117">[**SIP フェデレーション プロバイダー**] を選択し、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb940-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="eb940-118">次の設定を使用して新しいプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="eb940-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="eb940-119">**このプロバイダーとの通信を有効にする:**</span><span class="sxs-lookup"><span data-stu-id="eb940-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="eb940-120">オン</span><span class="sxs-lookup"><span data-stu-id="eb940-120">Selected</span></span>  <br/> |
|<span data-ttu-id="eb940-121">**[プロバイダー名]:**</span><span class="sxs-lookup"><span data-stu-id="eb940-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="eb940-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="eb940-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="eb940-123">**[アクセス エッジ サービス (FQDN)]:**</span><span class="sxs-lookup"><span data-stu-id="eb940-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="eb940-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb940-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="eb940-125">**[既定の確認レベル]:**</span><span class="sxs-lookup"><span data-stu-id="eb940-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="eb940-126">このプロバイダーを使うすべてのユーザーとの通信を許可する</span><span class="sxs-lookup"><span data-stu-id="eb940-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="eb940-127">Skype for Business Server 管理シェルで次のコマンドレットを実行して、Skype for business Online のリソースとのフェデレーションを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="eb940-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="eb940-128">SIP フェデレーション ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="eb940-128">Configure SIP federated domains</span></span>

<span data-ttu-id="eb940-129">次に、SIP フェデレーションドメインを許可ドメインリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb940-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="eb940-130">一覧にある 4 つのドメインのそれぞれに対して以下の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb940-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="eb940-131">これらのドメインは、Skype for Business Online で使用される地域データセンターのために用意されています。</span><span class="sxs-lookup"><span data-stu-id="eb940-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="eb940-132">Skype for Business Server コントロールパネルを起動し、左側の [**外部アクセス**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb940-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="eb940-133">[**SIP フェデレーション ドメイン**] を選択し、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb940-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="eb940-134">[**ドメイン名 (または FQDN):**] にはドメインを入力し、以下の各ドメインにこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb940-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="eb940-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb940-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="eb940-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb940-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="eb940-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb940-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="eb940-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="eb940-138">resources.lync.com</span></span>
    
<span data-ttu-id="eb940-139">また、Skype for Business Server 管理シェルで次のコマンドレットを実行して、SIP フェデレーションドメインの外部アクセスを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="eb940-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="eb940-140">これらの構成手順が完了したら、展開で Skype 会議ブロードキャストを使い始めることができます。</span><span class="sxs-lookup"><span data-stu-id="eb940-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="eb940-141">Skype 会議ブロードキャストの詳細については、「 [Skype 会議ブロードキャストとは](https://go.microsoft.com/fwlink/?LinkId=617071)」および「 [Skype 会議ブロードキャスト管理者ガイド](https://go.microsoft.com/fwlink/?LinkId=617075)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb940-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

