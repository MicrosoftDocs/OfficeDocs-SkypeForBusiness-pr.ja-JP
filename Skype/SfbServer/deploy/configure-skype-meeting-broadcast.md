---
title: Skype 会議ブロードキャストを使用できるようにオンプレミス展開を構成する
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '概要: は、ハイブリッド展開のビジネスのサーバーの設置型の Skype の Skype 会議のブロードキャストを構成するのには実行する必要がある手順について説明します。'
ms.openlocfilehash: 09b99cab45b8832be34a3219a222324d199c5195
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069470"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="dcd72-103">Configure your on-premises deployment for Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="dcd72-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="dcd72-104">**の概要:** 設置型の Skype ビジネス サーバー ハイブリッド展開用の Skype 会議のブロードキャストを構成するために実行する必要がある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="dcd72-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="dcd72-105">Skype 会議のブロードキャストは、Office 365 の一部であるオンライン サービスです。</span><span class="sxs-lookup"><span data-stu-id="dcd72-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="dcd72-106">ビジネス サーバー設置型の Skype を実行している環境で Skype 会議のブロードキャストを使用する場合は、このトピックで構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd72-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="dcd72-107">作業を開始する前に、環境をビジネス オンラインの Skype でのハイブリッドを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd72-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="dcd72-108">詳細については、「[Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」、および「[Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcd72-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="dcd72-109">Skype 会議のブロードキャストに、ハイブリッド環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="dcd72-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="dcd72-110">Skype 会議をブロードキャストするため、環境を準備するのには次の操作をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd72-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="dcd72-111">Skype でのビジネスのオンライン リソースのフェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="dcd72-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="dcd72-112">SIP フェデレーション ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="dcd72-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="dcd72-113">Skype でのビジネスのオンライン リソースのフェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="dcd72-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="dcd72-114">Skype でのビジネスのオンライン リソースのフェデレーションを有効にするには、SIP フェデレーション プロバイダーの外部アクセスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd72-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="dcd72-115">このビジネス サーバーのコントロール パネルの Skype を使用して以下の手順。</span><span class="sxs-lookup"><span data-stu-id="dcd72-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="dcd72-116">ビジネス サーバーのコントロール パネルの Skype を起動し、左上の**外部からのアクセス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="dcd72-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="dcd72-117">[**SIP フェデレーション プロバイダー**] を選択し、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcd72-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="dcd72-118">次の設定を使用して新しいプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="dcd72-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="dcd72-119">**このプロバイダーとの通信を有効にします。**</span><span class="sxs-lookup"><span data-stu-id="dcd72-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="dcd72-120">オン</span><span class="sxs-lookup"><span data-stu-id="dcd72-120">Selected</span></span>  <br/> |
|<span data-ttu-id="dcd72-121">**[プロバイダー名]:**</span><span class="sxs-lookup"><span data-stu-id="dcd72-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="dcd72-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="dcd72-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="dcd72-123">**[アクセス エッジ サービス (FQDN)]:**</span><span class="sxs-lookup"><span data-stu-id="dcd72-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="dcd72-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="dcd72-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="dcd72-125">**[既定の確認レベル]:**</span><span class="sxs-lookup"><span data-stu-id="dcd72-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="dcd72-126">このプロバイダーを使うすべてのユーザーとの通信を許可する</span><span class="sxs-lookup"><span data-stu-id="dcd72-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="dcd72-127">また、Skype でビジネス サーバー管理シェルの次のコマンドレットを実行して、Skype でのビジネスのオンライン リソースのフェデレーションを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="dcd72-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="dcd72-128">SIP フェデレーション ドメインを構成する</span><span class="sxs-lookup"><span data-stu-id="dcd72-128">Configure SIP federated domains</span></span>

<span data-ttu-id="dcd72-129">次に、フェデレーションする SIP ドメインを許可されているドメイン一覧に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcd72-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="dcd72-130">一覧にある 4 つのドメインのそれぞれに対して以下の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dcd72-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="dcd72-131">これらのドメインは、地域のデータのオンライン ビジネスで使用されている Skype を中央揃えにします。</span><span class="sxs-lookup"><span data-stu-id="dcd72-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="dcd72-132">ビジネス サーバーのコントロール パネルの Skype を起動し、左上の**外部からのアクセス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="dcd72-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="dcd72-133">[**SIP フェデレーション ドメイン**] を選択し、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcd72-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="dcd72-134">[**ドメイン名 (または FQDN):**] にはドメインを入力し、以下の各ドメインにこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dcd72-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="dcd72-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="dcd72-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="dcd72-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="dcd72-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="dcd72-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="dcd72-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="dcd72-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="dcd72-138">resources.lync.com</span></span>
    
<span data-ttu-id="dcd72-139">Skype でビジネス サーバー管理シェルの次のコマンドレットを実行して、フェデレーションする SIP ドメインの外部アクセスを構成することも。</span><span class="sxs-lookup"><span data-stu-id="dcd72-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="dcd72-140">構成手順を完了したら、環境で Skype 会議のブロードキャストを使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="dcd72-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="dcd72-141">Skype 会議のブロードキャストの詳細についてを参照してください[Skype の会議のブロードキャストとは何ですか?](https://go.microsoft.com/fwlink/?LinkId=617071)と[Skype 会議のブロードキャスト管理者ガイド](https://go.microsoft.com/fwlink/?LinkId=617075)です。</span><span class="sxs-lookup"><span data-stu-id="dcd72-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

