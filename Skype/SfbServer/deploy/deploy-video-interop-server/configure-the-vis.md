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
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Skype for Business Server でビデオ相互運用サーバーを構成する
 
**概要:** Skype for Business Server でビデオ相互運用サーバー (VIS) の役割を構成します。
  
 VIS がビデオ トランクに関連付ける設定を、ビデオ トランクを使用して構成Windows PowerShell。 グローバル スコープを持つビデオ トランク構成は、VIS サービスがインストールされると作成されます。 このビデオ トランク構成は、VIS によって、より具体的なスコープを持つビデオ トランク構成を持つすべてのトランクに適用されます。 ビデオ トランクの構成は、ビデオ トランクに適用可能な設定のコレクションです。
  
## <a name="configure-video-trunk-and-dial-plan"></a>ビデオ トランクとダイヤル プランの構成

次の Windows PowerShell コマンドを使用して、VIS とすべてのビデオ ゲートウェイの間のトポロジ ドキュメントで定義された新しく定義されたトランクに関連付けられるビデオ トランク構成とダイヤル プランを指定します。 これらの設定はすべて、グローバル、サイト、またはサービス (ビデオ ゲートウェイ) レベルで設定できます。 
  
グローバル スコープを持つダイヤル プランは、Skype for Business Server 展開ごとに作成されます。 このダイヤル プランは、VIS によって、より具体的なスコープを持つダイヤル プランを持つすべてのトランクに適用されます。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>デバイスを使用して VIS をWindows PowerShell

1. 次のコマンドレットを使用して、VIS と Cisco Unified Communications Manager (CallManager、または CUCM) の間のトランクで使用する新しいビデオ トランク構成 (設定のコレクション) をWindows PowerShellします。
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    変更する必要がある既存のビデオ トランクがある場合は、次のコマンドレットWindows PowerShellしてください。
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    特定のビデオ トランク構成に関連付けられている設定を表示するには、次のコマンドレットをWindows PowerShellします。
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    特定のビデオ トランク構成を削除するには、次の Windows PowerShell コマンドレットを使用します (特定のトランクに対してより具体的にスコープ設定されたビデオ トランク構成がない場合は、グローバルスコープのビデオ トランク構成が適用されます)。
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 次のコマンドレットを使用して、トランクに関連付けるダイヤル プランWindows PowerShellします。
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

**Remove-CsVoiceNormalizationRule** コマンドは、予期される VIS および CUCM の相互作用を妨げる既定のルールを上書きするために必要です。
> [!NOTE]
> [Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) を使用してダイヤル プランを削除できます。
  
要求 URI に E.164 以外の番号が含まれるビデオ ゲートウェイからのビデオ SIP トランク呼び出しの場合、VIS は関連付けられたトランクに関連付けられたダイヤル プランの名前を読み取り、VIS がフロントエンドに送信する招待の要求 URI の電話コンテキスト部分にダイヤル プラン名を含める予定です。 フロントエンドの変換アプリケーションは、ダイヤル プランに関連付けられた正規化ルールを抽出し、要求 URI に適用します。
## <a name="trunk-configuration-options"></a>トランク構成オプション

前述Windows PowerShellのビデオ トランク構成のコマンドレットは、Skype for Business Server 2015 の新機能でした。 ビデオ トランク構成に関連付けられている設定については、簡単な説明が必要です。
  
 **GatewaySendsRtcpForActiveCalls** このパラメーターは、アクティブな呼び出しのために RTCP パケットを VTC から VIS に送信するかどうかを決定します。 この文脈でアクティブな通話とは、メディアが少なくとも一方向へのフローを許可されている通話のことです。 GatewaySendsRtcpForActiveCalls が True に設定されている場合、30 秒を超える期間 RTCP パケットを受信しない場合、VIS は呼び出しを終了できます。 既定では **True です** 。
  
 **GatewaySendsRtcpForCallsOnHold** このパラメーターは、保留にされた通話に対して RTCP パケットをトランク間で送信し続け、どちらの方向にもメディア パケットが流れ込む必要がないかどうかを決定します。 通話が保留の間に VTC から VIS に流れる RTCP パケットがない場合、VIS は通話を終了できます。 既定では **True です** 。 SIPTransport プロトコルが TCP に設定されている場合、この設定は無視されます。
  
 **EnableMediaEncryptionForSipOverTls** このパラメーターは、SIPTransport プロトコルが TLS に設定されている場合、メディアの SRTP を有効または無効にします。 既定では **True です** 。 SIPTransport プロトコルが TCP に設定されている場合、この設定は無視されます。
  
 **EnableSessionTimer** このパラメーターは、ビデオ SIP トランクに関連付けられた SIP ダイアログごとに VIS 側のセッション タイマーを有効または無効にします。 既定値は **False** です。
  
 **ForwardErrorCorrectionType** このパラメーターは、ビデオ ストリームの前方エラー修正 (FEC) をビデオ相互運用サーバーとビデオ ゲートウェイの間の脚に適用するかどうかを判断するために使用します。 ForwardErrorCorrectionType を "None" に設定すると、VIS とビデオ ゲートウェイ/VTC の間で FEC がオフになります。 ForwardErrorCorrectionType を "Cisco" に設定すると、Cisco Unified Communications Manager (CUCM) などの Cisco によるビデオ ゲートウェイとの FEC 互換性が有効になります。 既定値は [**なし**] です。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server との相互運用のための CUCM の構成](configure-cucm-for-interoperation.md)