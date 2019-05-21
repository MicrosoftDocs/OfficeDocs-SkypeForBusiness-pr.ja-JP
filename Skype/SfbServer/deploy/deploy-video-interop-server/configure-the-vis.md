---
title: Skype for Business Server でビデオ相互運用機能サーバーを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: '概要: Skype for Business Server のビデオ相互運用機能サーバー (VIS) の役割を構成します。'
ms.openlocfilehash: 3c0b211897afdde0fc0a01e255cdc14bc466f65c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302743"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="6ab25-103">Skype for Business Server でビデオ相互運用機能サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="6ab25-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="6ab25-104">**概要:** Skype for Business Server のビデオ相互運用機能サーバー (VIS) の役割を構成します。</span><span class="sxs-lookup"><span data-stu-id="6ab25-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="6ab25-105">Windows PowerShell を使用して、VIS がビデオ trunks と関連付ける設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6ab25-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="6ab25-106">グローバル スコープのビデオ トランク構成は、VIS サービスがインストールされると作成されます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="6ab25-107">作成されたビデオ トランク構成は、VIS によって、スコープがより具体的なビデオ トランク構成を持たないすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="6ab25-108">ビデオ トランク構成とは、ビデオ トランクに適用可能な設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="6ab25-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="6ab25-109">ビデオ トランクおよびダイヤル プランを構成する</span><span class="sxs-lookup"><span data-stu-id="6ab25-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="6ab25-110">次の Windows PowerShell コマンドを使用して、VIS とすべてのビデオゲートウェイの間で、トポロジドキュメントで定義された新規に定義されたトランクに関連付けられるように、ビデオトランクの構成とダイヤルプランを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ab25-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="6ab25-111">設定はすべて、グローバル、サイト、サービス (ビデオ ゲートウェイ) の各レベルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="6ab25-112">グローバルスコープのダイヤルプランは、Skype for Business Server 展開ごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="6ab25-113">作成されたダイヤル プランは、VIS によって、スコープがより具体的ないかなるダイヤル プランもないすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="6ab25-114">Windows PowerShell を使用して VIS を構成する</span><span class="sxs-lookup"><span data-stu-id="6ab25-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="6ab25-115">次の Windows PowerShell コマンドレットを使用して、VIS と Cisco ユニファイドコミュニケーションマネージャー (CallManager または CUCM) 間のトランクで使用する新しいビデオトランク構成 (設定のコレクション) を作成します。</span><span class="sxs-lookup"><span data-stu-id="6ab25-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="6ab25-116">既存のビデオトランクを変更する必要がある場合は、次の Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ab25-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="6ab25-117">特定のビデオトランク構成に関連する設定を表示するには、次の Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ab25-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="6ab25-118">特定のビデオトランクの構成を削除するには、次の Windows PowerShell コマンドレットを使用します (特定のトランクに対して明示的に指定されたビデオトランク構成がない場合は、グローバルにスコープ設定されたビデオトランク構成が適用されることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6ab25-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="6ab25-119">次の Windows PowerShell コマンドレットを使用して、トランクに関連付けるダイヤルプランを確立します。</span><span class="sxs-lookup"><span data-stu-id="6ab25-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="6ab25-120">VIS と CUCM との予期される相互作用に干渉することになる既定のルールを上書きするには、**Remove-CsVoiceNormalizationRule** コマンドが必要です。</span><span class="sxs-lookup"><span data-stu-id="6ab25-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="6ab25-121">[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)を使用して、ダイヤルプランを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="6ab25-122">要求 URI に E 以外の番号が含まれているビデオゲートウェイからのビデオ通話トランク呼び出しの場合、VIS は、関連付けられたトランクに関連付けられているダイヤルプランの名前を読み取ります。また、そのダイヤルプラン名は、[Invite] の要求 URI の電話コンテキスト部分に含まれます。S では、フロントエンドに送信します。</span><span class="sxs-lookup"><span data-stu-id="6ab25-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="6ab25-123">これによって、フロントエンドの翻訳アプリケーションがそのダイヤル プランに関連付けられている正規化ルールを抽出して要求 URI に適用します。</span><span class="sxs-lookup"><span data-stu-id="6ab25-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="6ab25-124">トランク構成のオプション</span><span class="sxs-lookup"><span data-stu-id="6ab25-124">Trunk configuration options</span></span>

<span data-ttu-id="6ab25-125">前に説明したビデオトランク構成用の Windows PowerShell コマンドレットは、Skype for Business Server 2015 に新しく追加されました。</span><span class="sxs-lookup"><span data-stu-id="6ab25-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="6ab25-126">ビデオトランク構成に関連する設定については、簡単に説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ab25-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="6ab25-127">**GatewaySendsRtcpForActiveCalls**このパラメーターは、RTCP パケットを VTC から VIS に送信するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ab25-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="6ab25-128">この場合のアクティブな通話とは、メディアが最低でも一方向に流れることのできる通話のことです。</span><span class="sxs-lookup"><span data-stu-id="6ab25-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="6ab25-129">GatewaySendsRtcpForActiveCalls が True に設定されている場合、VIS は、30秒を超える期間に対して RTCP パケットを受信しない場合、通話を終了できます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="6ab25-130">既定値は**True**です。</span><span class="sxs-lookup"><span data-stu-id="6ab25-130">The default is **True**.</span></span>
  
 <span data-ttu-id="6ab25-131">**Gatewaysendsrtcpforcallsonhold**このパラメーターは、保留になっている通話に対して、RTCP パケットをトランク経由で送信するかどうかを決定します。どの方向にもメディアパケットが流れません。</span><span class="sxs-lookup"><span data-stu-id="6ab25-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="6ab25-132">VIS は、通話が保留中のときに VTC から VIS に流れるパケットがない場合に、通話を終了することができます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="6ab25-133">既定値は**True**です。</span><span class="sxs-lookup"><span data-stu-id="6ab25-133">The default is **True**.</span></span> <span data-ttu-id="6ab25-134">SIPTransport プロトコルが TCP に設定されている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="6ab25-135">**EnableMediaEncryptionForSipOverTls**このパラメーターは、SIPTransport プロトコルが TLS に設定されている場合に、メディアの SRTP を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6ab25-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="6ab25-136">既定値は**True**です。</span><span class="sxs-lookup"><span data-stu-id="6ab25-136">The default is **True**.</span></span> <span data-ttu-id="6ab25-137">SIPTransport プロトコルが TCP に設定されている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="6ab25-138">**Enablesessiontimer**このパラメーターは、ビデオ SIP トランクに関連付けられている各 SIP ダイアログの VIS side のセッションタイマーを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6ab25-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="6ab25-139">既定値は**False**です。</span><span class="sxs-lookup"><span data-stu-id="6ab25-139">The default is **False**.</span></span>
  
 <span data-ttu-id="6ab25-140">**Forwarderror正しく Tiontype**このパラメーターは、ビデオの相互運用サーバーとビデオゲートウェイの間の区間に、ビデオストリームの転送エラー訂正 (FEC) が適用されるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ab25-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="6ab25-141">ForwardErrorCorrectionType を "None" に設定すると、VIS とビデオゲートウェイ/VTC の間で FEC がオフになります。</span><span class="sxs-lookup"><span data-stu-id="6ab25-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="6ab25-142">ForwarderrorFEC Type を "Cisco" に設定すると、cisco ユニファイドコミュニケーションマネージャー (CUCM) などの Cisco のビデオゲートウェイとの互換性が可能になります。</span><span class="sxs-lookup"><span data-stu-id="6ab25-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="6ab25-143">既定値は **[なし**] です。</span><span class="sxs-lookup"><span data-stu-id="6ab25-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6ab25-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ab25-144">See also</span></span>

[<span data-ttu-id="6ab25-145">Skype for Business Server との相互運用用に CUCM を構成する</span><span class="sxs-lookup"><span data-stu-id="6ab25-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
