---
title: Skype for Business Server でビデオ相互運用サーバーを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: '概要: Skype for Business Server でビデオ相互運用サーバー (VIS) の役割を構成します。'
ms.openlocfilehash: 8d5da36d07583cc1c20407d842b94531062947ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120306"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="60415-103">Skype for Business Server でビデオ相互運用サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="60415-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="60415-104">**概要:** Skype for Business Server でビデオ相互運用サーバー (VIS) の役割を構成します。</span><span class="sxs-lookup"><span data-stu-id="60415-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="60415-105">VIS がビデオ トランクに関連付ける設定を、ビデオ トランクを使用して構成Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="60415-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="60415-106">グローバル スコープを持つビデオ トランク構成は、VIS サービスがインストールされると作成されます。</span><span class="sxs-lookup"><span data-stu-id="60415-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="60415-107">このビデオ トランク構成は、VIS によって、より具体的なスコープを持つビデオ トランク構成を持つすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="60415-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="60415-108">ビデオ トランクの構成は、ビデオ トランクに適用可能な設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="60415-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="60415-109">ビデオ トランクとダイヤル プランの構成</span><span class="sxs-lookup"><span data-stu-id="60415-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="60415-110">次の Windows PowerShell コマンドを使用して、VIS とすべてのビデオ ゲートウェイの間のトポロジ ドキュメントで定義された新しく定義されたトランクに関連付けられるビデオ トランク構成とダイヤル プランを指定します。</span><span class="sxs-lookup"><span data-stu-id="60415-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="60415-111">これらの設定はすべて、グローバル、サイト、またはサービス (ビデオ ゲートウェイ) レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="60415-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="60415-112">グローバル スコープを持つダイヤル プランは、Skype for Business Server 展開ごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="60415-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="60415-113">このダイヤル プランは、VIS によって、より具体的なスコープを持つダイヤル プランを持つすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="60415-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="60415-114">デバイスを使用して VIS をWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="60415-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="60415-115">次のコマンドレットを使用して、VIS と Cisco Unified Communications Manager (CallManager、または CUCM) の間のトランクで使用する新しいビデオ トランク構成 (設定のコレクション) をWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="60415-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="60415-116">変更する必要がある既存のビデオ トランクがある場合は、次のコマンドレットWindows PowerShellしてください。</span><span class="sxs-lookup"><span data-stu-id="60415-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="60415-117">特定のビデオ トランク構成に関連付けられている設定を表示するには、次のコマンドレットをWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="60415-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="60415-118">特定のビデオ トランク構成を削除するには、次の Windows PowerShell コマンドレットを使用します (特定のトランクに対してより具体的にスコープ設定されたビデオ トランク構成がない場合は、グローバルスコープのビデオ トランク構成が適用されます)。</span><span class="sxs-lookup"><span data-stu-id="60415-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="60415-119">次のコマンドレットを使用して、トランクに関連付けるダイヤル プランWindows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="60415-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="60415-120">**Remove-CsVoiceNormalizationRule** コマンドは、予期される VIS および CUCM の相互作用を妨げる既定のルールを上書きするために必要です。</span><span class="sxs-lookup"><span data-stu-id="60415-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="60415-121">[Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) を使用してダイヤル プランを削除できます。</span><span class="sxs-lookup"><span data-stu-id="60415-121">[Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="60415-122">要求 URI に E.164 以外の番号が含まれるビデオ ゲートウェイからのビデオ SIP トランク呼び出しの場合、VIS は関連付けられたトランクに関連付けられたダイヤル プランの名前を読み取り、VIS がフロントエンドに送信する招待の要求 URI の電話コンテキスト部分にダイヤル プラン名を含める予定です。</span><span class="sxs-lookup"><span data-stu-id="60415-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="60415-123">フロントエンドの変換アプリケーションは、ダイヤル プランに関連付けられた正規化ルールを抽出し、要求 URI に適用します。</span><span class="sxs-lookup"><span data-stu-id="60415-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="60415-124">トランク構成オプション</span><span class="sxs-lookup"><span data-stu-id="60415-124">Trunk configuration options</span></span>

<span data-ttu-id="60415-125">前述Windows PowerShellのビデオ トランク構成のコマンドレットは、Skype for Business Server 2015 の新機能でした。</span><span class="sxs-lookup"><span data-stu-id="60415-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="60415-126">ビデオ トランク構成に関連付けられている設定については、簡単な説明が必要です。</span><span class="sxs-lookup"><span data-stu-id="60415-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="60415-127">**GatewaySendsRtcpForActiveCalls** このパラメーターは、アクティブな呼び出しのために RTCP パケットを VTC から VIS に送信するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="60415-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="60415-128">この文脈でアクティブな通話とは、メディアが少なくとも一方向へのフローを許可されている通話のことです。</span><span class="sxs-lookup"><span data-stu-id="60415-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="60415-129">GatewaySendsRtcpForActiveCalls が True に設定されている場合、30 秒を超える期間 RTCP パケットを受信しない場合、VIS は呼び出しを終了できます。</span><span class="sxs-lookup"><span data-stu-id="60415-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="60415-130">既定では **True です** 。</span><span class="sxs-lookup"><span data-stu-id="60415-130">The default is **True**.</span></span>
  
 <span data-ttu-id="60415-131">**GatewaySendsRtcpForCallsOnHold** このパラメーターは、保留にされた通話に対して RTCP パケットをトランク間で送信し続け、どちらの方向にもメディア パケットが流れ込む必要がないかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="60415-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="60415-132">通話が保留の間に VTC から VIS に流れる RTCP パケットがない場合、VIS は通話を終了できます。</span><span class="sxs-lookup"><span data-stu-id="60415-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="60415-133">既定では **True です** 。</span><span class="sxs-lookup"><span data-stu-id="60415-133">The default is **True**.</span></span> <span data-ttu-id="60415-134">SIPTransport プロトコルが TCP に設定されている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="60415-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="60415-135">**EnableMediaEncryptionForSipOverTls** このパラメーターは、SIPTransport プロトコルが TLS に設定されている場合、メディアの SRTP を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="60415-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="60415-136">既定では **True です** 。</span><span class="sxs-lookup"><span data-stu-id="60415-136">The default is **True**.</span></span> <span data-ttu-id="60415-137">SIPTransport プロトコルが TCP に設定されている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="60415-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="60415-138">**EnableSessionTimer** このパラメーターは、ビデオ SIP トランクに関連付けられた SIP ダイアログごとに VIS 側のセッション タイマーを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="60415-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="60415-139">既定値は **False** です。</span><span class="sxs-lookup"><span data-stu-id="60415-139">The default is **False**.</span></span>
  
 <span data-ttu-id="60415-140">**ForwardErrorCorrectionType** このパラメーターは、ビデオ ストリームの前方エラー修正 (FEC) をビデオ相互運用サーバーとビデオ ゲートウェイの間の脚に適用するかどうかを判断するために使用します。</span><span class="sxs-lookup"><span data-stu-id="60415-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="60415-141">ForwardErrorCorrectionType を "None" に設定すると、VIS とビデオ ゲートウェイ/VTC の間で FEC がオフになります。</span><span class="sxs-lookup"><span data-stu-id="60415-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="60415-142">ForwardErrorCorrectionType を "Cisco" に設定すると、Cisco Unified Communications Manager (CUCM) などの Cisco によるビデオ ゲートウェイとの FEC 互換性が有効になります。</span><span class="sxs-lookup"><span data-stu-id="60415-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="60415-143">既定値は [**なし**] です。</span><span class="sxs-lookup"><span data-stu-id="60415-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="60415-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="60415-144">See also</span></span>

[<span data-ttu-id="60415-145">Skype for Business Server との相互運用のための CUCM の構成</span><span class="sxs-lookup"><span data-stu-id="60415-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)