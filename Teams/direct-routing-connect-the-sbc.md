---
title: セッション境界のコントローラー (SBC) を直接ルーティングに接続する
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
f1.keywords:
- NOCSH
description: Microsoft Phone システムのダイレクトルーティングを構成する方法について説明します。
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157987"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a><span data-ttu-id="8bbde-103">セッション境界のコントローラー (SBC) を直接ルーティングに接続する</span><span class="sxs-lookup"><span data-stu-id="8bbde-103">Connect your Session Border Controller (SBC) to Direct Routing</span></span> 

<span data-ttu-id="8bbde-104">この記事では、セッションボーダーコントローラー (SBC) を電話システムのダイレクトルーティングに接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-104">This article describes how to connect your Session Border Controller (SBC) to Phone System Direct Routing.</span></span>  <span data-ttu-id="8bbde-105">これは、次の手順の手順1で、直接ルーティングを構成します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-105">This is step 1 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="8bbde-106">**手順1お使いの SBC を電話システムに接続して接続を検証する**(この記事)</span><span class="sxs-lookup"><span data-stu-id="8bbde-106">**Step 1. Connect your SBC with Phone System and validate the connection** (This article)</span></span>
- <span data-ttu-id="8bbde-107">手順2</span><span class="sxs-lookup"><span data-stu-id="8bbde-107">Step 2.</span></span> [<span data-ttu-id="8bbde-108">ユーザーが直接ルーティングできるようにする</span><span class="sxs-lookup"><span data-stu-id="8bbde-108">Enable users for Direct Routing</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="8bbde-109">手順3</span><span class="sxs-lookup"><span data-stu-id="8bbde-109">Step 3.</span></span> [<span data-ttu-id="8bbde-110">通話ルーティングの構成</span><span class="sxs-lookup"><span data-stu-id="8bbde-110">Configure call routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="8bbde-111">手順4。</span><span class="sxs-lookup"><span data-stu-id="8bbde-111">Step 4.</span></span> [<span data-ttu-id="8bbde-112">数値を別の形式に変換する</span><span class="sxs-lookup"><span data-stu-id="8bbde-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="8bbde-113">直接ルーティングを設定するために必要なすべての手順については、「[直接ルーティングを構成する](direct-routing-configure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bbde-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="8bbde-114">SBC をダイレクトルーティングに接続するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bbde-114">To connect your SBC to Direct Routing, you'll need to:</span></span> 

1. <span data-ttu-id="8bbde-115">PowerShell を使用して、 **Skype For Business Online**管理センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-115">Connect to **Skype for Business Online** admin center by using PowerShell.</span></span>            
2. <span data-ttu-id="8bbde-116">SBC をテナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-116">Connect the SBC to the tenant.</span></span>
3. <span data-ttu-id="8bbde-117">接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-117">Validate the connection.</span></span> 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="8bbde-118">PowerShell を使用して Skype for Business Online に接続する</span><span class="sxs-lookup"><span data-stu-id="8bbde-118">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="8bbde-119">テナントに接続された PowerShell セッションを使って、SBC とダイレクトルーティングインターフェイスをペアリングすることができます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-119">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="8bbde-120">PowerShell セッションを開くには、「 [Windows powershell 用にコンピューターを](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)セットアップする」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8bbde-120">To open a PowerShell session, follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="8bbde-121">リモート PowerShell セッションを確立したら、SBC を管理するためのコマンドが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-121">After you establish a remote PowerShell session, validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="8bbde-122">コマンドを検証するには、PowerShell セッションで次のコマンドを入力するか、コピーして貼り付け、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-122">To validate the commands, type or copy and paste the following command in the PowerShell session and press Enter:</span></span> 

```PowerShell
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="8bbde-123">このコマンドは、SBC を管理できるように、次の4つの関数を返します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-123">The command returns the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


## <a name="connect-the-sbc-to-the-tenant"></a><span data-ttu-id="8bbde-124">SBC をテナントに接続する</span><span class="sxs-lookup"><span data-stu-id="8bbde-124">Connect the SBC to the tenant</span></span> 

<span data-ttu-id="8bbde-125">SBC をテナントに接続するには、PowerShell セッションで次のように入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-125">To connect the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="8bbde-126">Microsoft は、sbc ドキュメントに記載されている情報を使用して、SBC で最大限の通話制限を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8bbde-126">Microsoft recommends setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="8bbde-127">SBC がキャパシティレベルにある場合、制限によって通知がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-127">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="8bbde-128">SBC をペアリングできるのは、その FQDN のドメイン部分が、テナントに登録されているドメインのいずれ\*かに一致している場合のみです。 onmicrosoft.com を除きます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-128">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="8bbde-129">\*Onmicrosoft.com ドメイン名は、SBC FQDN 名ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8bbde-129">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="8bbde-130">たとえば、2つのドメイン名がある場合は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8bbde-130">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="8bbde-131">**contoso**.com</span><span class="sxs-lookup"><span data-stu-id="8bbde-131">**contoso**.com</span></span><br/><span data-ttu-id="8bbde-132">\*\*\*\* onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8bbde-132">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="8bbde-133">SBC 名には、sbc.contoso.com という名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-133">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="8bbde-134">SBC と名前 sbc をペアリングしようとしても、ドメインはこのテナントによって所有されていないため、システムによっては許可されません。</span><span class="sxs-lookup"><span data-stu-id="8bbde-134">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="8bbde-135">テナントに登録されているドメインに加えて、そのドメインを持つユーザーと E3 または E5 ライセンスが割り当てられていることが重要です。</span><span class="sxs-lookup"><span data-stu-id="8bbde-135">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="8bbde-136">存在しない場合、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-136">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="8bbde-137">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="8bbde-137">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span></span>

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="8bbde-138">返し</span><span class="sxs-lookup"><span data-stu-id="8bbde-138">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="8bbde-139">接続プロセス中に設定できるその他のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8bbde-139">There are additional options that can be set during the connection process.</span></span> <span data-ttu-id="8bbde-140">ただし、前の例では、必須の最小パラメーターのみが表示されています。</span><span class="sxs-lookup"><span data-stu-id="8bbde-140">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="8bbde-141">次の表は、の```New-CsOnlinePstnGateway```パラメーターの設定に使用できるその他のパラメーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="8bbde-141">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="8bbde-142">必須。</span><span class="sxs-lookup"><span data-stu-id="8bbde-142">Required?</span></span>|<span data-ttu-id="8bbde-143">名前</span><span class="sxs-lookup"><span data-stu-id="8bbde-143">Name</span></span>|<span data-ttu-id="8bbde-144">説明</span><span class="sxs-lookup"><span data-stu-id="8bbde-144">Description</span></span>|<span data-ttu-id="8bbde-145">既定</span><span class="sxs-lookup"><span data-stu-id="8bbde-145">Default</span></span>|<span data-ttu-id="8bbde-146">可能な値</span><span class="sxs-lookup"><span data-stu-id="8bbde-146">Possible values</span></span>|<span data-ttu-id="8bbde-147">種類と制限</span><span class="sxs-lookup"><span data-stu-id="8bbde-147">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8bbde-148">はい</span><span class="sxs-lookup"><span data-stu-id="8bbde-148">Yes</span></span>|<span data-ttu-id="8bbde-149">FQDN</span><span class="sxs-lookup"><span data-stu-id="8bbde-149">FQDN</span></span>|<span data-ttu-id="8bbde-150">SBC の FQDN 名</span><span class="sxs-lookup"><span data-stu-id="8bbde-150">The FQDN name of the SBC</span></span> |<span data-ttu-id="8bbde-151">なし</span><span class="sxs-lookup"><span data-stu-id="8bbde-151">None</span></span>|<span data-ttu-id="8bbde-152">NoneFQDN 名、63文字を制限する</span><span class="sxs-lookup"><span data-stu-id="8bbde-152">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="8bbde-153">[コンピューター、ドメイン、サイト、および ou の Active Directory の名前付け規則](https://support.microsoft.com/help/909264)での文字列、許可されている文字および禁止されている文字の一覧</span><span class="sxs-lookup"><span data-stu-id="8bbde-153">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="8bbde-154">いいえ</span><span class="sxs-lookup"><span data-stu-id="8bbde-154">No</span></span>|<span data-ttu-id="8bbde-155">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="8bbde-155">MediaBypass</span></span> |<span data-ttu-id="8bbde-156">は、SBC でサポートされているメディアバイパスのパラメーターであり、管理者はこのパラメーターを使いたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="8bbde-156">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="8bbde-157">なし</span><span class="sxs-lookup"><span data-stu-id="8bbde-157">None</span></span>|<span data-ttu-id="8bbde-158">True</span><span class="sxs-lookup"><span data-stu-id="8bbde-158">True</span></span><br/><span data-ttu-id="8bbde-159">False</span><span class="sxs-lookup"><span data-stu-id="8bbde-159">False</span></span>|<span data-ttu-id="8bbde-160">Boolean</span><span class="sxs-lookup"><span data-stu-id="8bbde-160">Boolean</span></span>|
|<span data-ttu-id="8bbde-161">はい</span><span class="sxs-lookup"><span data-stu-id="8bbde-161">Yes</span></span>|<span data-ttu-id="8bbde-162">SipSignalingPort</span><span class="sxs-lookup"><span data-stu-id="8bbde-162">SipSignalingPort</span></span> |<span data-ttu-id="8bbde-163">トランスポート層セキュリティ (TLS) プロトコルを使用した、直接ルーティングサービスとの通信に使用するリスニングポート。</span><span class="sxs-lookup"><span data-stu-id="8bbde-163">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="8bbde-164">なし</span><span class="sxs-lookup"><span data-stu-id="8bbde-164">None</span></span>|<span data-ttu-id="8bbde-165">任意のポート</span><span class="sxs-lookup"><span data-stu-id="8bbde-165">Any port</span></span>|<span data-ttu-id="8bbde-166">0 ~ 65535</span><span class="sxs-lookup"><span data-stu-id="8bbde-166">0 to 65535</span></span> |
|<span data-ttu-id="8bbde-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="8bbde-167">No</span></span>|<span data-ttu-id="8bbde-168">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="8bbde-168">FailoverTimeSeconds</span></span> |<span data-ttu-id="8bbde-169">10 (既定値) に設定すると、ゲートウェイによって応答されない送信通話は、次の利用可能なトランクにルーティングされます。追加の trunks がない場合、通話は自動的に切断されます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-169">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="8bbde-170">低速のネットワークとゲートウェイ応答を使用している組織では、通話が不必要に削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8bbde-170">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="8bbde-171">既定値は10です。</span><span class="sxs-lookup"><span data-stu-id="8bbde-171">The default value is 10.</span></span>|<span data-ttu-id="8bbde-172">常用</span><span class="sxs-lookup"><span data-stu-id="8bbde-172">10</span></span>|<span data-ttu-id="8bbde-173">数値</span><span class="sxs-lookup"><span data-stu-id="8bbde-173">Number</span></span>|<span data-ttu-id="8bbde-174">Int</span><span class="sxs-lookup"><span data-stu-id="8bbde-174">Int</span></span>|
|<span data-ttu-id="8bbde-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="8bbde-175">No</span></span>|<span data-ttu-id="8bbde-176">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="8bbde-176">ForwardCallHistory</span></span> |<span data-ttu-id="8bbde-177">通話履歴の情報をトランク経由で転送するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-177">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="8bbde-178">有効になっている場合、Office 365 PSTN プロキシは、2つのヘッダー (履歴-情報と参照) を送信します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-178">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="8bbde-179">既定値は**False** ($False) です。</span><span class="sxs-lookup"><span data-stu-id="8bbde-179">The default value is **False** ($False).</span></span> |<span data-ttu-id="8bbde-180">False</span><span class="sxs-lookup"><span data-stu-id="8bbde-180">False</span></span>|<span data-ttu-id="8bbde-181">True</span><span class="sxs-lookup"><span data-stu-id="8bbde-181">True</span></span><br/><span data-ttu-id="8bbde-182">False</span><span class="sxs-lookup"><span data-stu-id="8bbde-182">False</span></span>|<span data-ttu-id="8bbde-183">Boolean</span><span class="sxs-lookup"><span data-stu-id="8bbde-183">Boolean</span></span>|
|<span data-ttu-id="8bbde-184">いいえ</span><span class="sxs-lookup"><span data-stu-id="8bbde-184">No</span></span>|<span data-ttu-id="8bbde-185">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="8bbde-185">ForwardPAI</span></span>|<span data-ttu-id="8bbde-186">P-Asserted-Identity (PAI) ヘッダーを通話とともに転送するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-186">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="8bbde-187">PAI ヘッダーがあれば、発信者 ID を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-187">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="8bbde-188">有効になっている場合、プライバシー: ID ヘッダーも送信されます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-188">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="8bbde-189">既定値は**False** ($False) です。</span><span class="sxs-lookup"><span data-stu-id="8bbde-189">The default value is **False** ($False).</span></span>|<span data-ttu-id="8bbde-190">False</span><span class="sxs-lookup"><span data-stu-id="8bbde-190">False</span></span>|<span data-ttu-id="8bbde-191">True</span><span class="sxs-lookup"><span data-stu-id="8bbde-191">True</span></span><br/><span data-ttu-id="8bbde-192">False</span><span class="sxs-lookup"><span data-stu-id="8bbde-192">False</span></span>|<span data-ttu-id="8bbde-193">Boolean</span><span class="sxs-lookup"><span data-stu-id="8bbde-193">Boolean</span></span>|
|<span data-ttu-id="8bbde-194">いいえ</span><span class="sxs-lookup"><span data-stu-id="8bbde-194">No</span></span>|<span data-ttu-id="8bbde-195">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="8bbde-195">SendSIPOptions</span></span> |<span data-ttu-id="8bbde-196">SBC が SIP オプションを送信するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-196">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="8bbde-197">無効にした場合、SBC は、監視および警告システムから除外されます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-197">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="8bbde-198">SIP オプションを有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8bbde-198">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="8bbde-199">既定値は**True**です。</span><span class="sxs-lookup"><span data-stu-id="8bbde-199">Default value is **True**.</span></span> |<span data-ttu-id="8bbde-200">True</span><span class="sxs-lookup"><span data-stu-id="8bbde-200">True</span></span>|<span data-ttu-id="8bbde-201">True</span><span class="sxs-lookup"><span data-stu-id="8bbde-201">True</span></span><br/><span data-ttu-id="8bbde-202">False</span><span class="sxs-lookup"><span data-stu-id="8bbde-202">False</span></span>|<span data-ttu-id="8bbde-203">Boolean</span><span class="sxs-lookup"><span data-stu-id="8bbde-203">Boolean</span></span>|
|<span data-ttu-id="8bbde-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="8bbde-204">No</span></span>|<span data-ttu-id="8bbde-205">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="8bbde-205">MaxConcurrentSessions</span></span> |<span data-ttu-id="8bbde-206">アラートシステムで使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-206">Used by alerting system.</span></span> <span data-ttu-id="8bbde-207">いずれかの値が設定されると、同時セッション数が90% 以上である場合、またはこの値よりも高い場合に、通知システムによってテナント管理者に通知が生成されます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-207">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent sessions is 90% or higher than this value.</span></span> <span data-ttu-id="8bbde-208">このパラメーターが設定されていない場合、アラートは生成されません。</span><span class="sxs-lookup"><span data-stu-id="8bbde-208">If the parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="8bbde-209">ただし、監視システムでは、24時間ごとに同時セッション数が報告されます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-209">However, the monitoring system will report number of concurrent sessions every 24 hours.</span></span> |<span data-ttu-id="8bbde-210">空</span><span class="sxs-lookup"><span data-stu-id="8bbde-210">Null</span></span>|<span data-ttu-id="8bbde-211">空</span><span class="sxs-lookup"><span data-stu-id="8bbde-211">Null</span></span><br/><span data-ttu-id="8bbde-212">1 ~ 10万</span><span class="sxs-lookup"><span data-stu-id="8bbde-212">1 to 100,000</span></span> ||
|<span data-ttu-id="8bbde-213">いいえ</span><span class="sxs-lookup"><span data-stu-id="8bbde-213">No</span></span>|<span data-ttu-id="8bbde-214">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="8bbde-214">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="8bbde-215">メディアのパスを手動で選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-215">Allows selecting path for media manually.</span></span> <span data-ttu-id="8bbde-216">直接ルーティングでは、SBC のパブリック IP に基づいて、メディアパスのデータセンターが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-216">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="8bbde-217">常に、SBC データセンターに最も近いものを選択します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-217">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="8bbde-218">ただし、場合によっては、たとえば、米国の範囲をヨーロッパの SBC に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-218">However, in some cases a public IP from, for example, a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="8bbde-219">この場合は、最適なメディアパスを使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="8bbde-219">In this case, we will be using not optimal media path.</span></span> <span data-ttu-id="8bbde-220">このパラメーターを使うと、メディアトラフィックの優先領域を手動で設定できます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-220">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="8bbde-221">このパラメーターを設定することは、メディアパスのデータセンターの自動割り当てで SBC データセンターに最も近い値が割り当てられていないことを示すために、このパラメーターを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8bbde-221">Microsoft only recommends setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="8bbde-222">なし</span><span class="sxs-lookup"><span data-stu-id="8bbde-222">None</span></span>|<span data-ttu-id="8bbde-223">ISO 形式の国コード</span><span class="sxs-lookup"><span data-stu-id="8bbde-223">Country codes in ISO format</span></span>||
|<span data-ttu-id="8bbde-224">いいえ</span><span class="sxs-lookup"><span data-stu-id="8bbde-224">No</span></span>|<span data-ttu-id="8bbde-225">有効</span><span class="sxs-lookup"><span data-stu-id="8bbde-225">Enabled</span></span>|<span data-ttu-id="8bbde-226">この SBC を発信通話に対して有効にします。</span><span class="sxs-lookup"><span data-stu-id="8bbde-226">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="8bbde-227">更新中またはメンテナンス中に、SBC を一時的に削除するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-227">Can be used to temporarily remove the SBC while it is being updated or during maintenance.</span></span> |<span data-ttu-id="8bbde-228">False</span><span class="sxs-lookup"><span data-stu-id="8bbde-228">False</span></span>|<span data-ttu-id="8bbde-229">True</span><span class="sxs-lookup"><span data-stu-id="8bbde-229">True</span></span><br/><span data-ttu-id="8bbde-230">False</span><span class="sxs-lookup"><span data-stu-id="8bbde-230">False</span></span>|<span data-ttu-id="8bbde-231">Boolean</span><span class="sxs-lookup"><span data-stu-id="8bbde-231">Boolean</span></span>|
 
## <a name="verify-the-sbc-connection"></a><span data-ttu-id="8bbde-232">SBC 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="8bbde-232">Verify the SBC connection</span></span> 

<span data-ttu-id="8bbde-233">接続を確認するには:</span><span class="sxs-lookup"><span data-stu-id="8bbde-233">To verify the connection:</span></span> 
- <span data-ttu-id="8bbde-234">SBC が、ペアリングされた SBCs のリストにあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-234">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="8bbde-235">SIP オプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-235">Validate SIP Options.</span></span> 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="8bbde-236">SBC が、ペアリングされた SBCs のリストにあるかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="8bbde-236">Check if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="8bbde-237">SBC を接続した後、リモート PowerShell セッションで次のコマンドを実行して、SBC が [ペアリングされた SBCs] のリストに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-237">After you connect the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session:</span></span> 

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

<span data-ttu-id="8bbde-238">次の例に示すように、ペアリングされたゲートウェイがリストに表示され、**有効になっている**パラメーターに**True**の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-238">The paired gateway should appear in the list as shown in the example below, and the **Enabled** parameter should display a value of **True**.</span></span> 


<span data-ttu-id="8bbde-239">戻り値:</span><span class="sxs-lookup"><span data-stu-id="8bbde-239">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

### <a name="validate-sip-options-flow"></a><span data-ttu-id="8bbde-240">SIP オプションのフローを検証する</span><span class="sxs-lookup"><span data-stu-id="8bbde-240">Validate SIP Options flow</span></span> 

<span data-ttu-id="8bbde-241">発信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用して、SBC が送信オプションメッセージに対する 200 OK 応答を受信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-241">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="8bbde-242">ダイレクトルーティングでは、着信オプションが表示され、着信のオプションメッセージの [連絡先ヘッダー] フィールドに設定された SBC FQDN への送信 SIP オプションメッセージの送信が開始されます。</span><span class="sxs-lookup"><span data-stu-id="8bbde-242">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="8bbde-243">着信 SIP オプションを使用してペアリングを検証するには、SBC 管理インターフェイスを使用します。また、SBC は直接ルーティングからのオプションメッセージに返信を送信し、送信する応答コードは 200 OK であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8bbde-243">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>


## <a name="see-also"></a><span data-ttu-id="8bbde-244">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bbde-244">See also</span></span>

[<span data-ttu-id="8bbde-245">ダイレクト ルーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="8bbde-245">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="8bbde-246">ダイレクト ルーティングを構成する</span><span class="sxs-lookup"><span data-stu-id="8bbde-246">Configure Direct Routing</span></span>](direct-routing-configure.md)
