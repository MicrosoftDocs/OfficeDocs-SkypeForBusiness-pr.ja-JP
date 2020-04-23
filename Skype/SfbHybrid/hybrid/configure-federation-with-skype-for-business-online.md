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
ms.openlocfilehash: ccf140b62cdbad11605c99fe1cb0cc66aa1ee4dd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780106"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="e5920-103">Skype for Business ハイブリッドの構成</span><span class="sxs-lookup"><span data-stu-id="e5920-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="e5920-104">Skype for Business ハイブリッドを構成するには、次のことを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5920-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="e5920-105">[Office 365 または別の組織とフェデレーションするようにオンプレミスのエッジサービスを構成](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization)します。</span><span class="sxs-lookup"><span data-stu-id="e5920-105">[Configure your on-premises Edge service to federate with Office 365 or another organization](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).</span></span>
- <span data-ttu-id="e5920-106">Office [365 を信頼するようにオンプレミス環境を構成し、office 365 で共有 SIP アドレススペースを有効](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365)にします。</span><span class="sxs-lookup"><span data-stu-id="e5920-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="e5920-107">[Office 365 組織の共有 SIP アドレススペースを有効に](#enable-shared-sip-address-space-in-your-office-365-organization)します。</span><span class="sxs-lookup"><span data-stu-id="e5920-107">[Enable shared SIP address space in your Office 365 organization](#enable-shared-sip-address-space-in-your-office-365-organization).</span></span>

<span data-ttu-id="e5920-108">オンプレミスの Exchange を使用している場合は、Exchange のオンプレミスと Skype for business Online 環境の間で OAuth を構成することが必要になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5920-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="e5920-109">詳細については、「 [skype for Business server でサーバー間認証を管理](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)する」および「 [skype For business と Exchange の統合を計画する](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5920-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization"></a><span data-ttu-id="e5920-110">Office 365 または別の組織とフェデレーションするようにオンプレミスのエッジサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="e5920-110">Configure your on-premises Edge service to federate with Office 365 or another organization</span></span>

<span data-ttu-id="e5920-111">フェデレーションにより、オンプレミス展開のユーザーは、組織内の Microsoft 365 または Office 365 ユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="e5920-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="e5920-112">フェデレーションを構成するには、Skype for Business Server 管理シェルで次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5920-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="e5920-113">'-EnablePartnerDiscovery ' の値が $True に設定されている場合、Skype for Business Server は DNS レコードを使用して、AllowedDomains リストに一覧表示されていないパートナードメインを検索して検出します。</span><span class="sxs-lookup"><span data-stu-id="e5920-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="e5920-114">この値が $False に設定されている場合、Skype for Business Server は AllowedDomains リストにあるドメインとのみフェデレーションを行います。</span><span class="sxs-lookup"><span data-stu-id="e5920-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="e5920-115">DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="e5920-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="e5920-116">オンプレミスの Skype for business 展開と Skype for Business Online 組織のユーザーとの間のフェデレーションを有効にする方法の詳細については、「skype for business [Server で skype For Business online ユーザーのフェデレーションサポートを構成](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5920-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="e5920-117">Office 365 で共有 SIP アドレススペースを有効にするようにオンプレミス環境を構成する</span><span class="sxs-lookup"><span data-stu-id="e5920-117">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="e5920-118">また、Office 365 を信頼し Office 365 に対して共有 SIP アドレス スペースを有効にするように、オンプレミス環境を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5920-118">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="e5920-119">つまり、Office 365 は、オンプレミス環境と同じセットの SIP ドメインに対してユーザーアカウントをホストする可能性があり、社内および online でホストされているユーザー間でメッセージをルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5920-119">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="e5920-120">これを行うには、以下に示すように、ProxyFqdn = sipfed を使用してホスティングプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="e5920-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="e5920-121">最初に、ProxyFqdn = sipfed を使用するホスティングプロバイダーが既に存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e5920-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="e5920-122">存在する場合は、次のコマンドを使用して削除します。</span><span class="sxs-lookup"><span data-stu-id="e5920-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="e5920-123">次に、新しいホスティングプロバイダーを作成し、次のようにして、新しい-CsHostingProvider コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5920-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-organization"></a><span data-ttu-id="e5920-124">Office 365 組織の共有 SIP アドレススペースを有効にする</span><span class="sxs-lookup"><span data-stu-id="e5920-124">Enable shared SIP address space in your Office 365 organization</span></span>
  
<span data-ttu-id="e5920-125">オンプレミス展開で行われた変更に加えて、Office 365 組織で対応する変更を行って、オンプレミス展開で共有 SIP アドレススペースを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5920-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="e5920-126">Office 365 組織の共有 SIP アドレススペースを有効にするには、Skype for Business Online でリモート PowerShell セッションを確立し、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e5920-126">To enable shared SIP address space in your Office 365 organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="e5920-127">SharedSipAddressSpace 属性は、オンラインへの移行が final になるまで「True」のままにしておき、ユーザーがオンプレミスのままにならないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5920-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="e5920-128">Teams または Skype for Business Online とのリモート PowerShell セッションを確立するには、まず Windows PowerShell 用 Skype for Business Online connector モジュールをインストールする必要があります。これは[こちら](https://go.microsoft.com/fwlink/p/?LinkId=391911)から入手できます。</span><span class="sxs-lookup"><span data-stu-id="e5920-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="e5920-129">モジュールをインストールした後、次のコマンドレットを使用してリモートセッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="e5920-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="e5920-130">Skype for business Online でリモート PowerShell セッションを確立する方法と、Skype for Business Online Connector モジュールを使用する方法の詳細については、「 [Windows PowerShell 用にコンピューター](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5920-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="e5920-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5920-131">See also</span></span>

[<span data-ttu-id="e5920-132">新規-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="e5920-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
