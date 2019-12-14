---
title: ダイレクト ルーティングを構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Microsoft Phone システムのダイレクトルーティングを構成する方法について説明します。
ms.openlocfilehash: 3524d3d41db02dbc123700ae259386bb97257bbd
ms.sourcegitcommit: c15ab82834005b9a19247e06488f1f21161fc426
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2019
ms.locfileid: "40020071"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="b6023-103">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="b6023-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="b6023-104">ダイレクトルーティングの利点、計画方法、展開方法については、次のセッションをご覧ください。 [Microsoft Teams での直接ルーティング](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="b6023-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="b6023-105">まだインストールしていない場合は、「[直接ルーティング](direct-routing-plan.md)の前提条件」を参照してください。また、Microsoft 電話システムネットワークを構成する前に必要なその他の手順を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b6023-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="b6023-106">この記事では、Microsoft Phone システムのダイレクトルーティングを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6023-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="b6023-107">サポートされているセッション境界コントローラー (SBC) とダイレクトルーティングをペアリングする方法について説明します。また、Microsoft Teams ユーザーが直接ルーティングを使用して公衆交換電話網 (PSTN) に接続するように構成する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="b6023-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="b6023-108">この記事で説明されている手順を実行するには、管理者が PowerShell コマンドレットについて理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6023-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="b6023-109">PowerShell の使用方法の詳細については、「 [Windows powershell 用にコンピューターをセットアップする](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6023-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="b6023-110">Sbc が SBC ベンダーの推奨として既に構成されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6023-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="b6023-111">AudioCodes の展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="b6023-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="b6023-112">Oracle 展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="b6023-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="b6023-113">リボンの通信展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="b6023-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="b6023-114">TE システム (anynode) の展開ドキュメント</span><span class="sxs-lookup"><span data-stu-id="b6023-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="b6023-115">Microsoft 電話システムを構成し、ユーザーが直接ルーティングを使用できるようにすることができます。次の手順を実行して、優先発信クライアントとして Microsoft Teams をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="b6023-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="b6023-116">SBC と Microsoft 電話システムをペアリングし、ペアリングを検証する</span><span class="sxs-lookup"><span data-stu-id="b6023-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="b6023-117">ユーザーのダイレクトルーティングサービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="b6023-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- <span data-ttu-id="b6023-118">Microsoft Teams が、ユーザーの優先発信クライアントであることを確認する</span><span class="sxs-lookup"><span data-stu-id="b6023-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="b6023-119">SBC を電話システムのダイレクトルーティングサービスにペアリングする</span><span class="sxs-lookup"><span data-stu-id="b6023-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="b6023-120">次に、SBC を直接ルーティングインターフェイスに接続するかペアリングする3つの大まかな手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6023-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="b6023-121">PowerShell を使用して**Skype For Business Online**管理センターに接続する</span><span class="sxs-lookup"><span data-stu-id="b6023-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="b6023-122">SBC をペアリングする</span><span class="sxs-lookup"><span data-stu-id="b6023-122">Pair the SBC</span></span> 
- <span data-ttu-id="b6023-123">ペアリングを検証する</span><span class="sxs-lookup"><span data-stu-id="b6023-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="b6023-124">PowerShell を使用して Skype for Business Online に接続する</span><span class="sxs-lookup"><span data-stu-id="b6023-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="b6023-125">テナントに接続された PowerShell セッションを使って、SBC とダイレクトルーティングインターフェイスをペアリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6023-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="b6023-126">PowerShell セッションを開くには、「 [Windows powershell 用にコンピューターを](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)セットアップする」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b6023-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="b6023-127">リモート PowerShell セッションを確立したら、SBC を管理するためのコマンドが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="b6023-128">コマンドを検証するには、PowerShell セッションで次のように入力するか、コピーして貼り付け、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b6023-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="b6023-129">このコマンドを実行すると、次に示す4つの関数が返され、SBC を管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b6023-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="b6023-130">SBC をテナントにペアリングする</span><span class="sxs-lookup"><span data-stu-id="b6023-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="b6023-131">SBC をテナントにペアリングするには、PowerShell セッションで次のように入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b6023-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="b6023-132">Sbc ドキュメントに記載されている情報を使って、SBC で最大限の通話制限を設定することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6023-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="b6023-133">SBC がキャパシティレベルにある場合、制限によって通知がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="b6023-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="b6023-134">SBC をペアリングできるのは、その FQDN のドメイン部分が、テナントに登録されているドメインのいずれ\*かに一致している場合のみです。 onmicrosoft.com を除きます。</span><span class="sxs-lookup"><span data-stu-id="b6023-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="b6023-135">\*Onmicrosoft.com ドメイン名は、SBC FQDN 名ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b6023-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="b6023-136">たとえば、2つのドメイン名がある場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b6023-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="b6023-137">**contoso**.com</span><span class="sxs-lookup"><span data-stu-id="b6023-137">**contoso**.com</span></span><br/><span data-ttu-id="b6023-138">\*\*\*\* onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b6023-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="b6023-139">SBC 名には、sbc.contoso.com という名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6023-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="b6023-140">SBC と名前 sbc をペアリングしようとしても、ドメインはこのテナントによって所有されていないため、システムによっては許可されません。</span><span class="sxs-lookup"><span data-stu-id="b6023-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="b6023-141">テナントに登録されているドメインに加えて、そのドメインを持つユーザーと E3 または E5 ライセンスが割り当てられていることが重要です。</span><span class="sxs-lookup"><span data-stu-id="b6023-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="b6023-142">存在しない場合、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="b6023-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="b6023-143"></span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="b6023-144">返し</span><span class="sxs-lookup"><span data-stu-id="b6023-144">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="b6023-145">ペアリングプロセス中に設定できるその他のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b6023-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="b6023-146">ただし、前の例では、必須の最小パラメーターのみが表示されています。</span><span class="sxs-lookup"><span data-stu-id="b6023-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="b6023-147">次の表は、の```New-CsOnlinePstnGateway```パラメーターの設定に使用できるその他のパラメーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="b6023-147">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="b6023-148">必須。</span><span class="sxs-lookup"><span data-stu-id="b6023-148">Required?</span></span>|<span data-ttu-id="b6023-149">名前</span><span class="sxs-lookup"><span data-stu-id="b6023-149">Name</span></span>|<span data-ttu-id="b6023-150">説明</span><span class="sxs-lookup"><span data-stu-id="b6023-150">Description</span></span>|<span data-ttu-id="b6023-151">既定</span><span class="sxs-lookup"><span data-stu-id="b6023-151">Default</span></span>|<span data-ttu-id="b6023-152">可能な値</span><span class="sxs-lookup"><span data-stu-id="b6023-152">Possible values</span></span>|<span data-ttu-id="b6023-153">種類と制限</span><span class="sxs-lookup"><span data-stu-id="b6023-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b6023-154">はい</span><span class="sxs-lookup"><span data-stu-id="b6023-154">Yes</span></span>|<span data-ttu-id="b6023-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="b6023-155">FQDN</span></span>|<span data-ttu-id="b6023-156">SBC の FQDN 名</span><span class="sxs-lookup"><span data-stu-id="b6023-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="b6023-157">なし</span><span class="sxs-lookup"><span data-stu-id="b6023-157">None</span></span>|<span data-ttu-id="b6023-158">NoneFQDN 名、63文字を制限する</span><span class="sxs-lookup"><span data-stu-id="b6023-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="b6023-159">[コンピューター、ドメイン、サイト、および ou の Active Directory の名前付け規則](https://support.microsoft.com/help/909264)での文字列、許可されている文字および禁止されている文字の一覧</span><span class="sxs-lookup"><span data-stu-id="b6023-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="b6023-160">いいえ</span><span class="sxs-lookup"><span data-stu-id="b6023-160">No</span></span>|<span data-ttu-id="b6023-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="b6023-161">MediaBypass</span></span> |<span data-ttu-id="b6023-162">は、SBC でサポートされているメディアバイパスのパラメーターであり、管理者はこのパラメーターを使いたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="b6023-162">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="b6023-163">なし</span><span class="sxs-lookup"><span data-stu-id="b6023-163">None</span></span>|<span data-ttu-id="b6023-164">True</span><span class="sxs-lookup"><span data-stu-id="b6023-164">True</span></span><br/><span data-ttu-id="b6023-165">False</span><span class="sxs-lookup"><span data-stu-id="b6023-165">False</span></span>|<span data-ttu-id="b6023-166">Boolean</span><span class="sxs-lookup"><span data-stu-id="b6023-166">Boolean</span></span>|
|<span data-ttu-id="b6023-167">はい</span><span class="sxs-lookup"><span data-stu-id="b6023-167">Yes</span></span>|<span data-ttu-id="b6023-168">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="b6023-168">SipSignallingPort</span></span> |<span data-ttu-id="b6023-169">トランスポート層セキュリティ (TLS) プロトコルを使用した、直接ルーティングサービスとの通信に使用するリスニングポート。</span><span class="sxs-lookup"><span data-stu-id="b6023-169">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="b6023-170">なし</span><span class="sxs-lookup"><span data-stu-id="b6023-170">None</span></span>|<span data-ttu-id="b6023-171">任意のポート</span><span class="sxs-lookup"><span data-stu-id="b6023-171">Any port</span></span>|<span data-ttu-id="b6023-172">0 ~ 65535</span><span class="sxs-lookup"><span data-stu-id="b6023-172">0 to 65535</span></span> |
|<span data-ttu-id="b6023-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="b6023-173">No</span></span>|<span data-ttu-id="b6023-174">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="b6023-174">FailoverTimeSeconds</span></span> |<span data-ttu-id="b6023-175">10 (既定値) に設定すると、ゲートウェイによって応答されない送信通話は、次の利用可能なトランクにルーティングされます。追加の trunks がない場合、通話は自動的に切断されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-175">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="b6023-176">低速のネットワークとゲートウェイ応答を使用している組織では、通話が不必要に削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6023-176">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="b6023-177">既定値は10です。</span><span class="sxs-lookup"><span data-stu-id="b6023-177">The default value is 10.</span></span>|<span data-ttu-id="b6023-178">常用</span><span class="sxs-lookup"><span data-stu-id="b6023-178">10</span></span>|<span data-ttu-id="b6023-179">数値</span><span class="sxs-lookup"><span data-stu-id="b6023-179">Number</span></span>|<span data-ttu-id="b6023-180">Int</span><span class="sxs-lookup"><span data-stu-id="b6023-180">Int</span></span>|
|<span data-ttu-id="b6023-181">いいえ</span><span class="sxs-lookup"><span data-stu-id="b6023-181">No</span></span>|<span data-ttu-id="b6023-182">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="b6023-182">ForwardCallHistory</span></span> |<span data-ttu-id="b6023-183">通話履歴の情報をトランク経由で転送するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b6023-183">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="b6023-184">有効になっている場合、Office 365 PSTN プロキシは、2つのヘッダー (履歴-情報と参照) を送信します。</span><span class="sxs-lookup"><span data-stu-id="b6023-184">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="b6023-185">既定値は**False** ($False) です。</span><span class="sxs-lookup"><span data-stu-id="b6023-185">The default value is **False** ($False).</span></span> |<span data-ttu-id="b6023-186">False</span><span class="sxs-lookup"><span data-stu-id="b6023-186">False</span></span>|<span data-ttu-id="b6023-187">True</span><span class="sxs-lookup"><span data-stu-id="b6023-187">True</span></span><br/><span data-ttu-id="b6023-188">False</span><span class="sxs-lookup"><span data-stu-id="b6023-188">False</span></span>|<span data-ttu-id="b6023-189">Boolean</span><span class="sxs-lookup"><span data-stu-id="b6023-189">Boolean</span></span>|
|<span data-ttu-id="b6023-190">いいえ</span><span class="sxs-lookup"><span data-stu-id="b6023-190">No</span></span>|<span data-ttu-id="b6023-191">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="b6023-191">ForwardPAI</span></span>|<span data-ttu-id="b6023-192">P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b6023-192">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="b6023-193">PAI ヘッダーがあれば、発信者 ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b6023-193">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="b6023-194">有効になっている場合、プライバシー: ID ヘッダーも送信されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-194">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="b6023-195">既定値は**False** ($False) です。</span><span class="sxs-lookup"><span data-stu-id="b6023-195">The default value is **False** ($False).</span></span>|<span data-ttu-id="b6023-196">False</span><span class="sxs-lookup"><span data-stu-id="b6023-196">False</span></span>|<span data-ttu-id="b6023-197">True</span><span class="sxs-lookup"><span data-stu-id="b6023-197">True</span></span><br/><span data-ttu-id="b6023-198">False</span><span class="sxs-lookup"><span data-stu-id="b6023-198">False</span></span>|<span data-ttu-id="b6023-199">Boolean</span><span class="sxs-lookup"><span data-stu-id="b6023-199">Boolean</span></span>|
|<span data-ttu-id="b6023-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="b6023-200">No</span></span>|<span data-ttu-id="b6023-201">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="b6023-201">SendSIPOptions</span></span> |<span data-ttu-id="b6023-202">SBC が SIP オプションを送信するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="b6023-202">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="b6023-203">無効にした場合、SBC は、監視および警告システムから除外されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-203">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="b6023-204">SIP オプションを有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6023-204">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="b6023-205">既定値は**True**です。</span><span class="sxs-lookup"><span data-stu-id="b6023-205">Default value is **True**.</span></span> |<span data-ttu-id="b6023-206">True</span><span class="sxs-lookup"><span data-stu-id="b6023-206">True</span></span>|<span data-ttu-id="b6023-207">True</span><span class="sxs-lookup"><span data-stu-id="b6023-207">True</span></span><br/><span data-ttu-id="b6023-208">False</span><span class="sxs-lookup"><span data-stu-id="b6023-208">False</span></span>|<span data-ttu-id="b6023-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="b6023-209">Boolean</span></span>|
|<span data-ttu-id="b6023-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="b6023-210">No</span></span>|<span data-ttu-id="b6023-211">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="b6023-211">MaxConcurrentSessions</span></span> |<span data-ttu-id="b6023-212">アラートシステムで使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-212">Used by alerting system.</span></span> <span data-ttu-id="b6023-213">いずれかの値が設定されると、同時セッション数が90% 以上である場合、またはこの値よりも高い場合に、通知システムによってテナント管理者に通知が生成されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-213">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="b6023-214">パラメーターが設定されていない場合、アラートは生成されません。</span><span class="sxs-lookup"><span data-stu-id="b6023-214">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="b6023-215">ただし、監視システムでは、24時間ごとに同時セッションの数が報告されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-215">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="b6023-216">空</span><span class="sxs-lookup"><span data-stu-id="b6023-216">Null</span></span>|<span data-ttu-id="b6023-217">空</span><span class="sxs-lookup"><span data-stu-id="b6023-217">Null</span></span><br/><span data-ttu-id="b6023-218">1 ~ 10万</span><span class="sxs-lookup"><span data-stu-id="b6023-218">1 to 100,000</span></span> ||
|<span data-ttu-id="b6023-219">いいえ</span><span class="sxs-lookup"><span data-stu-id="b6023-219">No</span></span>|<span data-ttu-id="b6023-220">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="b6023-220">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="b6023-221">メディアのパスを手動で選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="b6023-221">Allows selecting path for media manually.</span></span> <span data-ttu-id="b6023-222">直接ルーティングでは、SBC のパブリック IP に基づいて、メディアパスのデータセンターが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b6023-222">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="b6023-223">常に、SBC データセンターに最も近いものを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6023-223">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="b6023-224">ただし、場合によっては、たとえば、米国の範囲を、ヨーロッパにある SBC に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b6023-224">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="b6023-225">この場合は、最適なメディアパスを使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="b6023-225">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="b6023-226">このパラメーターを使うと、メディアトラフィックの優先領域を手動で設定できます。</span><span class="sxs-lookup"><span data-stu-id="b6023-226">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="b6023-227">このパラメーターを設定することをお勧めします。このパラメーターを設定することは、メディアパスのデータセンターの自動割り当てで SBC データセンターに最も近い値が割り当てられないということを意味します。</span><span class="sxs-lookup"><span data-stu-id="b6023-227">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="b6023-228">なし</span><span class="sxs-lookup"><span data-stu-id="b6023-228">None</span></span>|<span data-ttu-id="b6023-229">ISO 形式の国コード</span><span class="sxs-lookup"><span data-stu-id="b6023-229">Country codes in ISO format</span></span>||
|<span data-ttu-id="b6023-230">いいえ</span><span class="sxs-lookup"><span data-stu-id="b6023-230">No</span></span>|<span data-ttu-id="b6023-231">有効</span><span class="sxs-lookup"><span data-stu-id="b6023-231">Enabled</span></span>|<span data-ttu-id="b6023-232">この SBC を発信通話に対して有効にします。</span><span class="sxs-lookup"><span data-stu-id="b6023-232">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="b6023-233">更新中またはメンテナンス中に、SBC を一時的に削除するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6023-233">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="b6023-234">False</span><span class="sxs-lookup"><span data-stu-id="b6023-234">False</span></span>|<span data-ttu-id="b6023-235">True</span><span class="sxs-lookup"><span data-stu-id="b6023-235">True</span></span><br/><span data-ttu-id="b6023-236">False</span><span class="sxs-lookup"><span data-stu-id="b6023-236">False</span></span>|<span data-ttu-id="b6023-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="b6023-237">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="b6023-238">SBC ペアリングを確認する</span><span class="sxs-lookup"><span data-stu-id="b6023-238">Verify the SBC pairing</span></span> 

<span data-ttu-id="b6023-239">接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-239">Verify the connection:</span></span> 
- <span data-ttu-id="b6023-240">SBC が、ペアリングされた SBCs のリストにあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-240">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="b6023-241">SIP オプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-241">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="b6023-242">SBC が、ペアリングされた SBCs のリストにあるかどうかを検証します</span><span class="sxs-lookup"><span data-stu-id="b6023-242">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="b6023-243">SBC をペアリングした後、リモート PowerShell セッションで次のコマンドを実行して、SBC が、[ペアリングされた SBCs] のリストに存在することを確認します。`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="b6023-243">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="b6023-244">次の例に示すように、ペアリングされたゲートウェイがリストに表示され、**有効になっ**ているパラメーターに**True**の値が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-244">The paired gateway should appear in the list as shown in the example below, and verify that the **Enabled** parameter  displays a value of **True**.</span></span> <span data-ttu-id="b6023-245">ください</span><span class="sxs-lookup"><span data-stu-id="b6023-245">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="b6023-246">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b6023-246">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="b6023-247">SIP オプションのフローを検証する</span><span class="sxs-lookup"><span data-stu-id="b6023-247">Validate SIP Options flow</span></span> 

<span data-ttu-id="b6023-248">発信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用して、SBC が送信オプションメッセージに対する 200 OK 応答を受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-248">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="b6023-249">ダイレクトルーティングでは、着信オプションが表示され、着信のオプションメッセージの [連絡先ヘッダー] フィールドに設定された SBC FQDN への送信 SIP オプションメッセージの送信が開始されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-249">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="b6023-250">着信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用します。また、SBC は直接ルーティングからのオプションメッセージに返信を送信し、送信する応答コードは 200 OK であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-250">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="b6023-251">ユーザーのダイレクトルーティングサービスを有効にする</span><span class="sxs-lookup"><span data-stu-id="b6023-251">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="b6023-252">ユーザーが直接ルーティングサービスを有効にする準備ができたら、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6023-252">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="b6023-253">Office 365 でユーザーを作成し、電話システムのライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b6023-253">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="b6023-254">ユーザーが Skype for Business Online に所属していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-254">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="b6023-255">電話番号を構成し、エンタープライズボイスとボイスメールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b6023-255">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="b6023-256">音声ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="b6023-256">Configure voice routing.</span></span> <span data-ttu-id="b6023-257">ルートは、自動的に検証されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-257">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="b6023-258">Office 365 でユーザーを作成してライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b6023-258">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="b6023-259">Office 365 で新規ユーザーを作成するには、2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b6023-259">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="b6023-260">ただし、ルーティングの問題を回避するために、次のいずれかのオプションを組織で選択して使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6023-260">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="b6023-261">オンプレミスの Active Directory でユーザーを作成し、ユーザーをクラウドと同期します。</span><span class="sxs-lookup"><span data-stu-id="b6023-261">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="b6023-262">「[オンプレミスディレクトリと Azure Active Directory の統合」を](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6023-262">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="b6023-263">Office 365 管理ポータルに直接ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6023-263">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="b6023-264">「 [Office 365 にユーザーを個別に、またはまとめて追加する-管理者向けヘルプ」を](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6023-264">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="b6023-265">Skype for business Online の展開が Skype for Business 2015 または Lync 2010/2013 のオンプレミスで共存している場合、サポートされているのは、オンプレミスの Active Directory でユーザーを作成して、ユーザーをクラウドに同期する方法 (オプション 1) だけです。</span><span class="sxs-lookup"><span data-stu-id="b6023-265">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="b6023-266">必要なライセンス:</span><span class="sxs-lookup"><span data-stu-id="b6023-266">Required licenses:</span></span> 

- <span data-ttu-id="b6023-267">Office 365 Enterprise E3 (SfB Plan2、Exchange Plan2、Teams など) + 電話システム</span><span class="sxs-lookup"><span data-stu-id="b6023-267">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="b6023-268">Office 365 Enterprise E5 (SfB Plan2、Exchange Plan2、Teams、電話システムなど)</span><span class="sxs-lookup"><span data-stu-id="b6023-268">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="b6023-269">オプションのライセンス:</span><span class="sxs-lookup"><span data-stu-id="b6023-269">Optional licenses:</span></span> 

- <span data-ttu-id="b6023-270">通話プラン</span><span class="sxs-lookup"><span data-stu-id="b6023-270">Calling Plan</span></span> 
- <span data-ttu-id="b6023-271">電話会議</span><span class="sxs-lookup"><span data-stu-id="b6023-271">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="b6023-272">ユーザーが Skype for Business Online に所属していることを確認する</span><span class="sxs-lookup"><span data-stu-id="b6023-272">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="b6023-273">直接ルーティングを使用するには、ユーザーが Skype for Business Online を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6023-273">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="b6023-274">これを確認するには、RegistrarPool パラメーターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6023-274">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="b6023-275">Infra.lync.com ドメインに値が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6023-275">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="b6023-276">リモート PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="b6023-276">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="b6023-277">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6023-277">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="b6023-278">電話番号を設定し、エンタープライズボイスとボイスメールを有効にする</span><span class="sxs-lookup"><span data-stu-id="b6023-278">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="b6023-279">ユーザーを作成してライセンスを割り当てたら、次の手順として、電話番号とボイスメールを構成します。</span><span class="sxs-lookup"><span data-stu-id="b6023-279">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="b6023-280">これは、1つの手順で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b6023-280">This can be done in one step.</span></span> 

<span data-ttu-id="b6023-281">電話番号を追加してボイスメールを有効にするには:</span><span class="sxs-lookup"><span data-stu-id="b6023-281">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="b6023-282">リモート PowerShell セッションに接続します。</span><span class="sxs-lookup"><span data-stu-id="b6023-282">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="b6023-283">コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b6023-283">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="b6023-284">たとえば、"Spencer Low" というユーザーの電話番号を追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6023-284">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="b6023-285">使用される電話番号は、国コードを含む完全な電子電話番号として構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6023-285">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="b6023-286">ユーザーの電話番号がオンプレミスで管理されている場合は、オンプレミスの Skype for Business 管理シェルまたはコントロールパネルを使用して、ユーザーの電話番号を構成します。</span><span class="sxs-lookup"><span data-stu-id="b6023-286">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="b6023-287">音声ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="b6023-287">Configure Voice Routing</span></span> 

<span data-ttu-id="b6023-288">Microsoft 電話システムには、以下に基づいて特定の SBC に通話を送信することができるルーティングメカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="b6023-288">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="b6023-289">"番号パターン" と呼ばれる</span><span class="sxs-lookup"><span data-stu-id="b6023-289">Called number pattern</span></span> 
- <span data-ttu-id="b6023-290">通話を発信している番号パターンと、特定のユーザー</span><span class="sxs-lookup"><span data-stu-id="b6023-290">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="b6023-291">SBCs は、アクティブなバックアップとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6023-291">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="b6023-292">つまり、この数値パターンに対してアクティブとして構成されている SBC、または数値パターンと特定のユーザーを使用できない場合、通話はバックアップ SBC にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b6023-292">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="b6023-293">通話ルーティングは、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-293">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="b6023-294">音声ルーティングポリシー– PSTN 使用のコンテナー。ユーザーまたは複数のユーザーに割り当てることができる</span><span class="sxs-lookup"><span data-stu-id="b6023-294">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="b6023-295">PSTN 使用状況–ボイスルートと PSTN 使用のコンテナー。異なる音声ルーティングポリシーで共有できる</span><span class="sxs-lookup"><span data-stu-id="b6023-295">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="b6023-296">ボイスルーティング–番号パターンとオンライン PSTN ゲートウェイのセットを使用して、通話番号がパターンと一致する通話に使用する</span><span class="sxs-lookup"><span data-stu-id="b6023-296">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="b6023-297">オンライン PSTN ゲートウェイ: SBC へのポインターでは、(PAI () forward Identity (PAI) または好ましいコーデックなど、SBC 経由で通話を発信するときに適用される構成も保存します。音声ルートに追加できます</span><span class="sxs-lookup"><span data-stu-id="b6023-297">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="b6023-298">単一の PSTN 使用を使用した音声ルーティングポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="b6023-298">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="b6023-299">次の図は、通話フローのボイスルーティングポリシーの2つの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="b6023-299">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="b6023-300">**通話フロー 1 (左側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx を呼び出した場合、通話は SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b6023-300">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="b6023-301">Sbc1.contoso.biz と sbc2.contoso.biz のどちらも使用できない場合は、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-301">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="b6023-302">**通話フロー 2 (右側):** ユーザーが + 1 425 XXX XX xx または + 1 206 XXX XX xx への通話を発信した場合、通話はまず SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b6023-302">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="b6023-303">どちらの SBC も使用できない場合は、優先度の低いルートが試されます (sbc3.contoso.biz と sbc4.contoso.biz)。</span><span class="sxs-lookup"><span data-stu-id="b6023-303">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="b6023-304">利用可能な SBCs がない場合は、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-304">If none of the SBCs are available, the call is dropped.</span></span> 

![ボイスルーティングポリシーの例を示しています](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="b6023-306">どちらの例でも、ボイスルートには優先順位が割り当てられていますが、ルートの SBCs はランダムな順序で試行されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-306">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b6023-307">ユーザーに Microsoft の通話プランライセンスも付与されていない限り、そのパターンに一致する番号 (1 425 XXX XX XX または + 1 206 XXX XX xx) は、この構成の例では削除されません。</span><span class="sxs-lookup"><span data-stu-id="b6023-307">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="b6023-308">ユーザーが通話プランライセンスを持っている場合は、Microsoft 通話プランのポリシーに従って、通話が自動的にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b6023-308">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="b6023-309">Microsoft 通話プランは、Microsoft 通話プランライセンスを持つすべてのユーザーに対して、最後のルートとして自動的に適用され、追加の通話ルーティング構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b6023-309">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="b6023-310">次の図に示す例では、すべての米国およびカナダの電話番号に通話を送信するための音声ルートが追加されています (通話は、番号パターン + 1 XXX XXX XX XX) に移動します。</span><span class="sxs-lookup"><span data-stu-id="b6023-310">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![ボイスルーティングポリシーを3番目のルートとともに示しています](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="b6023-312">その他のすべての通話では、ユーザーに両方のライセンス (Microsoft Phone システムと Microsoft 通話プラン) がある場合、自動ルートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-312">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="b6023-313">管理者が作成したオンラインボイスルートの番号パターンと一致しない場合は、Microsoft 通話プランを使ってルーティングします。</span><span class="sxs-lookup"><span data-stu-id="b6023-313">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="b6023-314">ユーザーが Microsoft 電話システムのみを使用している場合は、一致するルールがないため、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-314">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b6023-315">ルート "Other + 1" の Priority の値は、この例では関係ありません。パターンは1つだけであり、1 XXX XXX XX XX と一致します。</span><span class="sxs-lookup"><span data-stu-id="b6023-315">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="b6023-316">ユーザーが + 1 324 567 89 89 に通話を発信し、sbc5.contoso.biz と sbc6.contoso.biz の両方を利用できない場合は、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-316">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="b6023-317">次の表は、3つのボイスルートを使った構成をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="b6023-317">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="b6023-318">この例では、3つのルートすべてが同じ PSTN 使用状況 "US とカナダ" に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6023-318">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="b6023-319">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="b6023-319">**PSTN usage**</span></span>|<span data-ttu-id="b6023-320">**ボイスルート**</span><span class="sxs-lookup"><span data-stu-id="b6023-320">**Voice route**</span></span>|<span data-ttu-id="b6023-321">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="b6023-321">**Number pattern**</span></span>|<span data-ttu-id="b6023-322">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="b6023-322">**Priority**</span></span>|<span data-ttu-id="b6023-323">**SBC**</span><span class="sxs-lookup"><span data-stu-id="b6023-323">**SBC**</span></span>|<span data-ttu-id="b6023-324">**説明**</span><span class="sxs-lookup"><span data-stu-id="b6023-324">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b6023-325">米国限定</span><span class="sxs-lookup"><span data-stu-id="b6023-325">US only</span></span>|<span data-ttu-id="b6023-326">"レドモンド 1"</span><span class="sxs-lookup"><span data-stu-id="b6023-326">"Redmond 1"</span></span>|<span data-ttu-id="b6023-327">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="b6023-327">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b6023-328">1</span><span class="sxs-lookup"><span data-stu-id="b6023-328">1</span></span>|<span data-ttu-id="b6023-329">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-329">sbc1.contoso.biz</span></span><br/><span data-ttu-id="b6023-330">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-330">sbc2.contoso.biz</span></span>|<span data-ttu-id="b6023-331">呼び出された数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート</span><span class="sxs-lookup"><span data-stu-id="b6023-331">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b6023-332">米国限定</span><span class="sxs-lookup"><span data-stu-id="b6023-332">US only</span></span>|<span data-ttu-id="b6023-333">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="b6023-333">"Redmond 2"</span></span>|<span data-ttu-id="b6023-334">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="b6023-334">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b6023-335">両面</span><span class="sxs-lookup"><span data-stu-id="b6023-335">2</span></span>|<span data-ttu-id="b6023-336">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-336">sbc3.contoso.biz</span></span><br/><span data-ttu-id="b6023-337">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-337">sbc4.contoso.biz</span></span>|<span data-ttu-id="b6023-338">呼び出した数値 + 1 425 XXX XX XX または + 1 206 XXX XX xx のバックアップルート</span><span class="sxs-lookup"><span data-stu-id="b6023-338">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b6023-339">米国限定</span><span class="sxs-lookup"><span data-stu-id="b6023-339">US only</span></span>|<span data-ttu-id="b6023-340">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="b6023-340">"Other +1"</span></span>|<span data-ttu-id="b6023-341">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="b6023-341">^\\+1(\d{10})$</span></span>|<span data-ttu-id="b6023-342">3</span><span class="sxs-lookup"><span data-stu-id="b6023-342">3</span></span>|<span data-ttu-id="b6023-343">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-343">sbc5.contoso.biz</span></span><br/><span data-ttu-id="b6023-344">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-344">sbc6.contoso.biz</span></span>|<span data-ttu-id="b6023-345">"発信番号" のルート + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)</span><span class="sxs-lookup"><span data-stu-id="b6023-345">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="b6023-346">すべてのルートは、PSTN の使用状況 "US およびカナダ" と関連付けられ、PSTN の使用状況はボイスルーティングポリシー "US のみ" に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="b6023-346">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="b6023-347">この例では、ボイスルーティングポリシーがユーザー Spencer Low に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="b6023-347">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="b6023-348">通話ルートの例</span><span class="sxs-lookup"><span data-stu-id="b6023-348">Examples of call routes</span></span>

<span data-ttu-id="b6023-349">次の例では、ルート、PSTN の使用状況、ルーティングポリシーを構成する方法を示しています。これにより、ポリシーがユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b6023-349">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="b6023-350">**手順 1:**「US とカナダ」という PSTN の使用を作成します。</span><span class="sxs-lookup"><span data-stu-id="b6023-350">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="b6023-351">Skype for Business リモート PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6023-351">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="b6023-352">次のように入力して使用が作成されたことを検証します。</span><span class="sxs-lookup"><span data-stu-id="b6023-352">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="b6023-353">これは、切り捨てられる可能性がある名前のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="b6023-353">Which returns a list of names that may be truncated:</span></span>
```
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="b6023-354">次の例では、PowerShell コマンド`(Get-CSOnlinePSTNUsage).usage`を実行して完全な名前を表示できます (トランケートされません)。</span><span class="sxs-lookup"><span data-stu-id="b6023-354">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

<span data-ttu-id="b6023-355">**手順 2:** Skype for Business Online の PowerShell セッションで、前の表で説明したように、Redmond 1、レドモンド2、その他の + 1 の3つのルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6023-355">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="b6023-356">"Redmond 1" ルートを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6023-356">To create the "Redmond 1" route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b6023-357">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b6023-357">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="b6023-358">レドモンド2ルートを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6023-358">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b6023-359">他の + 1 ルートを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6023-359">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="b6023-360">数値 Pattern 属性の正規表現が有効な式であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-360">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="b6023-361">次の web サイトを使ってテストできます。[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="b6023-361">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="b6023-362">場合によっては、すべての通話を同じ SBC にルーティングする必要があります。-番号パターン ". \*" を使用してください。</span><span class="sxs-lookup"><span data-stu-id="b6023-362">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

<span data-ttu-id="b6023-363">すべての通話を同じ SBC にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="b6023-363">Route all calls to same SBC.</span></span>

```
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="b6023-364">次の`Get-CSOnlineVoiceRoute`ようなオプションを使用して PowerShell コマンドを実行して、ルートが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-364">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="b6023-365">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b6023-365">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="b6023-366">この例では、ルート "Other + 1" は優先度4を自動的に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="b6023-366">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="b6023-367">**手順 3:** ボイスルーティングポリシーを「US 専用」にして、「US とカナダ」という PSTN 使用のポリシーに追加します。</span><span class="sxs-lookup"><span data-stu-id="b6023-367">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="b6023-368">Skype for Business Online の PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6023-368">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="b6023-369">結果は、次の例のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-369">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="b6023-370">**手順 4:** Spencer には、PowerShell を使用してボイスルーティングポリシーを低いユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="b6023-370">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

<span data-ttu-id="b6023-371">Skype for Business Online の PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6023-371">In a PowerShell session in Skype for Business Online, type:</span></span>

```
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="b6023-372">このコマンドを入力して、ポリシーの割り当てを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-372">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="b6023-373">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b6023-373">Which returns:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="b6023-374">複数の PSTN 使用を使用した音声ルーティングポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="b6023-374">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="b6023-375">以前に作成した音声ルーティングポリシーでは、米国とカナダでの電話番号への通話のみが許可されています。 Microsoft 通話プランライセンスもユーザーに割り当てられている場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="b6023-375">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="b6023-376">次の例では、"制限なし" という音声ルーティングポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b6023-376">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="b6023-377">このポリシーでは、前の例で作成した PSTN の使用状況 "US and カナダ" も再利用され、新しい PSTN の利用状況 "国際" が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-377">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="b6023-378">これにより、すべての通話が SBCs sbc2.contoso.biz と sbc5.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b6023-378">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="b6023-379">以下の例では、ユーザー "John 森" に米国限定のポリシーが割り当てられていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b6023-379">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="b6023-380">Spencer 安値–米国とカナダの番号のみに許可されています。</span><span class="sxs-lookup"><span data-stu-id="b6023-380">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="b6023-381">Redmond の番号範囲に発信する場合は、特定の SBC のセットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6023-381">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="b6023-382">米国以外の番号は、通話プランライセンスがユーザーに割り当てられていない限り、ルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="b6023-382">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="b6023-383">John 森–任意の番号に通話を発信できます。</span><span class="sxs-lookup"><span data-stu-id="b6023-383">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="b6023-384">Redmond の番号範囲に発信する場合は、特定の SBC のセットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6023-384">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="b6023-385">米国以外の番号は、sbc2.contoso.biz と sbc5.contoso.biz 経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b6023-385">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![ユーザー Spencer Low に割り当てられている音声ルーティングポリシーを表示します](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="b6023-387">その他のすべての通話では、ユーザーに両方のライセンス (Microsoft Phone システムと Microsoft 通話プラン) がある場合、自動ルートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-387">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="b6023-388">管理者が作成したオンラインボイスルートの番号パターンと一致しない場合は、Microsoft 通話プランを使ってルーティングします。</span><span class="sxs-lookup"><span data-stu-id="b6023-388">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="b6023-389">ユーザーが Microsoft 電話システムのみを使用している場合は、一致するルールがないため、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-389">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![ユーザー John 森に割り当てられているボイスルーティングポリシーを示しています](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="b6023-391">次の表は、ルーティングポリシーの "制限なし" を使用しています。</span><span class="sxs-lookup"><span data-stu-id="b6023-391">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="b6023-392">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="b6023-392">**PSTN usage**</span></span>|<span data-ttu-id="b6023-393">**ボイスルート**</span><span class="sxs-lookup"><span data-stu-id="b6023-393">**Voice route**</span></span>|<span data-ttu-id="b6023-394">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="b6023-394">**Number pattern**</span></span>|<span data-ttu-id="b6023-395">**[Priority]**</span><span class="sxs-lookup"><span data-stu-id="b6023-395">**Priority**</span></span>|<span data-ttu-id="b6023-396">**SBC**</span><span class="sxs-lookup"><span data-stu-id="b6023-396">**SBC**</span></span>|<span data-ttu-id="b6023-397">**説明**</span><span class="sxs-lookup"><span data-stu-id="b6023-397">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b6023-398">米国限定</span><span class="sxs-lookup"><span data-stu-id="b6023-398">US Only</span></span>|<span data-ttu-id="b6023-399">"レドモンド 1"</span><span class="sxs-lookup"><span data-stu-id="b6023-399">"Redmond 1"</span></span>|<span data-ttu-id="b6023-400">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="b6023-400">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b6023-401">1</span><span class="sxs-lookup"><span data-stu-id="b6023-401">1</span></span>|<span data-ttu-id="b6023-402">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-402">sbc1.contoso.biz</span></span><br/><span data-ttu-id="b6023-403">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-403">sbc2.contoso.biz</span></span>|<span data-ttu-id="b6023-404">呼び出し先の番号 + 1 425 XXX XX XX または + 1 206 XXX XX xx のアクティブルート</span><span class="sxs-lookup"><span data-stu-id="b6023-404">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b6023-405">米国限定</span><span class="sxs-lookup"><span data-stu-id="b6023-405">US Only</span></span>|<span data-ttu-id="b6023-406">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="b6023-406">"Redmond 2"</span></span>|<span data-ttu-id="b6023-407">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="b6023-407">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="b6023-408">両面</span><span class="sxs-lookup"><span data-stu-id="b6023-408">2</span></span>|<span data-ttu-id="b6023-409">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-409">sbc3.contoso.biz</span></span><br/><span data-ttu-id="b6023-410">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-410">sbc4.contoso.biz</span></span>|<span data-ttu-id="b6023-411">呼び出し先の番号のバックアップルート + 1 425 XXX XX XX または + 1 206 XXX XX xx</span><span class="sxs-lookup"><span data-stu-id="b6023-411">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="b6023-412">米国限定</span><span class="sxs-lookup"><span data-stu-id="b6023-412">US Only</span></span>|<span data-ttu-id="b6023-413">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="b6023-413">"Other +1"</span></span>|<span data-ttu-id="b6023-414">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="b6023-414">^\\+1(\d{10})$</span></span>|<span data-ttu-id="b6023-415">3</span><span class="sxs-lookup"><span data-stu-id="b6023-415">3</span></span>|<span data-ttu-id="b6023-416">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-416">sbc5.contoso.biz</span></span><br/><span data-ttu-id="b6023-417">sbc6> contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-417">sbc6>.contoso.biz</span></span>|<span data-ttu-id="b6023-418">呼び出し先の番号のルーティング + 1 XXX XXX XX XX (+ 1 425 XXX XX xx または + 1 206 XXX XX xx)</span><span class="sxs-lookup"><span data-stu-id="b6023-418">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="b6023-419">International</span><span class="sxs-lookup"><span data-stu-id="b6023-419">International</span></span>|<span data-ttu-id="b6023-420">International</span><span class="sxs-lookup"><span data-stu-id="b6023-420">International</span></span>|<span data-ttu-id="b6023-421">\d +</span><span class="sxs-lookup"><span data-stu-id="b6023-421">\d+</span></span>|<span data-ttu-id="b6023-422">4</span><span class="sxs-lookup"><span data-stu-id="b6023-422">4</span></span>|<span data-ttu-id="b6023-423">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-423">sbc2.contoso.biz</span></span><br/><span data-ttu-id="b6023-424">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="b6023-424">sbc5.contoso.biz</span></span>|<span data-ttu-id="b6023-425">任意の番号パターンのルート</span><span class="sxs-lookup"><span data-stu-id="b6023-425">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="b6023-426">ボイスルーティングポリシーの PSTN 使用の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="b6023-426">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="b6023-427">使用状況は順番に適用され、最初の使用で一致が見つかった場合は、他の使用法は評価されません。</span><span class="sxs-lookup"><span data-stu-id="b6023-427">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="b6023-428">PSTN の使用は、PSTN の使用の後に「米国専用」として設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6023-428">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="b6023-429">PSTN の使用順序を変更するには、 `Set-CSOnlineVoiceRoutingPolicy`コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b6023-429">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="b6023-430">たとえば、"US" と "カナダ" の順序を "第 1" と "海外" の順に変更するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b6023-430">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="b6023-431">"Other + 1" と "海外" のボイスルートの優先度は、自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b6023-431">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="b6023-432">"Redmond 1" と "レドモンド 2" よりも優先順位が低い場合は、問題ありません。</span><span class="sxs-lookup"><span data-stu-id="b6023-432">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="b6023-433">ユーザー John 森のボイスルーティングポリシーの例</span><span class="sxs-lookup"><span data-stu-id="b6023-433">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="b6023-434">PSTN の使用方法として、"インターナショナル"、音声ルート "インターナショナル"、"ボイスルーティングポリシー" (制限なし)、ユーザーを "John 森" に割り当てる手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b6023-434">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


<span data-ttu-id="b6023-435">**手順 1**: PSTN 使用量「国際」を作成します。</span><span class="sxs-lookup"><span data-stu-id="b6023-435">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="b6023-436">Skype for Business Online のリモート PowerShell セッションで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b6023-436">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="b6023-437">**手順 2**: 新しいボイスルート "国際" を作成します。</span><span class="sxs-lookup"><span data-stu-id="b6023-437">**Step 2**:  Create the new voice route "International."</span></span>

```
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="b6023-438">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b6023-438">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="b6023-439">**手順 3**: 音声ルーティングポリシーを作成する "制限なし"。</span><span class="sxs-lookup"><span data-stu-id="b6023-439">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="b6023-440">PSTN の利用状況 "レドモンド 1" と "Redmond" は、電話番号 "+ 1 425 XXX XX XX" と "+ 1 206 XXX XX XX" への通話に対する特別な処理を、ローカルまたはオンプレミスの通話として維持するために、この音声ルーティングポリシーで再利用されています。</span><span class="sxs-lookup"><span data-stu-id="b6023-440">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

   ```
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

<span data-ttu-id="b6023-441">PSTN の使用順序に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b6023-441">Take note of the order of PSTN Usages:</span></span>

<span data-ttu-id="b6023-442">a.</span><span class="sxs-lookup"><span data-stu-id="b6023-442">a.</span></span> <span data-ttu-id="b6023-443">次の例のように、利用状況を設定して、"+ 1 425 XXX XX XX" という数値を指定した場合は、通話は "US およびカナダ" の使用に設定され、特殊なルーティングロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-443">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="b6023-444">つまり、sbc1.contoso.biz と sbc2.contoso.biz を使用して通話がルーティングされ、次にバックアップルートとして sbc3.contoso.biz と sbc4.contoso.biz が送信されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-444">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

<span data-ttu-id="b6023-445">b.</span><span class="sxs-lookup"><span data-stu-id="b6023-445">b.</span></span> <span data-ttu-id="b6023-446">"国際" という PSTN の使用が "US とカナダ" よりも前にある場合は、ルーティングロジックの一部として、+ 1 425 XXX XX XX への通話が sbc2.contoso.biz と sbc5.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b6023-446">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="b6023-447">コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="b6023-447">Enter the command:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

<span data-ttu-id="b6023-448">戻り値</span><span class="sxs-lookup"><span data-stu-id="b6023-448">Which returns</span></span>

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

<span data-ttu-id="b6023-449">**手順 4**: 次のコマンドを使用して、ボイスルーティングポリシーをユーザーの "John 森" に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b6023-449">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="b6023-450">次に、コマンドを使用して課題を確認します。</span><span class="sxs-lookup"><span data-stu-id="b6023-450">Then verify the assignment using the command:</span></span> 

```
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="b6023-451">戻り値:</span><span class="sxs-lookup"><span data-stu-id="b6023-451">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="b6023-452">結果として、John 森の通話に適用されるボイスポリシーは無制限であり、米国、カナダ、国際通話で利用可能な通話ルーティングのロジックに従うことになります。</span><span class="sxs-lookup"><span data-stu-id="b6023-452">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="b6023-453">Microsoft Teams で通話を確実に行うためにチームのみのモードをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="b6023-453">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="b6023-454">直接ルーティングを使うには、チームクライアントで着信通話を確実にするために、ユーザーが Teams 専用モードになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6023-454">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="b6023-455">ユーザーをチームのみのモードに配置するには、TeamsUpgradePolicy の "UpgradeToTeams" インスタンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b6023-455">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="b6023-456">組織で Skype for Business Server または Skype for Business Online を使用している場合は、次の記事を参照してください。 Skype と Teams の間の相互運用性については、「 [skype For business でチームを使用する](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6023-456">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information interoperability between Skype and Teams: [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 

## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="b6023-457">ボイスメールに直接通話を送信するように設定する</span><span class="sxs-lookup"><span data-stu-id="b6023-457">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="b6023-458">ダイレクトルーティングを使うと、ユーザの通話を終了してユーザのボイスメールに直接送ることができます。</span><span class="sxs-lookup"><span data-stu-id="b6023-458">Direct Routing allows you to end the call to a user and send it directly to the users' voicemail.</span></span> <span data-ttu-id="b6023-459">直接ボイスメールに通話を送信するには、符号化 = app: ボイスメールを要求 URI ヘッダーに接続してください。</span><span class="sxs-lookup"><span data-stu-id="b6023-459">If you want to send the call directly to voicemail, please attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="b6023-460">たとえば、"sip: user@yourdomain、不透明 = アプリ: ボイスメール" です。</span><span class="sxs-lookup"><span data-stu-id="b6023-460">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span>
<span data-ttu-id="b6023-461">この場合、Teams ユーザーは呼び出し通知を受信しません。通話はユーザーのボイスメールに直接接続されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-461">In this case the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a><span data-ttu-id="b6023-462">送信および着信通話の代わりの形式に対して、発信者と着信者の番号を変換する</span><span class="sxs-lookup"><span data-stu-id="b6023-462">Translate caller and callee numbers for outbound and inbound calls to an alternate format</span></span>

<span data-ttu-id="b6023-463">テナント管理者は、作成したパターンに基づいて、発信または着信の呼び出し先または着信者番号を変更して、SBCs との相互運用性を実現することができます。</span><span class="sxs-lookup"><span data-stu-id="b6023-463">Sometimes tenant administrators may want to change the callee or caller number for outbound and/or inbound calls based on the patterns they created to ensure interoperability with SBCs.</span></span> <span data-ttu-id="b6023-464">電話番号の翻訳ルールポリシーを設定して、呼び出し元または発信者番号を別の形式に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="b6023-464">You can set a Number Translation Rules policy to translate callee or caller numbers to an alternate format.</span></span> <span data-ttu-id="b6023-465">ポリシーを使用して、次のような数値を翻訳できます。</span><span class="sxs-lookup"><span data-stu-id="b6023-465">You can use the policy to translate numbers for the following:</span></span>

- <span data-ttu-id="b6023-466">着信通話: PSTN エンドポイントからチームクライアント (呼び出し元) への通話。</span><span class="sxs-lookup"><span data-stu-id="b6023-466">Inbound calls: Calls from a PSTN endpoint (caller) to a Teams client (callee).</span></span>
- <span data-ttu-id="b6023-467">発信通話: チームクライアント (発信者) から PSTN エンドポイント (呼び出し先) への通話。</span><span class="sxs-lookup"><span data-stu-id="b6023-467">Outbound calls: Calls from a Teams client (caller) to a PSTN endpoint (callee).</span></span>

<span data-ttu-id="b6023-468">ポリシーは、SBC レベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-468">The policy is applied at the SBC level.</span></span> <span data-ttu-id="b6023-469">複数の翻訳ルールを SBC に割り当てることができます。これは、PowerShell でそれらをリストしたときに表示される順序で適用されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-469">You can assign multiple translation rules to a SBC, which are applied in the order that they appear when you list them in PowerShell.</span></span> <span data-ttu-id="b6023-470">ポリシーのルールの順序を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6023-470">You can also change the order of the rules in the policy.</span></span>

<span data-ttu-id="b6023-471">数値操作ルールを作成、変更、表示、削除するには、TeamsTranslationRule、TeamsTranslationRule、TeamsTranslationRule、および TeamsTranslationRule コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6023-471">To create, modify, view, and delete number manipulation rules, use the New-TeamsTranslationRule, Set-TeamsTranslationRule, Get-TeamsTranslationRule, and Remove-TeamsTranslationRule cmdlets.</span></span>

<span data-ttu-id="b6023-472">SBCs で番号操作ルールを割り当て、構成、および一覧表示するには、、、、、、、および```OutboundPSTNNumberTranslationRulesList```パラメーターを```InboundTeamsNumberTranslationRules```使用```InboundPSTNNumberTranslationRules```し```OutboundTeamsNumberTranslationRules```て```OutboundPSTNNumberTranslationRules```、 ```InboundTeamsNumberTranslationRulesList```CSOnlinePSTNGateway ```InboundPSTNNumberTranslationRulesList```と```OutboundTeamsNumberTranslationRulesList``` [CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway)コマンドレットを併用します。 [](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)</span><span class="sxs-lookup"><span data-stu-id="b6023-472">To assign, configure, and list number manipulation rules on SBCs, use the [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) and [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlets together with the  ```InboundTeamsNumberTranslationRules```, ```InboundPSTNNumberTranslationRules```, ```OutboundTeamsNumberTranslationRules```, ```OutboundPSTNNumberTranslationRules```, ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList```, ```OutboundTeamsNumberTranslationRulesList```, and ```OutboundPSTNNumberTranslationRulesList``` parameters.</span></span>

### <a name="examples"></a><span data-ttu-id="b6023-473">例</span><span class="sxs-lookup"><span data-stu-id="b6023-473">Examples</span></span>

#### <a name="example-sbc-configuration"></a><span data-ttu-id="b6023-474">SBC 構成の例</span><span class="sxs-lookup"><span data-stu-id="b6023-474">Example SBC configuration</span></span>

<span data-ttu-id="b6023-475">このシナリオの例では、 ```New-CsOnlinePSTNGateway```コマンドレットを実行して、次の SBC 構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="b6023-475">For the example scenarios, we run the ```New-CsOnlinePSTNGateway``` cmdlet to create the following SBC configuration.</span></span>

```
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

<span data-ttu-id="b6023-476">SBC に割り当てられている翻訳ルールは、次の表のようにまとめられています。</span><span class="sxs-lookup"><span data-stu-id="b6023-476">The translation rules assigned to the SBC are summarized in the following table.</span></span>

|<span data-ttu-id="b6023-477">名前</span><span class="sxs-lookup"><span data-stu-id="b6023-477">Name</span></span>  |<span data-ttu-id="b6023-478">実線</span><span class="sxs-lookup"><span data-stu-id="b6023-478">Pattern</span></span> |<span data-ttu-id="b6023-479">変換</span><span class="sxs-lookup"><span data-stu-id="b6023-479">Translation</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b6023-480">AddPlus1</span><span class="sxs-lookup"><span data-stu-id="b6023-480">AddPlus1</span></span>     |<span data-ttu-id="b6023-481">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="b6023-481">^(\d{10})$</span></span>          |<span data-ttu-id="b6023-482">+1$1</span><span class="sxs-lookup"><span data-stu-id="b6023-482">+1$1</span></span>          |
|<span data-ttu-id="b6023-483">AddE164SeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="b6023-483">AddE164SeattleAreaCode</span></span>      |<span data-ttu-id="b6023-484">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="b6023-484">^(\d{4})$</span></span>          | <span data-ttu-id="b6023-485">+ 1206555 $ 1</span><span class="sxs-lookup"><span data-stu-id="b6023-485">+1206555$1</span></span>         |
|<span data-ttu-id="b6023-486">AddSeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="b6023-486">AddSeattleAreaCode</span></span>    |<span data-ttu-id="b6023-487">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="b6023-487">^(\d{4})$</span></span>          | <span data-ttu-id="b6023-488">425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="b6023-488">425555$1</span></span>         |
|<span data-ttu-id="b6023-489">StripPlus1</span><span class="sxs-lookup"><span data-stu-id="b6023-489">StripPlus1</span></span>    |<span data-ttu-id="b6023-490">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="b6023-490">^+1(\d{10})$</span></span>          | <span data-ttu-id="b6023-491">$1</span><span class="sxs-lookup"><span data-stu-id="b6023-491">$1</span></span>         |

<span data-ttu-id="b6023-492">このようなシナリオでは、Alice と Bob の2人のユーザーがいます。</span><span class="sxs-lookup"><span data-stu-id="b6023-492">In these example scenarios, we have two users, Alice and Bob.</span></span> <span data-ttu-id="b6023-493">アリスは Teams ユーザーで、この番号は + 1 206 555 0100 です。</span><span class="sxs-lookup"><span data-stu-id="b6023-493">Alice is a Teams user and her number is +1 206 555 0100.</span></span> <span data-ttu-id="b6023-494">ボブは PSTN ユーザーで、その番号は + 1 425 555 0100 です。</span><span class="sxs-lookup"><span data-stu-id="b6023-494">Bob is a PSTN user and his number is +1 425 555 0100.</span></span>

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a><span data-ttu-id="b6023-495">例 1:10 桁の番号への着信通話</span><span class="sxs-lookup"><span data-stu-id="b6023-495">Example 1: Inbound call to a ten-digit number</span></span>

<span data-ttu-id="b6023-496">ボブの10桁の数字以外の番号を使用してアリスが通話を発信します。</span><span class="sxs-lookup"><span data-stu-id="b6023-496">Bob calls Alice using a non-E.164 ten-digit number.</span></span> <span data-ttu-id="b6023-497">ボブは、アリスに連絡するために2065550100をダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="b6023-497">Bob dials 2065550100 to reach Alice.</span></span>
<span data-ttu-id="b6023-498">SBC は、RequestURI で2065550100を使用し、From ヘッダーではヘッダーと4255550100を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6023-498">SBC uses 2065550100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="b6023-499">Header</span><span class="sxs-lookup"><span data-stu-id="b6023-499">Header</span></span>  |<span data-ttu-id="b6023-500">翻訳元</span><span class="sxs-lookup"><span data-stu-id="b6023-500">Original</span></span> |<span data-ttu-id="b6023-501">翻訳済みヘッダー</span><span class="sxs-lookup"><span data-stu-id="b6023-501">Translated header</span></span> |<span data-ttu-id="b6023-502">パラメーターとルールの適用</span><span class="sxs-lookup"><span data-stu-id="b6023-502">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b6023-503">RequestURI</span><span class="sxs-lookup"><span data-stu-id="b6023-503">RequestURI</span></span>  |<span data-ttu-id="b6023-504">Sip:2065550100@sbc.contoso.com を招待する</span><span class="sxs-lookup"><span data-stu-id="b6023-504">INVITE sip:2065550100@sbc.contoso.com</span></span>|<span data-ttu-id="b6023-505">Sip:+12065550100@sbc.contoso.com を招待する</span><span class="sxs-lookup"><span data-stu-id="b6023-505">INVITE sip:+12065550100@sbc.contoso.com</span></span>|<span data-ttu-id="b6023-506">InboundTeamsNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="b6023-506">InboundTeamsNumberTranslationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="b6023-507">宛先</span><span class="sxs-lookup"><span data-stu-id="b6023-507">TO</span></span>    |<span data-ttu-id="b6023-508">宛先: \<sip:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-508">TO: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-509">宛先: \<sip:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-509">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-510">InboundTeamsNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="b6023-510">InboundTeamsNumberTranlationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="b6023-511">差出人</span><span class="sxs-lookup"><span data-stu-id="b6023-511">FROM</span></span>   |<span data-ttu-id="b6023-512">差出人: \<sip:4255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-512">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-513">差出人: \<sip:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-513">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-514">InboundPSTNNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="b6023-514">InboundPSTNNumberTranslationRulesList ‘AddPlus1’</span></span>|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a><span data-ttu-id="b6023-515">例 2: 4 桁の番号への着信通話</span><span class="sxs-lookup"><span data-stu-id="b6023-515">Example 2: Inbound call to a four-digit number</span></span>

<span data-ttu-id="b6023-516">ボブは、4桁の数字を使って Alice と通話します。</span><span class="sxs-lookup"><span data-stu-id="b6023-516">Bob calls Alice using a four-digit number.</span></span> <span data-ttu-id="b6023-517">ボブは、アリスに連絡するために0100をダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="b6023-517">Bob dials 0100 to reach Alice.</span></span>
<span data-ttu-id="b6023-518">SBC は、RequestURI で0100を使用し、From ヘッダーではヘッダーと4255550100を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6023-518">SBC uses 0100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="b6023-519">Header</span><span class="sxs-lookup"><span data-stu-id="b6023-519">Header</span></span>  |<span data-ttu-id="b6023-520">翻訳元</span><span class="sxs-lookup"><span data-stu-id="b6023-520">Original</span></span> |<span data-ttu-id="b6023-521">翻訳済みヘッダー</span><span class="sxs-lookup"><span data-stu-id="b6023-521">Translated header</span></span> |<span data-ttu-id="b6023-522">パラメーターとルールの適用</span><span class="sxs-lookup"><span data-stu-id="b6023-522">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b6023-523">RequestURI</span><span class="sxs-lookup"><span data-stu-id="b6023-523">RequestURI</span></span>  |<span data-ttu-id="b6023-524">Sip:0100@sbc.contoso.com を招待する</span><span class="sxs-lookup"><span data-stu-id="b6023-524">INVITE sip:0100@sbc.contoso.com</span></span>          |<span data-ttu-id="b6023-525">Sip:+12065550100@sbc.contoso.com を招待する</span><span class="sxs-lookup"><span data-stu-id="b6023-525">INVITE sip:+12065550100@sbc.contoso.com</span></span>           |<span data-ttu-id="b6023-526">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="b6023-526">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>        |
|<span data-ttu-id="b6023-527">宛先</span><span class="sxs-lookup"><span data-stu-id="b6023-527">TO</span></span>    |<span data-ttu-id="b6023-528">宛先: \<sip:0100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-528">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-529">宛先: \<sip:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-529">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-530">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="b6023-530">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>         |
|<span data-ttu-id="b6023-531">差出人</span><span class="sxs-lookup"><span data-stu-id="b6023-531">FROM</span></span>   |<span data-ttu-id="b6023-532">差出人: \<sip:4255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-532">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-533">差出人: \<sip:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-533">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-534">InboundPSTNNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="b6023-534">InboundPSTNNumberTranlationRulesList ‘AddPlus1’</span></span>        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a><span data-ttu-id="b6023-535">例 3:10 桁の番号を使用した発信通話</span><span class="sxs-lookup"><span data-stu-id="b6023-535">Example 3: Outbound call using a ten-digit non-E.164 number</span></span>

<span data-ttu-id="b6023-536">アリスは、10桁の数字を使ってボブを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b6023-536">Alice calls Bob using a ten-digit number.</span></span> <span data-ttu-id="b6023-537">アリスは、425 555 0100 にダイヤルしてボブに連絡します。</span><span class="sxs-lookup"><span data-stu-id="b6023-537">Alice dials 425 555 0100 to reach Bob.</span></span>
<span data-ttu-id="b6023-538">SBC は、Teams と PSTN の両方の10桁の10桁の番号を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="b6023-538">SBC is configured to use non-E.164 ten-digit numbers for both Teams and PSTN users.</span></span>

<span data-ttu-id="b6023-539">このシナリオでは、ダイヤルプランによって電話番号がダイレクトルーティングインターフェイスに送信される前に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-539">In this scenario, a dial plan translates the number before sending it to the Direct Routing interface.</span></span> <span data-ttu-id="b6023-540">アリスが Teams クライアントに 425 555 0100 を入力すると、その番号は国のダイヤルプランによって + 14255550100 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="b6023-540">When Alice enters 425 555 0100 in the Teams client, the number is translated to +14255550100 by the country dial plan.</span></span> <span data-ttu-id="b6023-541">結果として得られる数値は、ダイヤルプランのルールと Teams の翻訳ルールの累積正規化です。</span><span class="sxs-lookup"><span data-stu-id="b6023-541">The resulting numbers are a cumulative normalization of the dial plan rules and Teams translation rules.</span></span> <span data-ttu-id="b6023-542">Teams の翻訳ルールは、ダイヤルプランによって追加された "+ 1" を削除します。</span><span class="sxs-lookup"><span data-stu-id="b6023-542">The Teams translation rules remove the "+1" that was added by the dial plan.</span></span>

|<span data-ttu-id="b6023-543">Header</span><span class="sxs-lookup"><span data-stu-id="b6023-543">Header</span></span>  |<span data-ttu-id="b6023-544">翻訳元</span><span class="sxs-lookup"><span data-stu-id="b6023-544">Original</span></span> |<span data-ttu-id="b6023-545">翻訳済みヘッダー</span><span class="sxs-lookup"><span data-stu-id="b6023-545">Translated header</span></span> |<span data-ttu-id="b6023-546">パラメーターとルールの適用</span><span class="sxs-lookup"><span data-stu-id="b6023-546">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b6023-547">RequestURI</span><span class="sxs-lookup"><span data-stu-id="b6023-547">RequestURI</span></span>  |<span data-ttu-id="b6023-548">Sip:+14255550100@sbc.contoso.com を招待する</span><span class="sxs-lookup"><span data-stu-id="b6023-548">INVITE sip:+14255550100@sbc.contoso.com</span></span>          |<span data-ttu-id="b6023-549">Sip:4255550100@sbc.contoso.com を招待する</span><span class="sxs-lookup"><span data-stu-id="b6023-549">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="b6023-550">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="b6023-550">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>         |
|<span data-ttu-id="b6023-551">宛先</span><span class="sxs-lookup"><span data-stu-id="b6023-551">TO</span></span>    |<span data-ttu-id="b6023-552">宛先: \<sip:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-552">TO: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-553">宛先: \<sip:4255555555@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-553">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-554">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="b6023-554">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>       |
|<span data-ttu-id="b6023-555">差出人</span><span class="sxs-lookup"><span data-stu-id="b6023-555">FROM</span></span>   |<span data-ttu-id="b6023-556">差出人: \<sip:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-556">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-557">差出人: \<sip:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-557">FROM: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-558">Outboundteamsnumber/Ationルールリスト ' StripPlus1 '</span><span class="sxs-lookup"><span data-stu-id="b6023-558">OutboundTeamsNumberTranlationRulesList ‘StripPlus1’</span></span>         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a><span data-ttu-id="b6023-559">例 4: 4 桁以外の番号を使用した発信通話</span><span class="sxs-lookup"><span data-stu-id="b6023-559">Example 4: Outbound call using a four-digit non-E.164 number</span></span>

<span data-ttu-id="b6023-560">アリスは、4桁の数字を使ってボブを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b6023-560">Alice calls Bob using a four-digit number.</span></span> <span data-ttu-id="b6023-561">アリスは、0100を使って、通話から、または連絡先を使ってボブに連絡します。</span><span class="sxs-lookup"><span data-stu-id="b6023-561">Alice uses 0100 to reach Bob from Calls or by using a contact.</span></span>
<span data-ttu-id="b6023-562">SBC は、Teams ユーザーと PSTN ユーザー用に10桁の4桁の番号を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="b6023-562">SBC is configured to use non-E.164 four-digit numbers for Teams users and ten-digit numbers for PSTN users.</span></span> <span data-ttu-id="b6023-563">このシナリオでは、ダイヤルプランは適用されません。</span><span class="sxs-lookup"><span data-stu-id="b6023-563">The dial plan isn't applied in this scenario.</span></span>

|<span data-ttu-id="b6023-564">Header</span><span class="sxs-lookup"><span data-stu-id="b6023-564">Header</span></span>  |<span data-ttu-id="b6023-565">翻訳元</span><span class="sxs-lookup"><span data-stu-id="b6023-565">Original</span></span> |<span data-ttu-id="b6023-566">翻訳済みヘッダー</span><span class="sxs-lookup"><span data-stu-id="b6023-566">Translated header</span></span> |<span data-ttu-id="b6023-567">パラメーターとルールの適用</span><span class="sxs-lookup"><span data-stu-id="b6023-567">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b6023-568">RequestURI</span><span class="sxs-lookup"><span data-stu-id="b6023-568">RequestURI</span></span>  |<span data-ttu-id="b6023-569">Sip:0100@sbc.contoso.com を招待する</span><span class="sxs-lookup"><span data-stu-id="b6023-569">INVITE sip:0100@sbc.contoso.com</span></span>           |<span data-ttu-id="b6023-570">Sip:4255550100@sbc.contoso.com を招待する</span><span class="sxs-lookup"><span data-stu-id="b6023-570">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="b6023-571">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="b6023-571">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>         |
|<span data-ttu-id="b6023-572">宛先</span><span class="sxs-lookup"><span data-stu-id="b6023-572">TO</span></span>    |<span data-ttu-id="b6023-573">宛先: \<sip:0100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-573">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-574">宛先: \<sip:4255555555@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-574">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-575">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="b6023-575">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>       |
|<span data-ttu-id="b6023-576">差出人</span><span class="sxs-lookup"><span data-stu-id="b6023-576">FROM</span></span>   |<span data-ttu-id="b6023-577">差出人: \<sip:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-577">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="b6023-578">差出人: \<sip:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="b6023-578">FROM: \<sip:2065550100@sbc.contoso.com></span></span>| <span data-ttu-id="b6023-579">InboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="b6023-579">InboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span> |

## <a name="see-also"></a><span data-ttu-id="b6023-580">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6023-580">See also</span></span>

[<span data-ttu-id="b6023-581">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="b6023-581">Plan Direct Routing</span></span>](direct-routing-plan.md)
