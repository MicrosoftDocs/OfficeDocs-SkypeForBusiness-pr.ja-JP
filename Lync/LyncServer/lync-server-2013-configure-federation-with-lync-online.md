---
title: 'Lync Server 2013: Lync Online とのフェデレーションの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfeffc8a72d26167b9771e6437d21ba55c8f5636
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525954"
---
# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="5221e-102">Lync Online で Lync Server 2013 のフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="5221e-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5221e-103">_**トピックの最終更新日:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="5221e-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="5221e-104">このセクションの手順に従って、オンプレミス展開と Skype for Business Online の間の相互運用性を構成します。</span><span class="sxs-lookup"><span data-stu-id="5221e-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="5221e-105">Skype for Business Online とのフェデレーション用にオンプレミスエッジサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="5221e-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="5221e-106">フェデレーションにより、オンプレミス展開のユーザーは、組織内の Microsoft 365 または Office 365 ユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="5221e-106">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="5221e-107">フェデレーションを構成するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5221e-107">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="5221e-108">共有 SIP アドレススペース用に Skype for Business Online テナントを構成する</span><span class="sxs-lookup"><span data-stu-id="5221e-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="5221e-109">セッション開始プロトコル (SIP) アドレスは、電話番号や電子メールアドレスと同様に、ネットワーク上の各ユーザーの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="5221e-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="5221e-110">オンプレミスから Skype for Business Online に Lync ユーザーを移動する前に、Microsoft 365 または Office 365 組織を構成して、共有セッション開始プロトコル (SIP) アドレススペースを社内展開と共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5221e-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Microsoft 365 or Office 365 organization to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="5221e-111">この設定が構成されていない場合は、次のエラーメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5221e-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="5221e-112">Move-CsUser: HostedMigration fault: Error = (510)、Description = (このユーザーのテナントは、共有 sip アドレススペースでは有効ではありません。)</span><span class="sxs-lookup"><span data-stu-id="5221e-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="5221e-113">共有 SIP アドレススペースを構成するには、Skype for Business Online でリモート PowerShell セッションを確立し、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5221e-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="5221e-114">Skype for Business Online とのリモート PowerShell セッションを確立するには、まず、Windows PowerShell 用の Skype for Business Online モジュールをインストールする必要があります。これには、次の情報を入手でき [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) ます。</span><span class="sxs-lookup"><span data-stu-id="5221e-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="5221e-115">モジュールをインストールした後、次のコマンドレットを使用してリモートセッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="5221e-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

<span data-ttu-id="5221e-116">Skype for business Online とのリモート PowerShell セッションを確立する方法の詳細については、「 [Windows PowerShell を使用した skype For Business online への接続](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5221e-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="5221e-117">Skype for Business Online PowerShell モジュールの使用方法の詳細については、「 [Windows PowerShell を使用して skype For Business online を管理する](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5221e-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5221e-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5221e-118">See Also</span></span>


[<span data-ttu-id="5221e-119">新規-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="5221e-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
