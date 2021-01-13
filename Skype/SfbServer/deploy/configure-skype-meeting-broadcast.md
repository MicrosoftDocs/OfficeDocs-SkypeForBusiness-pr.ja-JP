---
title: Skype 会議ブロードキャストのオンプレミス展開を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: オンプレミスの Skype for Business Server ハイブリッド展開用に Skype 会議ブロードキャストを構成するために実行する必要がある手順について説明します。'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820707"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="0c7ca-103">Skype 会議ブロードキャストのオンプレミス展開を構成する</span><span class="sxs-lookup"><span data-stu-id="0c7ca-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="0c7ca-104">**概要:** オンプレミスの Skype for Business Server ハイブリッド展開用に Skype 会議ブロードキャストを構成するために実行する必要がある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="0c7ca-105">Skype 会議ブロードキャストは、Office 365 の一部です。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="0c7ca-106">Skype for Business Server をオンプレミスで実行し、環境で Skype 会議ブロードキャストを使用する場合は、このトピックの構成手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="0c7ca-107">開始する前に、環境を Skype for Business Online とのハイブリッド用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="0c7ca-108">詳細については [、「Skype for Business Server](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) と Skype for Business Online 間のハイブリッド接続を計画する」および [「Skype for Business Server](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)と Skype for Business Online 間のハイブリッド接続を展開する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="0c7ca-109">Skype 会議ブロードキャストのハイブリッド環境を構成する</span><span class="sxs-lookup"><span data-stu-id="0c7ca-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="0c7ca-110">Skype 会議ブロードキャストの環境を準備するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="0c7ca-111">Skype for Business Online リソースとのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="0c7ca-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="0c7ca-112">SIP フェデレーション ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="0c7ca-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="0c7ca-113">Skype for Business Online リソースとのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="0c7ca-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="0c7ca-114">Skype for Business Online リソースとのフェデレーションを有効にするには、SIP フェデレーション プロバイダーの外部アクセスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="0c7ca-115">Skype for Business Server コントロール パネルを使用してこれを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="0c7ca-116">Skype for Business Server コントロール パネルを起動し、左側の **[外部アクセス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="0c7ca-117">**[SIP フェデレーション プロバイダー] を選択し、[新規**] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="0c7ca-118">次の設定で新しいプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="0c7ca-119">**このプロバイダーとの通信を有効にする:**</span><span class="sxs-lookup"><span data-stu-id="0c7ca-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="0c7ca-120">選択済み</span><span class="sxs-lookup"><span data-stu-id="0c7ca-120">Selected</span></span>  <br/> |
|<span data-ttu-id="0c7ca-121">**プロバイダー名:**</span><span class="sxs-lookup"><span data-stu-id="0c7ca-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="0c7ca-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="0c7ca-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="0c7ca-123">**アクセス エッジ サービス (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="0c7ca-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="0c7ca-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c7ca-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="0c7ca-125">**既定の検証レベル:**</span><span class="sxs-lookup"><span data-stu-id="0c7ca-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="0c7ca-126">ユーザーがこのプロバイダーを使用してすべてのユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="0c7ca-127">Skype for Business Server 管理シェルで次のコマンドレットを実行して、Skype for Business Online リソースとのフェデレーションを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="0c7ca-128">SIP フェデレーション ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="0c7ca-128">Configure SIP federated domains</span></span>

<span data-ttu-id="0c7ca-129">次に、SIP フェデレーション ドメインを許可されたドメインの一覧に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="0c7ca-130">リストされている各ドメインに対してこれらの手順を繰り返し、4 つの新しい SIP フェデレーション ドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="0c7ca-131">これらのドメインには、Skype for Business Online で使用される地域データ センターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="0c7ca-132">Skype for Business Server コントロール パネルを起動し、左側の **[外部アクセス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="0c7ca-133">**[SIP フェデレーション ドメイン] を選択し、[新規**] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="0c7ca-134">ドメイン名 **(または FQDN)** にドメインを入力し、次の各ドメインに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="0c7ca-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c7ca-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="0c7ca-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c7ca-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="0c7ca-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c7ca-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="0c7ca-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="0c7ca-138">resources.lync.com</span></span>
    
<span data-ttu-id="0c7ca-139">Skype for Business Server 管理シェルで次のコマンドレットを実行して、SIP フェデレーション ドメインの外部アクセスを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="0c7ca-140">これらの構成手順を完了すると、展開で Skype 会議ブロードキャストの使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="0c7ca-141">Skype 会議ブロードキャストの詳細については [、「Skype](https://go.microsoft.com/fwlink/?LinkId=617071) 会議ブロードキャストとは」および「Skype 会議ブロードキャスト管理ガイド」 [を参照してください](https://go.microsoft.com/fwlink/?LinkId=617075)。</span><span class="sxs-lookup"><span data-stu-id="0c7ca-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

