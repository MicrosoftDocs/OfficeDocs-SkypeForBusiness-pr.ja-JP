---
title: Skype をビジネスのハイブリッドを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: '概要: は、オンライン ビジネスの設置型展開と Skype との間の相互運用性を構成する方法について説明します。'
ms.openlocfilehash: b71ea92b5f7ce275dc5d1b5d2b7ece5be3c77ffc
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244005"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="17240-103">Skype をビジネスのハイブリッドを構成します。</span><span class="sxs-lookup"><span data-stu-id="17240-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="17240-104">ビジネスのハイブリッド用には、Skype を構成するにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="17240-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="17240-105">Office 365 とフェデレーションを行う、オンプレミスの環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="17240-105">Configure your on-premises environment to federate with Office 365.</span></span>](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [<span data-ttu-id="17240-106">オンプレミス環境に Office 365 を信頼するを構成し、Office 365 との共有 SIP アドレス スペースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="17240-106">Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span>](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [<span data-ttu-id="17240-107">Office 365 テナント内の共有 SIP アドレス スペースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="17240-107">Enable shared SIP address space in your Office 365 tenant.</span></span>](#configure-server-to-server-authentication-if-required)

<span data-ttu-id="17240-108">Exchange の設置型の場合は、可能性があるオンライン ビジネス環境の Exchange の設置型と Skype の OAuth を構成するのには注意してください。</span><span class="sxs-lookup"><span data-stu-id="17240-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="17240-109">詳細については、 [Skype のビジネス サーバーの管理サーバーからサーバーへの認証](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)と[ビジネスとの交換用 Skype を統合する計画](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17240-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="17240-110">Office 365 とフェデレーションを行うには、設置端サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="17240-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="17240-111">フェデレーションにより、組織で Office 365 のユーザーと通信する設置型展開でユーザーです。</span><span class="sxs-lookup"><span data-stu-id="17240-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="17240-112">フェデレーションを構成するには、ビジネス サーバー管理シェルの Skype で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="17240-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="17240-113">Office 365 の共有 SIP アドレス スペースを有効にするのには、オンプレミス環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="17240-113">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="17240-114">Office 365 の信頼、オンプレミス環境を構成しと Office 365 の共有 SIP アドレス スペースを有効にする必要がありますもします。</span><span class="sxs-lookup"><span data-stu-id="17240-114">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="17240-115">つまり、Office 365 では、オンプレミス環境では、SIP ドメインの同じセットのユーザー アカウントをホストできる可能性のある施設内でホストされているユーザー間でルーティングとオンラインをメッセージとして使用することができます。</span><span class="sxs-lookup"><span data-stu-id="17240-115">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="17240-116">ProxyFqdn=sipfed.online.lync.com 以下に示すように、ホスティング プロバイダーを構成することによってこれを行います。</span><span class="sxs-lookup"><span data-stu-id="17240-116">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="17240-117">最初に、ProxyFqdn=sipfed.online.lync.com のホスティング プロバイダーが既にあるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="17240-117">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="17240-118">1 つ存在する場合、次のコマンドを使用して削除します。</span><span class="sxs-lookup"><span data-stu-id="17240-118">If one exists, then remove it by using the following command:</span></span>

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="17240-119">新しいホスティング プロバイダーを作成し、新規 CsHostingProvider コマンドレットを使用して、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="17240-119">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="17240-120">Office 365 テナント内の共有 SIP アドレス スペースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="17240-120">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="17240-121">、設置型展開で行った変更に加え、社内設置型展開と共有 SIP アドレス スペースを有効にする、Office 365 テナントに対応する変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="17240-121">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="17240-122">Office 365 テナント内の共有 SIP アドレス スペースを有効にするには、ビジネス オンラインでは、Skype でのリモート PowerShell セッションを確立し、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="17240-122">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="17240-123">SharedSipAddressSpace 属性は、オンラインへの移行が終わり、オンプレミス状態のユーザーがいなくなるまで「True」のままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="17240-123">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="17240-124">ビジネス オンラインのチームと Skype、リモート PowerShell セッションを確立するためにまず取得することができる Windows PowerShell のオンライン ビジネスのコネクタ モジュールの Skype をインストールするのには[ここ](https://go.microsoft.com/fwlink/p/?LinkId=391911)です。</span><span class="sxs-lookup"><span data-stu-id="17240-124">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="17240-125">そのモジュールをインストールしたら、次のコマンドレットによってリモート セッションを確立します。</span><span class="sxs-lookup"><span data-stu-id="17240-125">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="17240-126">ビジネス online では、Skype でのリモート PowerShell セッションを確立する方法と、Skype のビジネス オンライン コネクタ モジュールの使用方法に関する詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17240-126">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="17240-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="17240-127">See also</span></span>

[<span data-ttu-id="17240-128">新しい-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="17240-128">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

