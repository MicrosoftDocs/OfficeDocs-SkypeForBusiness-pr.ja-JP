---
title: 直接ルーティングを構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: Microsoft 電話システム直接ルーティングを構成する方法について説明します。
ms.openlocfilehash: 4e117cd7e8bdde34a4982408052a1a61aedd00d7
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30353483"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="ad285-103">直接ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="ad285-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="ad285-104">ルーティング、それを計画する方法と展開方法は、直接の利点について説明するのには次のセッションを監視する:[マイクロソフトのチームに直接ルーティング](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="ad285-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="ad285-105">されていない場合は、前提条件の[直接ルーティングの計画](direct-routing-plan.md)が読み込まれ、他の手順を確認する必要があります、Microsoft の電話システムのネットワークを構成する前にします。</span><span class="sxs-lookup"><span data-stu-id="ad285-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="ad285-106">この資料では、マイクロソフト電話システム直接ルーティングを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ad285-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="ad285-107">ペア、サポートされているセッション ボーダー コント ローラー (SBC) に直接ルーティングする方法とを公衆交換電話網 (PSTN) を接続するのには直接ルーティングを使用するマイクロソフトのチームのユーザーを構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ad285-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="ad285-108">この資料で説明した手順を完了するには、管理者には、PowerShell コマンドレットをある程度が必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad285-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="ad285-109">PowerShell を使用の詳細については、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad285-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="ad285-110">SBC が既に設定されている SBC の製造元によって推奨されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad285-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="ad285-111">展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="ad285-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="ad285-112">リボンの通信の展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="ad285-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="ad285-113">マイクロソフト電話システムを構成して、直接ルーティングを使用し、マイクロソフトのチームを次の手順を完了しての優先呼び出し側のクライアントとして設定するユーザーを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad285-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="ad285-114">マイクロソフトの電話システムと SBC のペアし、ペアを検証します。</span><span class="sxs-lookup"><span data-stu-id="ad285-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="ad285-115">直接ルーティング サービスのユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ad285-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="ad285-116">マイクロソフトのチームが、ユーザーの優先呼び出し側のクライアントであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad285-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="ad285-117">電話システムの直接のルーティング サービスに SBC を組み合わせ</span><span class="sxs-lookup"><span data-stu-id="ad285-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="ad285-118">使用すると、接続、または直接ルーティング インターフェイスに SBC とペアにするには次の 3 つの大まかな手順は、次のように。</span><span class="sxs-lookup"><span data-stu-id="ad285-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="ad285-119">PowerShell を使用して、 **Skype**管理センターへの接続します。</span><span class="sxs-lookup"><span data-stu-id="ad285-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="ad285-120">SBC のペア</span><span class="sxs-lookup"><span data-stu-id="ad285-120">Pair the SBC</span></span> 
- <span data-ttu-id="ad285-121">ペアを検証します。</span><span class="sxs-lookup"><span data-stu-id="ad285-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="ad285-122">PowerShell を使用して、オンライン ビジネスの Skype に接続します。</span><span class="sxs-lookup"><span data-stu-id="ad285-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="ad285-123">直接ルーティング インターフェイスに SBC をペアにするには、テナントに接続している PowerShell セッションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad285-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="ad285-124">PowerShell セッションを開くには、するには、 [Windows PowerShell には、コンピューターの設定](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)で説明する手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ad285-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="ad285-125">リモート PowerShell セッションを確立すると後を検証してください、SBC を管理するためにコマンドを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="ad285-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="ad285-126">コマンドを検証するには、入力または PowerShell セッションで次のコピーと貼り付けし Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ad285-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="ad285-127">コマンドでは、ここで示すように、SBC を管理できるようになる 4 つの関数を返します。</span><span class="sxs-lookup"><span data-stu-id="ad285-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="ad285-128">テナントに SBC の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="ad285-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="ad285-129">テナントに SBC とペアに PowerShell セッションで次を入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ad285-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="ad285-130">強くお勧め、SBC の呼び出しの最大制限を設定する SBC のドキュメントで使用されている情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad285-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="ad285-131">制限は、SBC の能力のレベルにある場合に通知をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="ad285-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="ad285-132">FQDN のドメイン部分を除く、テナントに登録されているドメインのいずれかと一致する場合、SBC をペアのみ\*. onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ad285-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="ad285-133">使用して\*. SBC の FQDN 名を onmicrosoft.com ドメイン名がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ad285-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="ad285-134">たとえば、2 つのドメイン名があるとします。</span><span class="sxs-lookup"><span data-stu-id="ad285-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="ad285-135">**contoso**.com</span><span class="sxs-lookup"><span data-stu-id="ad285-135">**contoso**.com</span></span><br/><span data-ttu-id="ad285-136">**contoso**onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="ad285-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="ad285-137">SBC 名の名前の sbc.contoso.com を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad285-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="ad285-138">名 sbc.contoso.abc を持つ SBC のペアにしようとすると、システムは動かせません、このテナントは、ドメインを所有していないようです。</span><span class="sxs-lookup"><span data-stu-id="ad285-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="ad285-139">返します。</span><span class="sxs-lookup"><span data-stu-id="ad285-139">Returns:</span></span>
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
<span data-ttu-id="ad285-140">ペアリング処理中に設定できる追加のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ad285-140">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="ad285-141">前の例では、ただし、のみ、最低限必要なパラメーターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-141">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="ad285-142">次の表のパラメーターの設定で使用できる追加のパラメーターを一覧表示します。`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="ad285-142">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="ad285-143">必須。</span><span class="sxs-lookup"><span data-stu-id="ad285-143">Required?</span></span>|<span data-ttu-id="ad285-144">名前</span><span class="sxs-lookup"><span data-stu-id="ad285-144">Name</span></span>|<span data-ttu-id="ad285-145">説明</span><span class="sxs-lookup"><span data-stu-id="ad285-145">Description</span></span>|<span data-ttu-id="ad285-146">Default</span><span class="sxs-lookup"><span data-stu-id="ad285-146">Default</span></span>|<span data-ttu-id="ad285-147">可能な値</span><span class="sxs-lookup"><span data-stu-id="ad285-147">Possible values</span></span>|<span data-ttu-id="ad285-148">種類と制限</span><span class="sxs-lookup"><span data-stu-id="ad285-148">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad285-149">あり</span><span class="sxs-lookup"><span data-stu-id="ad285-149">Yes</span></span>|<span data-ttu-id="ad285-150">FQDN</span><span class="sxs-lookup"><span data-stu-id="ad285-150">FQDN</span></span>|<span data-ttu-id="ad285-151">SBC の FQDN 名</span><span class="sxs-lookup"><span data-stu-id="ad285-151">The FQDN name of the SBC</span></span> |<span data-ttu-id="ad285-152">なし</span><span class="sxs-lookup"><span data-stu-id="ad285-152">None</span></span>|<span data-ttu-id="ad285-153">NoneFQDN 名、制限は 63 文字</span><span class="sxs-lookup"><span data-stu-id="ad285-153">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="ad285-154">文字列、[コンピューター、ドメイン、サイト、および Ou の Active Directory の名前付け規則](https://support.microsoft.com/help/909264)で許可の文字の一覧</span><span class="sxs-lookup"><span data-stu-id="ad285-154">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="ad285-155">不要</span><span class="sxs-lookup"><span data-stu-id="ad285-155">No</span></span>|<span data-ttu-id="ad285-156">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="ad285-156">MediaBypass</span></span> |<span data-ttu-id="ad285-157">将来使用するために予約されているパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="ad285-157">The parameter reserved for future use.</span></span> <span data-ttu-id="ad285-158">SBC の示されているパラメーターには、メディア バイ パスがサポートされていて、管理者がそれを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad285-158">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="ad285-159">なし</span><span class="sxs-lookup"><span data-stu-id="ad285-159">None</span></span>|<span data-ttu-id="ad285-160">True</span><span class="sxs-lookup"><span data-stu-id="ad285-160">True</span></span><br/><span data-ttu-id="ad285-161">False</span><span class="sxs-lookup"><span data-stu-id="ad285-161">False</span></span>|<span data-ttu-id="ad285-162">ブール型</span><span class="sxs-lookup"><span data-stu-id="ad285-162">Boolean</span></span>|
|<span data-ttu-id="ad285-163">あり</span><span class="sxs-lookup"><span data-stu-id="ad285-163">Yes</span></span>|<span data-ttu-id="ad285-164">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="ad285-164">SipSignallingPort</span></span> |<span data-ttu-id="ad285-165">トランスポート層セキュリティ (TLS) プロトコルを使用して直接ルーティング サービスと通信するために使用するポートをリッスンします。</span><span class="sxs-lookup"><span data-stu-id="ad285-165">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="ad285-166">なし</span><span class="sxs-lookup"><span data-stu-id="ad285-166">None</span></span>|<span data-ttu-id="ad285-167">任意のポート</span><span class="sxs-lookup"><span data-stu-id="ad285-167">Any port</span></span>|<span data-ttu-id="ad285-168">0 から 65535 まで</span><span class="sxs-lookup"><span data-stu-id="ad285-168">0 to 65535</span></span> |
|<span data-ttu-id="ad285-169">不要</span><span class="sxs-lookup"><span data-stu-id="ad285-169">No</span></span>|<span data-ttu-id="ad285-170">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="ad285-170">FailoverTimeSeconds</span></span> |<span data-ttu-id="ad285-171">10 (既定値) に設定すると、10 秒以内に、ゲートウェイが応答しない送信の呼び出しにルーティングされる次の使用可能なトランクです。トランクを追加することはありません、し、呼び出しは自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="ad285-171">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="ad285-172">低速のネットワークとゲートウェイの応答を持つ組織内を可能性があります可能性のある呼び出しが不必要に削除されています。</span><span class="sxs-lookup"><span data-stu-id="ad285-172">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="ad285-173">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="ad285-173">The default value is 10.</span></span>|<span data-ttu-id="ad285-174"> 10</span><span class="sxs-lookup"><span data-stu-id="ad285-174">10</span></span>|<span data-ttu-id="ad285-175">数値</span><span class="sxs-lookup"><span data-stu-id="ad285-175">Number</span></span>|<span data-ttu-id="ad285-176">Int</span><span class="sxs-lookup"><span data-stu-id="ad285-176">Int</span></span>|
|<span data-ttu-id="ad285-177">不要</span><span class="sxs-lookup"><span data-stu-id="ad285-177">No</span></span>|<span data-ttu-id="ad285-178">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="ad285-178">ForwardCallHistory</span></span> |<span data-ttu-id="ad285-179">通話履歴の情報をトランク経由で転送するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad285-179">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="ad285-180">Office 365 の PSTN のプロキシに 2 つのヘッダーが送信が有効な場合: 履歴情報と Referred で。</span><span class="sxs-lookup"><span data-stu-id="ad285-180">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="ad285-181">既定値は**False** ($False) です。</span><span class="sxs-lookup"><span data-stu-id="ad285-181">The default value is **False** ($False).</span></span> |<span data-ttu-id="ad285-182">False</span><span class="sxs-lookup"><span data-stu-id="ad285-182">False</span></span>|<span data-ttu-id="ad285-183">True</span><span class="sxs-lookup"><span data-stu-id="ad285-183">True</span></span><br/><span data-ttu-id="ad285-184">False</span><span class="sxs-lookup"><span data-stu-id="ad285-184">False</span></span>|<span data-ttu-id="ad285-185">ブール型</span><span class="sxs-lookup"><span data-stu-id="ad285-185">Boolean</span></span>|
|<span data-ttu-id="ad285-186">不要</span><span class="sxs-lookup"><span data-stu-id="ad285-186">No</span></span>|<span data-ttu-id="ad285-187">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="ad285-187">ForwardPAI</span></span>|<span data-ttu-id="ad285-188">P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ad285-188">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="ad285-189">PAI ヘッダーがあれば、発信者 ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ad285-189">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="ad285-190">既定値は**False** ($False) です。</span><span class="sxs-lookup"><span data-stu-id="ad285-190">The default value is **False** ($False).</span></span>|<span data-ttu-id="ad285-191">False</span><span class="sxs-lookup"><span data-stu-id="ad285-191">False</span></span>|<span data-ttu-id="ad285-192">True</span><span class="sxs-lookup"><span data-stu-id="ad285-192">True</span></span><br/><span data-ttu-id="ad285-193">False</span><span class="sxs-lookup"><span data-stu-id="ad285-193">False</span></span>|<span data-ttu-id="ad285-194">ブール型</span><span class="sxs-lookup"><span data-stu-id="ad285-194">Boolean</span></span>|
|<span data-ttu-id="ad285-195">不要</span><span class="sxs-lookup"><span data-stu-id="ad285-195">No</span></span>|<span data-ttu-id="ad285-196">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="ad285-196">SendSIPOptions</span></span> |<span data-ttu-id="ad285-197">SBC または SIP オプションを送信しない場合を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad285-197">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="ad285-198">無効にした場合、SBC は、監視と警告のシステムから除外されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-198">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="ad285-199">SIP オプションを有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad285-199">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="ad285-200">既定値は**True**です。</span><span class="sxs-lookup"><span data-stu-id="ad285-200">Default value is **True**.</span></span> |<span data-ttu-id="ad285-201">True</span><span class="sxs-lookup"><span data-stu-id="ad285-201">True</span></span>|<span data-ttu-id="ad285-202">True</span><span class="sxs-lookup"><span data-stu-id="ad285-202">True</span></span><br/><span data-ttu-id="ad285-203">False</span><span class="sxs-lookup"><span data-stu-id="ad285-203">False</span></span>|<span data-ttu-id="ad285-204">ブール型</span><span class="sxs-lookup"><span data-stu-id="ad285-204">Boolean</span></span>|
|<span data-ttu-id="ad285-205">不要</span><span class="sxs-lookup"><span data-stu-id="ad285-205">No</span></span>|<span data-ttu-id="ad285-206">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="ad285-206">MaxConcurrentSessions</span></span> |<span data-ttu-id="ad285-207">警告システムによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-207">Used by alerting system.</span></span> <span data-ttu-id="ad285-208">同時セッションの数が 90% の場合、アラート ・ システム、テナント管理者にアラートを生成の任意の値を設定すると、この値よりも大きいか。</span><span class="sxs-lookup"><span data-stu-id="ad285-208">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="ad285-209">パラメーターが設定されていない場合、アラートは生成されません。</span><span class="sxs-lookup"><span data-stu-id="ad285-209">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="ad285-210">ただし、監視システムは 24 時間ごとの同時セッションの数を報告します。</span><span class="sxs-lookup"><span data-stu-id="ad285-210">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="ad285-211">Null</span><span class="sxs-lookup"><span data-stu-id="ad285-211">Null</span></span>|<span data-ttu-id="ad285-212">Null</span><span class="sxs-lookup"><span data-stu-id="ad285-212">Null</span></span><br/><span data-ttu-id="ad285-213">1 ~ 100,000</span><span class="sxs-lookup"><span data-stu-id="ad285-213">1 to 100,000</span></span> ||
|<span data-ttu-id="ad285-214">不要</span><span class="sxs-lookup"><span data-stu-id="ad285-214">No</span></span>|<span data-ttu-id="ad285-215">有効になっている \*</span><span class="sxs-lookup"><span data-stu-id="ad285-215">Enabled\*</span></span>|<span data-ttu-id="ad285-216">発信呼のこの SBC を有効にする場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-216">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="ad285-217">メンテナンス中または更新中に、SBC を一時的に削除するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ad285-217">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="ad285-218">False</span><span class="sxs-lookup"><span data-stu-id="ad285-218">False</span></span>|<span data-ttu-id="ad285-219">True</span><span class="sxs-lookup"><span data-stu-id="ad285-219">True</span></span><br/><span data-ttu-id="ad285-220">False</span><span class="sxs-lookup"><span data-stu-id="ad285-220">False</span></span>|<span data-ttu-id="ad285-221">ブール型</span><span class="sxs-lookup"><span data-stu-id="ad285-221">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="ad285-222">SBC の組み合わせを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad285-222">Verify the SBC pairing</span></span> 

<span data-ttu-id="ad285-223">接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="ad285-223">Verify the connection:</span></span> 
- <span data-ttu-id="ad285-224">SBCs のペアのリストに、SBC があるかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ad285-224">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="ad285-225">SIP オプションを検証します。</span><span class="sxs-lookup"><span data-stu-id="ad285-225">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="ad285-226">SBCs のペアの一覧に場合は、SBC の検証します。</span><span class="sxs-lookup"><span data-stu-id="ad285-226">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="ad285-227">SBC のペアであることを確認、SBC SBCs のペアのリストに存在リモート PowerShell セッションで次のコマンドを実行しています。`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="ad285-227">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="ad285-228">ペアのゲートウェイは、次の例に示すように、一覧に表示し、パラメーターを*有効*に**は True**の値が表示されることを確認ください。</span><span class="sxs-lookup"><span data-stu-id="ad285-228">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="ad285-229">入力します。</span><span class="sxs-lookup"><span data-stu-id="ad285-229">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="ad285-230">返します。</span><span class="sxs-lookup"><span data-stu-id="ad285-230">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="ad285-231">SIP オプションのフローを検証します。</span><span class="sxs-lookup"><span data-stu-id="ad285-231">Validate SIP Options flow</span></span> 

<span data-ttu-id="ad285-232">送信 SIP オプションを使用しての組み合わせを検証するには、SBC の管理インターフェイスを使用し、SBC がそのオプションのメッセージを 200 OK 応答を受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad285-232">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="ad285-233">受信オプションを見て直接ルーティングでは、SBC の FQDN へのメッセージは、オプションの受信メッセージの連絡先ヘッダー フィールドで構成されている送信 SIP のオプションの送信を開始します。</span><span class="sxs-lookup"><span data-stu-id="ad285-233">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="ad285-234">着信 SIP オプションを使用しての組み合わせを検証するには、SBC の管理インターフェイスを使用し、SBC から直接ルーティング オプションのメッセージへの返信を送信して、送信する応答コードが 200 [ok] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad285-234">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="ad285-235">直接ルーティング サービスのユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ad285-235">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="ad285-236">直接ルーティング サービスに対してユーザーを有効にする準備ができたら、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ad285-236">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="ad285-237">Office 365 にユーザーを作成し、電話システムのライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad285-237">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="ad285-238">ビジネス オンラインの Skype のユーザーのホームすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad285-238">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="ad285-239">電話番号を構成し、エンタープライズ ボイスとボイス メールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ad285-239">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="ad285-240">音声ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="ad285-240">Configure voice routing.</span></span> <span data-ttu-id="ad285-241">ルートが自動的に検証されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-241">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="ad285-242">Office 365 にユーザーを作成し、ライセンスの割り当てください</span><span class="sxs-lookup"><span data-stu-id="ad285-242">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="ad285-243">Office 365 で新しいユーザーを作成するための 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ad285-243">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="ad285-244">ただし、組織が選択し、1 つのオプションを使用して、ルーティングの問題を回避することお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad285-244">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="ad285-245">オンプレミスの Active Directory でユーザーを作成し、ユーザーがクラウドを同期します。</span><span class="sxs-lookup"><span data-stu-id="ad285-245">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="ad285-246">[Azure Active Directory と統合、設置ディレクトリ](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad285-246">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="ad285-247">Office 365 管理者ポータルで直接ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad285-247">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="ad285-248">[追加ユーザー個別にまたは一括で Office 365 の管理者のヘルプ](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad285-248">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="ad285-249">オンライン ビジネス展開するため、Skype は、設置型のビジネス 2015年または Lync 2010/2013 Skype で共存して、サポートされている唯一のオプションが、オンプレミスの Active Directory でユーザーを作成し、(オプション 1) をクラウドに移行するユーザーを同期します。</span><span class="sxs-lookup"><span data-stu-id="ad285-249">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="ad285-250">必須ライセンス:</span><span class="sxs-lookup"><span data-stu-id="ad285-250">Required licenses:</span></span> 

- <span data-ttu-id="ad285-251">Office 365 エンタープライズ E3 (デバイス Plan2、Plan2 の交換、チームを含む) 電話システム</span><span class="sxs-lookup"><span data-stu-id="ad285-251">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="ad285-252">Office 365 エンタープライズ E5 (デバイス Plan2、Plan2 の交換、チーム、および電話システムを含む)</span><span class="sxs-lookup"><span data-stu-id="ad285-252">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="ad285-253">オプションのライセンス数:</span><span class="sxs-lookup"><span data-stu-id="ad285-253">Optional licenses:</span></span> 

- <span data-ttu-id="ad285-254">計画を呼び出す</span><span class="sxs-lookup"><span data-stu-id="ad285-254">Calling Plan</span></span> 
- <span data-ttu-id="ad285-255">電話会議</span><span class="sxs-lookup"><span data-stu-id="ad285-255">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="ad285-256">ビジネス オンラインの Skype のユーザーが所属していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad285-256">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="ad285-257">直接ルーティングでは、Skype でのオンライン ビジネスのホーム ユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="ad285-257">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="ad285-258">これを確認するには、RegistrarPool パラメーターを参照しています。</span><span class="sxs-lookup"><span data-stu-id="ad285-258">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="ad285-259">Infra.lync.com ドメイン内の値を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad285-259">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="ad285-260">リモート PowerShell に接続します。</span><span class="sxs-lookup"><span data-stu-id="ad285-260">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="ad285-261">コマンドを発行します。</span><span class="sxs-lookup"><span data-stu-id="ad285-261">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="ad285-262">電話番号を構成し、エンタープライズ ボイスとボイス メールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ad285-262">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="ad285-263">ユーザーを作成すると、次の手順は、電話番号やボイス メールを構成するのには、ライセンスが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="ad285-263">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="ad285-264">これは、1 つのステップで実行できます。</span><span class="sxs-lookup"><span data-stu-id="ad285-264">This can be done in one step.</span></span> 

<span data-ttu-id="ad285-265">電話番号を追加し、ボイス メールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ad285-265">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="ad285-266">リモート PowerShell セッションに接続します。</span><span class="sxs-lookup"><span data-stu-id="ad285-266">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="ad285-267">コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ad285-267">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="ad285-268">たとえば、「Spencer 低」のユーザーの電話番号を追加するのにはするは、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ad285-268">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="ad285-269">電話番号に国コードを含む完全 E.164 電話番号として構成するのには。</span><span class="sxs-lookup"><span data-stu-id="ad285-269">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="ad285-270">ユーザーの電話番号が施設内で管理されている場合は、ユーザーの電話番号を構成するのにはビジネス管理シェルまたはコントロール パネルの設置型の Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad285-270">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="ad285-271">音声ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="ad285-271">Configure Voice Routing</span></span> 

<span data-ttu-id="ad285-272">マイクロソフトの電話システムに基づく特定の SBC に送られる呼び出しを可能にするためのルーティング メカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="ad285-272">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="ad285-273">番号のパターンと呼ばれる</span><span class="sxs-lookup"><span data-stu-id="ad285-273">Called number pattern</span></span> 
- <span data-ttu-id="ad285-274">番号のパターン + 呼び出しでは、特定のユーザーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ad285-274">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="ad285-275">SBCs は、アクティブとバックアップとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="ad285-275">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="ad285-276">この番号のパターンまたはパターンの番号 + 特定のユーザーに対してアクティブに設定されている SBC が使用できない場合を意味し、呼び出しは、バックアップの SBC にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="ad285-276">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="ad285-277">通話のルーティングは、次の要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="ad285-277">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="ad285-278">音声ルーティング ポリシー – PSTN の使用法のためのコンテナーユーザーまたは複数のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ad285-278">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="ad285-279">PSTN 使用法: ボイス ルートと PSTN の使用法のためのコンテナー別の音声ルーティング ポリシーで共有することができます。</span><span class="sxs-lookup"><span data-stu-id="ad285-279">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="ad285-280">ボイス ルート – 番号のパターンと、パターンに一致する番号を呼び出す呼び出しに使用するオンラインの PSTN ゲートウェイの設定</span><span class="sxs-lookup"><span data-stu-id="ad285-280">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="ad285-281">オンラインの PSTN ゲートウェイ、SBC へのポインター、前方の P アサートされた Id (PAI) や優先のコーデックなど、SBC を使用して電話をかけるときに適用される設定を格納します。ボイス ルートを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ad285-281">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="ad285-282">PSTN 使用法の 1 つの音声ルーティング ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad285-282">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="ad285-283">次の図は、呼び出しの流れの音声ルーティング ポリシーの 2 つの例を示します。</span><span class="sxs-lookup"><span data-stu-id="ad285-283">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="ad285-284">**(左側) のフロー 1 の呼び出し:**+1 425 XXX XX XX または +1 206 XXX XX XX への呼び出しを行うと、SBC sbc1.contoso.biz または sbc2.contoso.biz 呼び出しがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="ad285-284">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="ad285-285">Sbc1.contoso.biz と sbc2.contoso.biz のどちらもが利用可能な場合は、呼び出しは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-285">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="ad285-286">**(右側) のフロー 2 の呼び出し:**+1 425 XXX XX XX または +1 206 XXX XX XX への呼び出しを行うと場合の呼び出しはまず SBC sbc1.contoso.biz または sbc2.contoso.biz にルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="ad285-286">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="ad285-287">SBC のどちらが使用可能な場合は、優先度の低いルートになります (sbc3.contoso.biz と sbc4.contoso.biz) をしようとしました。</span><span class="sxs-lookup"><span data-stu-id="ad285-287">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="ad285-288">SBCs の [なし] がある場合、呼び出しは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-288">If none of the SBCs are available, the call is dropped.</span></span> 

![音声ルーティング ポリシーの例を示しています。](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="ad285-290">どちらの例では、ボイス ルートは、優先順位を割り当てられている間、ルートの SBCs はランダムな順序で試行されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-290">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ad285-291">ユーザーもライセンスを持つ、Microsoft の計画を呼び出すことをしない限り、+1 425 の XXX の XX XX または構成の例で +1 206 の XXX XX XX のパターンに一致する数字以外の任意の数への呼び出しは削除されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-291">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="ad285-292">ユーザーのライセンス計画を呼び出す場合は、呼び出しは自動的にマイクロソフトを呼び出す予定のポリシーに従ってルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="ad285-292">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="ad285-293">マイクロソフトを呼び出す計画では、Microsoft の計画を呼び出してライセンスを持つすべてのユーザーに最後のルートとしてには、自動的に適用され、追加の呼び出しのルーティングの構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ad285-293">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="ad285-294">例では、次の図に示すように、すべての他の米国およびカナダ番号 (番号のパターンと呼ばれる +1 XXX XXX XX XX に行われる呼び出し) への呼び出しを送信するボイス ルートが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-294">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![番組音声の 3 つ目のルートをルーティング ポリシー](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="ad285-296">他のすべての呼び出しでは、ユーザーは、(マイクロソフトの電話システムと Microsoft の計画を呼び出す)、両方のライセンスを持っている場合、自動工順が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-296">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="ad285-297">何もには、管理者が作成したオンラインでのボイス ルートの番号のパターンが一致すると、Microsoft の計画を呼び出すを使用してルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ad285-297">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="ad285-298">ユーザーは、マイクロソフトの電話システムのみがある、一致する規則がないために、呼び出しが切断されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-298">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ad285-299">「+1 その他の」ルートの優先順位の値 +1 のパターンに一致する 1 つだけのルートがある、この例では、関係ありません XXX XXX XX XX。</span><span class="sxs-lookup"><span data-stu-id="ad285-299">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="ad285-300">+1 324 の 567 89 89 への呼び出しを行うと、sbc5.contoso.biz と sbc6.contoso.biz の両方が使用できない場合は、呼び出しは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-300">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="ad285-301">次の表では、3 つのボイス ルートを使用して設定をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="ad285-301">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="ad285-302">この例では、すべての 3 つのルートは、同じ PSTN 使用法米国およびカナダの一部です。</span><span class="sxs-lookup"><span data-stu-id="ad285-302">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="ad285-303">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="ad285-303">**PSTN usage**</span></span>|<span data-ttu-id="ad285-304">**ボイス ルート**</span><span class="sxs-lookup"><span data-stu-id="ad285-304">**Voice route**</span></span>|<span data-ttu-id="ad285-305">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="ad285-305">**Number pattern**</span></span>|<span data-ttu-id="ad285-306">**優先度**</span><span class="sxs-lookup"><span data-stu-id="ad285-306">**Priority**</span></span>|<span data-ttu-id="ad285-307">**SBC**</span><span class="sxs-lookup"><span data-stu-id="ad285-307">**SBC**</span></span>|<span data-ttu-id="ad285-308">**説明**</span><span class="sxs-lookup"><span data-stu-id="ad285-308">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad285-309">米国のみ</span><span class="sxs-lookup"><span data-stu-id="ad285-309">US only</span></span>|<span data-ttu-id="ad285-310">「Redmond 1」</span><span class="sxs-lookup"><span data-stu-id="ad285-310">"Redmond 1"</span></span>|<span data-ttu-id="ad285-311">^\\+1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="ad285-311">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="ad285-312">1</span><span class="sxs-lookup"><span data-stu-id="ad285-312">1</span></span>|<span data-ttu-id="ad285-313">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-313">sbc1.contoso.biz</span></span><br/><span data-ttu-id="ad285-314">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-314">sbc2.contoso.biz</span></span>|<span data-ttu-id="ad285-315">+1 425 XXX XX XX または +1 206 XXX XX XX の呼び出された番号の有効な工順</span><span class="sxs-lookup"><span data-stu-id="ad285-315">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="ad285-316">米国のみ</span><span class="sxs-lookup"><span data-stu-id="ad285-316">US only</span></span>|<span data-ttu-id="ad285-317">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="ad285-317">"Redmond 2"</span></span>|<span data-ttu-id="ad285-318">^\\+1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="ad285-318">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="ad285-319">2</span><span class="sxs-lookup"><span data-stu-id="ad285-319">2</span></span>|<span data-ttu-id="ad285-320">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-320">sbc3.contoso.biz</span></span><br/><span data-ttu-id="ad285-321">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-321">sbc4.contoso.biz</span></span>|<span data-ttu-id="ad285-322">+1 425 XXX XX XX または +1 206 XXX XX XX の呼び出された番号のバックアップ ルート</span><span class="sxs-lookup"><span data-stu-id="ad285-322">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="ad285-323">米国のみ</span><span class="sxs-lookup"><span data-stu-id="ad285-323">US only</span></span>|<span data-ttu-id="ad285-324">「その他の +1」</span><span class="sxs-lookup"><span data-stu-id="ad285-324">"Other +1"</span></span>|<span data-ttu-id="ad285-325">^\\+1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="ad285-325">^\\+1(\d{10})$</span></span>|<span data-ttu-id="ad285-326">3</span><span class="sxs-lookup"><span data-stu-id="ad285-326">3</span></span>|<span data-ttu-id="ad285-327">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-327">sbc5.contoso.biz</span></span><br/><span data-ttu-id="ad285-328">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-328">sbc6.contoso.biz</span></span>|<span data-ttu-id="ad285-329">呼ばれる数字の +1 XXX XXX の XX XX (+1 425 XXX XX XX +1 206 XXX XX XX 以外) をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ad285-329">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="ad285-330">すべてのルートは、米国およびカナダの PSTN 使用法に関連付けられているし、は、音声ルーティング ポリシー「u. s. だけです」に関連付けられている PSTN 使用法</span><span class="sxs-lookup"><span data-stu-id="ad285-330">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="ad285-331">この例では、音声ルーティング ポリシーは Spencer 低のユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ad285-331">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="ad285-332">呼び出しのルーティングの例</span><span class="sxs-lookup"><span data-stu-id="ad285-332">Examples of call routes</span></span>

<span data-ttu-id="ad285-333">次の例では、ルート、PSTN の使用法、およびルーティング ポリシーを構成する方法について説明し、ユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad285-333">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="ad285-334">**手順 1:** PSTN 使用法] 米国およびカナダ」を作成します。</span><span class="sxs-lookup"><span data-stu-id="ad285-334">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="ad285-335">ビジネス リモート PowerShell セッションを Skype では、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ad285-335">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="ad285-336">使用状況が入力することにより作成されたものであることを検証します。</span><span class="sxs-lookup"><span data-stu-id="ad285-336">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="ad285-337">切り捨てられる可能性がありますの名前の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="ad285-337">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="ad285-338">次の例では、実行中の結果を確認できます PowerShell コマンド`(Get-CSOnlinePSTNUsage).usage`(切り捨てではない) 完全な名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="ad285-338">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="ad285-339">**手順 2:** ビジネス オンラインの Skype の PowerShell セッションで次の 3 つのルートを作成: 上記の表に示すとおり、レッドモンド 1、2、およびその他の +1 のレドモンド。</span><span class="sxs-lookup"><span data-stu-id="ad285-339">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="ad285-340">「Redmond 1」のルートを作成するには、次コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ad285-340">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="ad285-341">返します。</span><span class="sxs-lookup"><span data-stu-id="ad285-341">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
<span data-ttu-id="ad285-342">レドモンド 2 ルートを作成するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ad285-342">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="ad285-343">+1 で他のルートを作成するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ad285-343">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="ad285-344">[NumberPattern] 属性には、正規表現が有効な式であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ad285-344">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="ad285-345">この web サイトを使用することをテストすることができます。[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="ad285-345">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="ad285-346">場合によっては、同じの SBC はすべての呼び出しをルーティングする必要があります。-NumberPattern を使用してください」. \*"</span><span class="sxs-lookup"><span data-stu-id="ad285-346">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="ad285-347">同じ SBC へのすべての呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ad285-347">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="ad285-348">正しく構成したルートを実行して、検証、 `Get-CSOnlineVoiceRoute` PowerShell コマンドのようにオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad285-348">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="ad285-349">次の項目を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad285-349">Which should return:</span></span>
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

<span data-ttu-id="ad285-350">例では、ルート「その他の +1」が 4 の優先順位を自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ad285-350">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="ad285-351">**手順 3:**「私たちだけ」音声ルーティング ポリシーを作成し、「米国とカナダ」PSTN の使用法をポリシーに追加</span><span class="sxs-lookup"><span data-stu-id="ad285-351">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="ad285-352">ビジネス オンラインの Skype の PowerShell セッションで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ad285-352">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="ad285-353">結果は、次の使用例で示されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-353">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="ad285-354">**手順 4:** PowerShell を使用して、音声ルーティング ポリシーを Spencer 低のユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="ad285-354">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="ad285-355">ビジネス オンラインの Skype の PowerShell セッションで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ad285-355">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="ad285-356">このコマンドを入力して、ポリシーの割り当てを検証します。</span><span class="sxs-lookup"><span data-stu-id="ad285-356">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="ad285-357">返します。</span><span class="sxs-lookup"><span data-stu-id="ad285-357">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="ad285-358">PSTN 使用法のいくつかの音声ルーティング ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad285-358">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="ad285-359">音声ルーティング ポリシーを作成以前のみでは、米国およびカナダ - 電話番号への呼び出し Microsoft の計画を呼び出してライセンスがユーザーにも割り当てられている場合を除き、します。</span><span class="sxs-lookup"><span data-stu-id="ad285-359">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="ad285-360">次の例で作成できます音声ルーティング ポリシー「制限なし」です。</span><span class="sxs-lookup"><span data-stu-id="ad285-360">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="ad285-361">ポリシーは、米国およびカナダで新しい PSTN 使用法国際。」と、前の例では、作成した PSTN 使用法を再利用します。</span><span class="sxs-lookup"><span data-stu-id="ad285-361">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="ad285-362">これは、SBCs の sbc2.contoso.biz と sbc5.contoso.biz に他のすべての呼び出しをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ad285-362">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="ad285-363">示されている例を付ける [Spencer 低"のユーザーにポリシー米国のみと制限のないユーザー「John 森」です。</span><span class="sxs-lookup"><span data-stu-id="ad285-363">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="ad285-364">Spencer 低: 米国およびカナダの番号にのみ許可される呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="ad285-364">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="ad285-365">レドモンドの番号の範囲を呼び出すと、SBC の特定のセットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad285-365">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="ad285-366">計画を呼び出してライセンスがユーザーに割り当てられている場合を除き、米国以外の数値はルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="ad285-366">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="ad285-367">ジョンの森 – 呼び出しは、任意の数を許可しました。</span><span class="sxs-lookup"><span data-stu-id="ad285-367">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="ad285-368">レドモンドの番号の範囲を呼び出すと、SBC の特定のセットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad285-368">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="ad285-369">米国以外の番号は、sbc2.contoso.biz と sbc5.contoso.biz を使用してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="ad285-369">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Spencer 低のユーザーに割り当てられている音声のルーティング ポリシーを示しています。](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="ad285-371">他のすべての呼び出しでは、ユーザーは、(マイクロソフトの電話システムと Microsoft の計画を呼び出す)、両方のライセンスを持っている場合、自動工順が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-371">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="ad285-372">何もには、管理者が作成したオンラインでのボイス ルートの番号のパターンが一致すると、Microsoft の計画を呼び出すを使用してルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ad285-372">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="ad285-373">ユーザーは、マイクロソフトの電話システムのみがある、一致する規則がないために、呼び出しが切断されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-373">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![音声ルーティング ポリシーのユーザー John の森に割り当てられているを示しています。](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="ad285-375">次の表は、ルーティング ポリシー「制限なし」の使用の指定、およびボイス ルートをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="ad285-375">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="ad285-376">**PSTN 使用法**</span><span class="sxs-lookup"><span data-stu-id="ad285-376">**PSTN usage**</span></span>|<span data-ttu-id="ad285-377">**ボイス ルート**</span><span class="sxs-lookup"><span data-stu-id="ad285-377">**Voice route**</span></span>|<span data-ttu-id="ad285-378">**番号パターン**</span><span class="sxs-lookup"><span data-stu-id="ad285-378">**Number pattern**</span></span>|<span data-ttu-id="ad285-379">**優先度**</span><span class="sxs-lookup"><span data-stu-id="ad285-379">**Priority**</span></span>|<span data-ttu-id="ad285-380">**SBC**</span><span class="sxs-lookup"><span data-stu-id="ad285-380">**SBC**</span></span>|<span data-ttu-id="ad285-381">**説明**</span><span class="sxs-lookup"><span data-stu-id="ad285-381">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad285-382">米国のみ</span><span class="sxs-lookup"><span data-stu-id="ad285-382">US Only</span></span>|<span data-ttu-id="ad285-383">「Redmond 1」</span><span class="sxs-lookup"><span data-stu-id="ad285-383">"Redmond 1"</span></span>|<span data-ttu-id="ad285-384">^\\+1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="ad285-384">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="ad285-385">1</span><span class="sxs-lookup"><span data-stu-id="ad285-385">1</span></span>|<span data-ttu-id="ad285-386">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-386">sbc1.contoso.biz</span></span><br/><span data-ttu-id="ad285-387">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-387">sbc2.contoso.biz</span></span>|<span data-ttu-id="ad285-388">+1 425 XXX XX XX または +1 206 XXX XX XX 番号が呼び出し先の有効な工順</span><span class="sxs-lookup"><span data-stu-id="ad285-388">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="ad285-389">米国のみ</span><span class="sxs-lookup"><span data-stu-id="ad285-389">US Only</span></span>|<span data-ttu-id="ad285-390">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="ad285-390">"Redmond 2"</span></span>|<span data-ttu-id="ad285-391">^\\+1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="ad285-391">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="ad285-392">2</span><span class="sxs-lookup"><span data-stu-id="ad285-392">2</span></span>|<span data-ttu-id="ad285-393">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-393">sbc3.contoso.biz</span></span><br/><span data-ttu-id="ad285-394">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-394">sbc4.contoso.biz</span></span>|<span data-ttu-id="ad285-395">+1 425 XXX XX XX または +1 206 XXX XX XX 番号が呼び出し先のバックアップ ルート</span><span class="sxs-lookup"><span data-stu-id="ad285-395">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="ad285-396">米国のみ</span><span class="sxs-lookup"><span data-stu-id="ad285-396">US Only</span></span>|<span data-ttu-id="ad285-397">「その他の +1」</span><span class="sxs-lookup"><span data-stu-id="ad285-397">"Other +1"</span></span>|<span data-ttu-id="ad285-398">^\\+1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="ad285-398">^\\+1(\d{10})$</span></span>|<span data-ttu-id="ad285-399">3</span><span class="sxs-lookup"><span data-stu-id="ad285-399">3</span></span>|<span data-ttu-id="ad285-400">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-400">sbc5.contoso.biz</span></span><br/><span data-ttu-id="ad285-401">sbc6>.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-401">sbc6>.contoso.biz</span></span>|<span data-ttu-id="ad285-402">呼び出し先のルートの番号 +1 XXX XXX の XX XX (+1 425 XXX XX XX または +1 206 XXX XX XX) を除く</span><span class="sxs-lookup"><span data-stu-id="ad285-402">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="ad285-403">International</span><span class="sxs-lookup"><span data-stu-id="ad285-403">International</span></span>|<span data-ttu-id="ad285-404">International</span><span class="sxs-lookup"><span data-stu-id="ad285-404">International</span></span>|<span data-ttu-id="ad285-405">\d+</span><span class="sxs-lookup"><span data-stu-id="ad285-405">\d+</span></span>|<span data-ttu-id="ad285-406">4</span><span class="sxs-lookup"><span data-stu-id="ad285-406">4</span></span>|<span data-ttu-id="ad285-407">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-407">sbc2.contoso.biz</span></span><br/><span data-ttu-id="ad285-408">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="ad285-408">sbc5.contoso.biz</span></span>|<span data-ttu-id="ad285-409">任意の番号のパターンのルート</span><span class="sxs-lookup"><span data-stu-id="ad285-409">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="ad285-410">音声ルーティング ポリシーの PSTN 使用法の順序は重要です。</span><span class="sxs-lookup"><span data-stu-id="ad285-410">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="ad285-411">順番については、使用法が適用され、最初の使用で一致が見つかった場合、その他の方法は評価されません。</span><span class="sxs-lookup"><span data-stu-id="ad285-411">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="ad285-412">PSTN 使用法「国際」する必要があります後に配置される PSTN 使用法」ことだけです」</span><span class="sxs-lookup"><span data-stu-id="ad285-412">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="ad285-413">PSTN 使用法の順序を変更するには、実行、`Set-CSOnlineRouteRoutingPolicy`コマンドです。</span><span class="sxs-lookup"><span data-stu-id="ad285-413">To change the order of the PSTN Usages, run the `Set-CSOnlineRouteRoutingPolicy` command.</span></span> <br/><span data-ttu-id="ad285-414">たとえば、米国およびカナダからの順序を変更する順序とは逆に国際化し、最初の 2 番目を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad285-414">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="ad285-415">「その他の +1」と「国際」ボイス ルートの優先順位は自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ad285-415">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="ad285-416">「Redmond 1」と「レドモンド 2」よりも低い優先順位がある限り、問題でない</span><span class="sxs-lookup"><span data-stu-id="ad285-416">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="ad285-417">ユーザー John の森の音声ルーティング ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="ad285-417">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="ad285-418">PSTN 使用法「国際」を作成する手順はルーティング ポリシー制限のなし」、「音声ボイス ルート「国際」とは、次ように、それを「ジョンの森"のユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad285-418">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="ad285-419">国際「PSTN 使用法を最初に、作成</span><span class="sxs-lookup"><span data-stu-id="ad285-419">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="ad285-420">ビジネス オンラインの Skype のリモート PowerShell セッションで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ad285-420">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="ad285-421">国際"次に、新しいボイス ルートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad285-421">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="ad285-422">返します。</span><span class="sxs-lookup"><span data-stu-id="ad285-422">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SupressCallerId           :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="ad285-423">次に、「制限なし」の音声ルーティング ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad285-423">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="ad285-424">"+1 425 XXX XX XX"とローカルとして「+1 206 XXX XX XX」の番号への呼び出しまたはオンプレミス呼び出しの特別な処理を保持するにはこの音声ルーティング ポリシーでは、PSTN の使用法"Redmond 1"と"Redmond"が再利用されます。</span><span class="sxs-lookup"><span data-stu-id="ad285-424">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="ad285-425">返します。</span><span class="sxs-lookup"><span data-stu-id="ad285-425">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="ad285-426">ユーザー「John 森」次のコマンドを使用するには、音声ルーティング ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad285-426">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="ad285-427">コマンドを使用して割り当てを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad285-427">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="ad285-428">返します。</span><span class="sxs-lookup"><span data-stu-id="ad285-428">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="ad285-429">結果は、ジョンの森の呼び出しに適用されるボイス ポリシーは制限はないと、米国、カナダ、および国際通話に使用できる通話のルーティングのロジックを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad285-429">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="ad285-430">マイクロソフトのチームを優先する呼び出し元クライアントとユーザーの設定します。</span><span class="sxs-lookup"><span data-stu-id="ad285-430">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="ad285-431">直接ルーティング ルートのみを呼び出しのユーザーとの間のチームのクライアントを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="ad285-431">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="ad285-432">のみ、組織には、チームが使用しているチームのみ] 設定モードでのアップグレードのポリシーを推奨します。</span><span class="sxs-lookup"><span data-stu-id="ad285-432">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="ad285-433">詳細については次の資料を参照してくださいし、適切なオプションを選択する組織は、オンライン ビジネスのビジネス サーバーまたは Skype の Skype を使用する場合:[共存を理解しビジネスとチームの Skype の旅をアップグレード](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)します。</span><span class="sxs-lookup"><span data-stu-id="ad285-433">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="ad285-434">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad285-434">See also</span></span>

[<span data-ttu-id="ad285-435">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="ad285-435">Plan Direct Routing</span></span>](direct-routing-plan.md)
