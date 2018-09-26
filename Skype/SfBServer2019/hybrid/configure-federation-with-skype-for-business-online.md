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
ms.openlocfilehash: fb04ecd53c93ae7bd64fca760b752d2d69324c3d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030722"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="897ac-103">Skype をビジネスのハイブリッドを構成します。</span><span class="sxs-lookup"><span data-stu-id="897ac-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="897ac-104">ビジネスのハイブリッド用には、Skype を構成するにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="897ac-104">To configure Skype for Business hybrid, you need to:</span></span>

- [<span data-ttu-id="897ac-105">フェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="897ac-105">Configure federation</span></span>](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [<span data-ttu-id="897ac-106">共有セッション開始プロトコル (SIP) のアドレス スペースを構成します。</span><span class="sxs-lookup"><span data-stu-id="897ac-106">Configure a shared Session Initiation Protocol (SIP) address space</span></span>](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [<span data-ttu-id="897ac-107">必要な場合は、サーバーからサーバーへの認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="897ac-107">Configure server-to-server authentication if required</span></span>](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="897ac-108">ビジネス オンラインの Skype で、設置型のエッジ サービスのフェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="897ac-108">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="897ac-109">フェデレーションにより、組織で Office 365 のユーザーと通信する設置型展開でユーザーです。</span><span class="sxs-lookup"><span data-stu-id="897ac-109">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="897ac-110">フェデレーションを構成するには、ビジネス サーバー管理シェルの Skype で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="897ac-110">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="897ac-111">共有 SIP アドレス スペースのオンライン ビジネスのテナントは、Skype を構成します。</span><span class="sxs-lookup"><span data-stu-id="897ac-111">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="897ac-112">セッション開始プロトコル (SIP) アドレスは、電話番号や電子メール アドレスに似た、ネットワーク上の各ユーザーの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="897ac-112">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="897ac-113">オンライン ビジネスのユーザーを設置から Skype に移動しようとすると、前に、社内設置型展開と共有のセッション開始プロトコル (SIP) アドレス空間を共有するのには、Office 365 のテナントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="897ac-113">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="897ac-114">これが構成されていないと、次のエラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="897ac-114">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="897ac-115">移動-CsUser: HostedMigration フォールト: Error=(510)、説明 = (このユーザーのテナントが対応でない共有 sip アドレス スペースです)。</span><span class="sxs-lookup"><span data-stu-id="897ac-115">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="897ac-116">共有 SIP アドレス スペースを構成するには、ビジネス オンラインでは、Skype でのリモート PowerShell セッションを確立し、次のコマンドレットを実行し。</span><span class="sxs-lookup"><span data-stu-id="897ac-116">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="897ac-117">SharedSipAddressSpace 属性は、オンラインへの移行が終わり、オンプレミス状態のユーザーがいなくなるまで「True」のままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="897ac-117">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="897ac-118">ビジネス オンラインの Skype でのリモート PowerShell セッションを確立するためにまず取得することができる Windows PowerShell のオンライン ビジネスのコネクタ モジュールの Skype をインストールするのには[ここ](https://go.microsoft.com/fwlink/p/?LinkId=391911)です。</span><span class="sxs-lookup"><span data-stu-id="897ac-118">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="897ac-119">そのモジュールをインストールしたら、次のコマンドレットによってリモート セッションを確立します。</span><span class="sxs-lookup"><span data-stu-id="897ac-119">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

<span data-ttu-id="897ac-120">ビジネス online では、Skype でのリモート PowerShell セッションを確立する方法と、Skype のビジネス オンライン コネクタ モジュールの使用方法に関する詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="897ac-120">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="configure-server-to-server-authentication-if-required"></a><span data-ttu-id="897ac-121">必要な場合は、サーバーからサーバーへの認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="897ac-121">Configure server-to-server authentication if required</span></span>

<span data-ttu-id="897ac-122">、ハイブリッド環境を構成しているの種類によっては、サーバーからサーバーへの認証を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="897ac-122">Depending on the type of hybrid environment you are configuring, you may need to configure server-to-server authentication.</span></span>  <span data-ttu-id="897ac-123">詳細については、 [Skype のビジネス サーバーの管理サーバーからサーバーへの認証](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="897ac-123">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).</span></span>


## <a name="see-also"></a><span data-ttu-id="897ac-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="897ac-124">See also</span></span>

[<span data-ttu-id="897ac-125">新しい-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="897ac-125">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

