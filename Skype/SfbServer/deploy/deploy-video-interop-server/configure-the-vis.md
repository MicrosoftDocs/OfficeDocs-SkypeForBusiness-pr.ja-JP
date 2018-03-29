---
title: Skype for Business Server 2015 でのビデオ相互運用サーバーの構成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: '概要: ビジネス サーバー 2015 の Skype でビデオの相互運用機能サーバー (VIS) の役割を構成します。'
ms.openlocfilehash: 7192135f5822e3086de7533afbdc8492194a3889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server-2015"></a><span data-ttu-id="d0929-103">Skype for Business Server 2015 でのビデオ相互運用サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="d0929-103">Configure the Video Interop Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d0929-104">**の概要:**ビジネス サーバー 2015 の Skype でのビデオの相互運用機能サーバー (VIS) の役割を構成します。</span><span class="sxs-lookup"><span data-stu-id="d0929-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="d0929-105">VIS は Windows PowerShell を使用してビデオのトランクに関連付ける設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d0929-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="d0929-106">グローバル スコープのビデオ トランク構成は、VIS サービスがインストールされると作成されます。</span><span class="sxs-lookup"><span data-stu-id="d0929-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="d0929-107">作成されたビデオ トランク構成は、VIS によって、スコープがより具体的なビデオ トランク構成を持たないすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0929-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="d0929-108">ビデオ トランク構成とは、ビデオ トランクに適用可能な設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d0929-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="d0929-109">ビデオ トランクおよびダイヤル プランを構成する</span><span class="sxs-lookup"><span data-stu-id="d0929-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="d0929-110">VIS とビデオのすべてのゲートウェイとの間のトポロジ ドキュメントで定義されている、新しく定義した trunk(s) に関連するしようとしているビデオのトランク構成とダイヤルを指定するのには、次の Windows PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0929-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="d0929-111">設定はすべて、グローバル、サイト、サービス (ビデオ ゲートウェイ) の各レベルで指定できます。</span><span class="sxs-lookup"><span data-stu-id="d0929-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="d0929-112">Skype あたり、ビジネス サーバー展開のグローバル スコープを持つダイヤル プランが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d0929-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="d0929-113">作成されたダイヤル プランは、VIS によって、スコープがより具体的ないかなるダイヤル プランもないすべてのトランクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0929-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="d0929-114">Windows PowerShell を使用して VIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="d0929-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="d0929-115">VIS と次の Windows PowerShell コマンドレットを使用して、CUCM の間のトランクを使用するには、新しいビデオのトランク構成 (設定のコレクション) を作成します。</span><span class="sxs-lookup"><span data-stu-id="d0929-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and CUCM, using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="d0929-116">変更する必要がある既存のビデオ ・ トランクがある場合は、次の Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0929-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="d0929-117">、ビデオの特定のトランク構成に関連付けられている設定を表示するには、次の Windows PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0929-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="d0929-118">ビデオの特定のトランク構成を削除するには、次の Windows PowerShell コマンドレットを使用して (特定のトランクのスコープを設定した具体的にはビデオのトランク構成がない場合にビデオのグローバル スコープのトランク構成が適用されることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="d0929-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="d0929-119">次の Windows PowerShell コマンドレットを使用して、トランクに関連付けるダイヤル プランを確立します。</span><span class="sxs-lookup"><span data-stu-id="d0929-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="d0929-120">VIS と CUCM との予期される相互作用に干渉することになる既定のルールを上書きするには、**Remove-CsVoiceNormalizationRule** コマンドが必要です。</span><span class="sxs-lookup"><span data-stu-id="d0929-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="d0929-121">ダイヤル プランを削除するのには[削除 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d0929-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="d0929-122">要求の URI には、E.164 ではない数値が含まれているビデオ ゲートウェイからのビデオ SIP トランク コール、VIS、関連付けられているトランクに関連付けられているダイヤル プランの名前を読み取り、要求 URI への招待を VI での電話のコンテキストの一部で、ダイヤル プラン名が含まれますS は、フロント エンドに送信します。</span><span class="sxs-lookup"><span data-stu-id="d0929-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="d0929-123">これによって、フロントエンドの翻訳アプリケーションがそのダイヤル プランに関連付けられている正規化ルールを抽出して要求 URI に適用します。</span><span class="sxs-lookup"><span data-stu-id="d0929-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="d0929-124">トランク構成のオプション</span><span class="sxs-lookup"><span data-stu-id="d0929-124">Trunk configuration options</span></span>

<span data-ttu-id="d0929-125">記載されているビデオのトランク構成の Windows PowerShell コマンドレットは、ビジネス サーバー 2015 の Skype にします。</span><span class="sxs-lookup"><span data-stu-id="d0929-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously are new to the Skype for Business Server 2015.</span></span> <span data-ttu-id="d0929-126">ビデオのトランク構成に関連付けられている設定は、簡単な説明を必要とします。</span><span class="sxs-lookup"><span data-stu-id="d0929-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="d0929-127">**GatewaySendsRtcpForActiveCalls**このパラメーターは、かどうか RTCP パケット、VTC から用に送信される、VIS アクティブな呼び出しを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0929-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="d0929-128">この場合のアクティブな通話とは、メディアが最低でも一方向に流れることのできる通話のことです。</span><span class="sxs-lookup"><span data-stu-id="d0929-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="d0929-129">GatewaySendsRtcpForActiveCalls を True に設定すると、30 秒を超える期間に RTCP パケットを受信しない場合、VIS は呼び出しを終了できます。</span><span class="sxs-lookup"><span data-stu-id="d0929-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="d0929-130">既定では**True です**。</span><span class="sxs-lookup"><span data-stu-id="d0929-130">The default is **True**.</span></span>
  
 <span data-ttu-id="d0929-131">**GatewaySendsRtcpForCallsOnHold**このパラメーターは、保留状態に設定されている通話のトランクの間で送信される RTCP パケットを続けるし、いずれかの方向にフローするメディアのパケットはないかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d0929-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="d0929-132">RTCP パケットが呼び出しが保留中に、VIS に、VTC のフローがない場合、VIS では、呼び出しを終了できます。</span><span class="sxs-lookup"><span data-stu-id="d0929-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="d0929-133">既定では**True です**。</span><span class="sxs-lookup"><span data-stu-id="d0929-133">The default is **True**.</span></span> <span data-ttu-id="d0929-134">SIPTransport プロトコルは、TCP に設定されている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d0929-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="d0929-135">**EnableMediaEncryptionForSipOverTls**このパラメーターは、有効または、SIPTransport プロトコルは TLS に設定されている場合は、メディアの SRTP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0929-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="d0929-136">既定では**True です**。</span><span class="sxs-lookup"><span data-stu-id="d0929-136">The default is **True**.</span></span> <span data-ttu-id="d0929-137">SIPTransport プロトコルは、TCP に設定されている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d0929-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="d0929-138">**EnableSessionTimer**このパラメーターは、有効または、ビデオの SIP トランクに関連付けられている各 SIP ダイアログの VIS 側で、セッション タイマーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d0929-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="d0929-139">既定では**False です**。</span><span class="sxs-lookup"><span data-stu-id="d0929-139">The default is **False**.</span></span>
  
 <span data-ttu-id="d0929-140">**ForwardErrorCorrectionType**フォワード エラー訂正 (FEC) ビデオ ストリームのビデオの相互運用機能のサーバーとビデオのゲートウェイとの間の区間に適用されるかどうかを判断するこのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d0929-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="d0929-141">[なし] に設定 ForwardErrorCorrectionType は、FEC VIS とビデオ ゲートウェイ/VTC の間で無効になります。</span><span class="sxs-lookup"><span data-stu-id="d0929-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="d0929-142">"Cisco"に ForwardErrorCorrectionType を設定すると、FEC シスコ、シスコ ユニファイド コミュニケーション マネージャー (CUCM) などによってビデオ ゲートウェイとの互換性が有効になります。</span><span class="sxs-lookup"><span data-stu-id="d0929-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="d0929-143">既定では**ないです**。</span><span class="sxs-lookup"><span data-stu-id="d0929-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d0929-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0929-144">See also</span></span>

#### 

[<span data-ttu-id="d0929-145">ビジネス サーバー 2015 の Skype での相互運用のため CUCM を構成します。</span><span class="sxs-lookup"><span data-stu-id="d0929-145">Configure CUCM for Interoperation with Skype for Business Server 2015</span></span>](configure-cucm-for-interoperation.md)

