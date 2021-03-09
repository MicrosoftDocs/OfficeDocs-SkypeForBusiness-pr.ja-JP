---
title: Skype for Business ハイブリッドの構成
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '概要: オンプレミス展開と Skype for Business Online の間の相互運用性を構成する方法について説明します。'
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569219"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="57e8f-103">Skype for Business ハイブリッドの構成</span><span class="sxs-lookup"><span data-stu-id="57e8f-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="57e8f-104">Skype for Business ハイブリッドを構成するには、次のことを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57e8f-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="57e8f-105">[Microsoft 365 または Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)とフェデレーションするために、オンプレミスエッジ サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="57e8f-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="57e8f-106">[Microsoft 365 または Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)を信頼し、共有 SIP アドレス空間を有効にOfficeオンプレミス環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="57e8f-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="57e8f-107">[Microsoft 365 または 365](#enable-shared-sip-address-space-in-your-organization)組織で共有 SIP Officeを有効にします。</span><span class="sxs-lookup"><span data-stu-id="57e8f-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="57e8f-108">Exchange がオンプレミスの場合は、Exchange オンプレミス環境と Skype for Business Online 環境の間で OAuth を構成できます。</span><span class="sxs-lookup"><span data-stu-id="57e8f-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="57e8f-109">詳細については  [、「Manage server-to-server authentication in Skype for Business Server」および「Plan to](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) [integrate Skype for Business and Exchange」を参照してください](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="57e8f-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="57e8f-110">Microsoft 365 または Office 365 とのフェデレーションを行うオンプレミスエッジ サービスを構成する</span><span class="sxs-lookup"><span data-stu-id="57e8f-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="57e8f-111">フェデレーションを使用すると、オンプレミス展開のユーザーは、組織内の Microsoft 365 Office 365 ユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="57e8f-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="57e8f-112">フェデレーションを構成するには、Skype for Business Server 管理シェルで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="57e8f-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="57e8f-113">'-EnablePartnerDiscovery' の値が $True に設定されている場合、Skype for Business Server は DNS レコードを使用して、AllowedDomains リストに記載されていないパートナー ドメインを試して検出します。</span><span class="sxs-lookup"><span data-stu-id="57e8f-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="57e8f-114">値が [ドメイン] に$False場合、Skype for Business Server は AllowedDomains リストにあるドメインとのみフェデレーションします。</span><span class="sxs-lookup"><span data-stu-id="57e8f-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="57e8f-115">DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="57e8f-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="57e8f-116">オンプレミスの Skype for Business 展開のユーザーと Skype for Business Online 組織のユーザー間のフェデレーションを有効にする方法の詳細については、「Skype for Business Server での [Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)顧客のフェデレーション サポートの構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57e8f-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="57e8f-117">Microsoft 365 または Microsoft 365 または 365 で共有 SIP アドレス空間を有効にOfficeする</span><span class="sxs-lookup"><span data-stu-id="57e8f-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="57e8f-118">また、Microsoft 365 または 365 を信頼し、共有 SIP アドレス空間を有効Officeオンプレミス環境を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57e8f-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="57e8f-119">つまり、Microsoft 365 または Office 365 は、オンプレミス環境と同じ一連の SIP ドメインのユーザー アカウントをホストする可能性があります。また、メッセージはオンプレミスとオンラインでホストされているユーザー間でルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="57e8f-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="57e8f-120">これを行うには、以下で説明するように ProxyFqdn=sipfed.online.lync.com を使用してホスティング プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="57e8f-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="57e8f-121">まず、ProxyFqdn=sipfed.online.lync.com のホスティング プロバイダーが既にあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="57e8f-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="57e8f-122">存在する場合は、次のコマンドを使用して削除します。</span><span class="sxs-lookup"><span data-stu-id="57e8f-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="57e8f-123">次に、新しいホスティング プロバイダーを作成し、次のように New-CsHostingProviderコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="57e8f-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="57e8f-124">組織内の共有 SIP アドレス空間を有効にする</span><span class="sxs-lookup"><span data-stu-id="57e8f-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="57e8f-125">オンプレミス展開で行った変更に加えて、Microsoft 365 または Office 365 組織で対応する変更を行い、オンプレミス展開で共有 SIP アドレス空間を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="57e8f-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="57e8f-126">組織内の共有 SIP アドレス空間を有効にするには、Skype for Business Online でリモート PowerShell セッションを確立し、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="57e8f-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="57e8f-127">SharedSipAddressSpace 属性は、オンラインに移行するまで "True" に維持する必要があります。ユーザーはオンプレミスのままではありません。</span><span class="sxs-lookup"><span data-stu-id="57e8f-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="57e8f-128">Teams または Skype for Business Online とのリモート PowerShell セッションを確立するには、まず [Teams PowerShell モジュールをインストールする必要があります](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="57e8f-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
  
<span data-ttu-id="57e8f-129">モジュールをインストールした後、次のコマンドレットを使用してリモート セッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="57e8f-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="57e8f-130">Skype for Business Online でリモート PowerShell セッションを確立する方法、および Skype for Business Online Connector モジュールを使用する方法の詳細については、「Set up your computer for Windows PowerShell」を参照 [してください](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="57e8f-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="57e8f-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="57e8f-131">See also</span></span>

[<span data-ttu-id="57e8f-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="57e8f-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
