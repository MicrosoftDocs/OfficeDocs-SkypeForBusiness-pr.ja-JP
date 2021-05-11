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
description: '概要: オンプレミスの展開と組織間の相互運用性を構成する方法について説明Teams。'
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305971"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="c0152-103">Skype for Business ハイブリッドの構成</span><span class="sxs-lookup"><span data-stu-id="c0152-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="c0152-104">Skype for Business ハイブリッドを構成するには、次のことを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0152-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="c0152-105">[オンプレミスのエッジ サービスを構成して、サーバーとフェデレーション](#configure-your-on-premises-edge-service-to-federate-with-teams)Teams。</span><span class="sxs-lookup"><span data-stu-id="c0152-105">[Configure your on-premises Edge service to federate with Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span></span>
- <span data-ttu-id="c0152-106">[共有 SIP アドレス空間を信頼して有効にTeamsオンプレミス環境を構成します](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)。</span><span class="sxs-lookup"><span data-stu-id="c0152-106">[Configure your on-premises environment to trust Teams and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams).</span></span>
- <span data-ttu-id="c0152-107">[組織で共有 SIP アドレス空間をTeamsします](#enable-shared-sip-address-space-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="c0152-107">[Enable shared SIP address space in your Teams organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="c0152-108">オンプレミス環境Exchange場合は、オンプレミス環境とオンライン環境の間Exchange OAuth を構成Skype for Business場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0152-108">If you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="c0152-109">詳細については、「Manage [server-to-server authentication](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) in Skype for Business Server」および「Plan to integrate Skype for Business and Exchange」 を[参照してください](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="c0152-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a><span data-ttu-id="c0152-110">オンプレミスのエッジ サービスを構成して、サーバーとフェデレーションTeams</span><span class="sxs-lookup"><span data-stu-id="c0152-110">Configure your on-premises Edge service to federate with Teams</span></span>

<span data-ttu-id="c0152-111">フェデレーションを使用すると、オンプレミス展開のユーザーは、組織内Teamsオンライン Skype for Businessと通信できます。</span><span class="sxs-lookup"><span data-stu-id="c0152-111">Federation allows users in your on-premises deployment to communicate with Teams and Skype for Business Online  users in your organization.</span></span> <span data-ttu-id="c0152-112">フェデレーションを構成するには、管理シェルで次のコマンドレットSkype for Business Server実行します。</span><span class="sxs-lookup"><span data-stu-id="c0152-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="c0152-113">'-EnablePartnerDiscovery' の値が $True に設定されている場合、Skype for Business Server は DNS レコードを使用して、AllowedDomains リストに記載されていないパートナー ドメインを試して検出します。</span><span class="sxs-lookup"><span data-stu-id="c0152-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="c0152-114">値を [許可] に設定$False、Skype for Business Server AllowedDomains リストにあるドメインとのみフェデレーションします。</span><span class="sxs-lookup"><span data-stu-id="c0152-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="c0152-115">DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="c0152-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="c0152-116">オンプレミス Skype for Business 展開のユーザーと Microsoft 365 組織のユーザーとのフェデレーションを有効にする方法の詳細については、「Skype for Business Server での Microsoft 365 顧客のフェデレーション サポートの構成」[を参照してください](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)。</span><span class="sxs-lookup"><span data-stu-id="c0152-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Microsoft 365 organization, see [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a><span data-ttu-id="c0152-117">オンプレミス環境を構成して、共有 SIP アドレス空間を有効にTeams</span><span class="sxs-lookup"><span data-stu-id="c0152-117">Configure your on-premises environment to enable shared SIP address space with Teams</span></span>

<span data-ttu-id="c0152-118">また、共有 SIP アドレス空間を信頼して有効にTeamsオンプレミス環境を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0152-118">You must also configure your on-premises environment to trust Teams and enable shared SIP address space.</span></span> <span data-ttu-id="c0152-119">この構成は、Teamsオンプレミス環境と同じ一連の SIP ドメインのユーザー アカウントをホストする可能性があるという意味で、オンプレミスとオンラインでホストされているユーザー間でメッセージをルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="c0152-119">This configuration means Teams can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span> <span data-ttu-id="c0152-120">以下で説明するように、ProxyFqdn=sipfed.online.lync.com を使用してホスティング プロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c0152-120">You configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="c0152-121">まず、ProxyFqdn=sipfed.online.lync.com のホスティング プロバイダーが既にあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="c0152-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="c0152-122">存在する場合は、管理シェルの次のコマンドを使用してSkype for Business Serverします。</span><span class="sxs-lookup"><span data-stu-id="c0152-122">If one exists, then remove it by using the following command in the Skype for Business Server Management Shell:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="c0152-123">次に、次のように New-CsHostingProviderコマンドレットを使用して、新しいホスティング プロバイダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0152-123">Then create a new hosting provider by using the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="c0152-124">組織内の共有 SIP アドレス空間を有効にする</span><span class="sxs-lookup"><span data-stu-id="c0152-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="c0152-125">オンプレミス展開で行った変更に加えて、Teams 組織で対応する変更を行い、オンプレミス展開で共有 SIP アドレス空間を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0152-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Teams organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="c0152-126">組織内の共有 SIP アドレス空間を有効にするには、リモート PowerShell セッションを Teamsし、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0152-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Teams, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="c0152-127">SharedSipAddressSpace 属性は、オンラインに移行するまで "True" に維持する必要があります。ユーザーはオンプレミスのままではありません。</span><span class="sxs-lookup"><span data-stu-id="c0152-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="c0152-128">リモート PowerShell セッションを Teams (Skype for Business Online) で確立するには、まず PowerShell モジュールをインストールTeams[必要があります](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="c0152-128">To establish a remote PowerShell session with Teams (or Skype for Business Online), you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span> <span data-ttu-id="c0152-129">PowerShell Teamsモジュールは、廃止Skypeされた Busines Online Connector モジュールのモジュールを置き換えるものです。</span><span class="sxs-lookup"><span data-stu-id="c0152-129">The Teams PowerShell module replaces the Skype for Busines Online Connector module, which has been retired.</span></span>
  
<span data-ttu-id="c0152-130">モジュールをインストールした後、次のコマンドレットを使用してリモート セッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="c0152-130">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="c0152-131">Teams を使用してリモート PowerShell セッションを確立する方法、および Teams PowerShell モジュールを使用する方法の詳細については、「Windows PowerShell 用にコンピューターをセットアップする」[を参照してください](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="c0152-131">For more information about how to establish a remote PowerShell session with Teams, and how to use the Teams PowerShell module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="c0152-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0152-132">See also</span></span>

[<span data-ttu-id="c0152-133">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="c0152-133">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
