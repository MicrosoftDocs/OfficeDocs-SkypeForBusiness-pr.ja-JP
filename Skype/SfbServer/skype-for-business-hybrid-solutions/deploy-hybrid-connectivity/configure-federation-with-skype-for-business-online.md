---
title: Skype for Business Online とのフェデレーションを構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: '概要: は、オンライン ビジネスの設置型展開と Skype との間の相互運用性を構成する方法について説明します。'
ms.openlocfilehash: 403cabdd808cd197ece2289564b14fea62a5c72a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="configure-federation-with-skype-for-business-online"></a><span data-ttu-id="806e6-103">Skype for Business Online とのフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="806e6-103">Configure federation with Skype for Business Online</span></span>
 
<span data-ttu-id="806e6-104">**の概要:** オンライン ビジネスの設置型展開と Skype との間の相互運用性を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="806e6-104">**Summary:** Learn how to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
<span data-ttu-id="806e6-105">ビジネス オンラインの設置型展開と Skype との間の相互運用性を構成するには、このセクションの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="806e6-105">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="806e6-106">ビジネス オンラインの Skype で、設置型のエッジ サービスのフェデレーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="806e6-106">Configure your on-premises Edge service for federation with Skype for Business Online</span></span>

<span data-ttu-id="806e6-107">フェデレーションにより、組織で Office 365 のユーザーと通信する設置型展開でユーザーです。</span><span class="sxs-lookup"><span data-stu-id="806e6-107">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="806e6-108">フェデレーションを構成するには、ビジネス サーバー管理シェルの Skype で次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="806e6-108">To configure federation, run the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="806e6-109">共有 SIP アドレス スペースのオンライン ビジネスのテナントは、Skype を構成します。</span><span class="sxs-lookup"><span data-stu-id="806e6-109">Configure your Skype for Business Online tenant for a shared SIP address space</span></span>

<span data-ttu-id="806e6-110">セッション開始プロトコル (SIP) アドレスは、電話番号や電子メール アドレスに似た、ネットワーク上の各ユーザーの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="806e6-110">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="806e6-111">オンライン ビジネスのユーザーを設置から Skype に移動しようとすると、前に、社内設置型展開と共有のセッション開始プロトコル (SIP) アドレス空間を共有するのには、Office 365 のテナントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="806e6-111">Before you try to move users from on-premises to Skype for Business Online, you'll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="806e6-112">これが構成されていないと、次のエラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="806e6-112">If this is not configured, you may see the following error message:</span></span>
  
<span data-ttu-id="806e6-113">移動-CsUser: HostedMigration フォールト: Error=(510)、説明 = (このユーザーのテナントが対応でない共有 sip アドレス スペースです)。</span><span class="sxs-lookup"><span data-stu-id="806e6-113">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user's tenant is not enabled for shared sip address space.)</span></span>
  
<span data-ttu-id="806e6-114">共有 SIP アドレス スペースを構成するには、ビジネス オンラインでは、Skype でのリモート PowerShell セッションを確立し、次のコマンドレットを実行し。</span><span class="sxs-lookup"><span data-stu-id="806e6-114">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="806e6-115">SharedSipAddressSpace 属性は、オンラインへの移行が終わり、オンプレミス状態のユーザーがいなくなるまで「True」のままにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="806e6-115">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="806e6-116">ビジネス オンラインの Skype でのリモート PowerShell セッションを確立するためにまずここに到達することができる Windows PowerShell のオンライン ビジネスのコネクタ モジュールの Skype をインストールするのには: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911)。</span><span class="sxs-lookup"><span data-stu-id="806e6-116">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="806e6-117">そのモジュールをインストールしたら、次のコマンドレットによってリモート セッションを確立します。</span><span class="sxs-lookup"><span data-stu-id="806e6-117">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
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

<span data-ttu-id="806e6-118">ビジネス オンラインの Skype でのリモート PowerShell セッションを確立する方法の詳細については、 [Lync オンラインで使用する Windows PowerShell への接続](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="806e6-118">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Lync Online By Using Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).</span></span>
  
<span data-ttu-id="806e6-119">Skype を使用して、オンライン ビジネスのコネクタの PowerShell モジュールの詳細については、 [Lync Online の管理に Windows PowerShell を使用する](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="806e6-119">For more information about using the Skype for Business Online connector PowerShell module, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="806e6-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="806e6-120">See also</span></span>

#### 

[<span data-ttu-id="806e6-121">新しい-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="806e6-121">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

