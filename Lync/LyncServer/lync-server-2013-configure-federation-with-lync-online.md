---
title: 'Lync Server 2013: Lync Online とのフェデレーションを構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ee7cf175e2ca46a54f3c6505fe5f94b69120763
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="8d727-102">Lync Server 2013 と Lync Online のフェデレーションを構成する</span><span class="sxs-lookup"><span data-stu-id="8d727-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d727-103">_**最終更新日:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="8d727-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="8d727-104">このセクションの手順に従って、オンプレミス展開と Skype for Business Online の間の相互運用性を構成します。</span><span class="sxs-lookup"><span data-stu-id="8d727-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="8d727-105">Skype for Business Online とのフェデレーション用にオンプレミスエッジサービスを構成する</span><span class="sxs-lookup"><span data-stu-id="8d727-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="8d727-106">フェデレーションによって、オンプレミスの展開のユーザーは、組織内の Office 365 ユーザーと通信することができます。</span><span class="sxs-lookup"><span data-stu-id="8d727-106">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="8d727-107">フェデレーションを構成するには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d727-107">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="8d727-108">共有 SIP アドレス空間用に Skype for Business Online テナントを構成する</span><span class="sxs-lookup"><span data-stu-id="8d727-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="8d727-109">セッション開始プロトコル (SIP) アドレスは、電話番号や電子メール アドレスに似た、ネットワーク上の各ユーザーの一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="8d727-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="8d727-110">Lync ユーザーをオンプレミスから Skype for Business Online に移行する前に、オンプレミスの展開を使用して共有セッション開始プロトコル (SIP) アドレススペースを共有するように Office 365 テナントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d727-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="8d727-111">これが構成されていないと、次のエラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="8d727-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="8d727-112">Move-CsUser : HostedMigration エラー: エラー=(510), 説明=(このユーザーのテナントは共有 SIP アドレス スペース用に有効化されていません。)</span><span class="sxs-lookup"><span data-stu-id="8d727-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="8d727-113">共有 SIP アドレス空間を構成するには、Skype for Business Online とのリモート PowerShell セッションを確立して、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d727-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="8d727-114">Skype for Business Online とのリモート PowerShell セッションを確立するには、まず、Windows PowerShell 用 Skype for Business Online モジュールをインストールする必要があります。 [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)これには、次のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d727-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="8d727-115">そのモジュールをインストールしたら、次のコマンドレットによってリモート セッションを確立します。</span><span class="sxs-lookup"><span data-stu-id="8d727-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

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

<span data-ttu-id="8d727-116">Skype for Business Online とのリモート PowerShell セッションを確立する方法の詳細については、「 [Windows PowerShell を使用して skype For Business online に接続](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d727-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="8d727-117">Skype for Business Online PowerShell モジュールの使用方法の詳細については、「 [Windows PowerShell を使用して skype For Business online を管理する](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d727-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d727-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8d727-118">See Also</span></span>


[<span data-ttu-id="8d727-119">新規-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="8d727-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

