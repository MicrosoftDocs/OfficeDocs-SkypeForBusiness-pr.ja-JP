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
ms.openlocfilehash: 84ab821249ae388bc1ba0dc41cb980c90d4f0853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820697"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Skype for Business Server でビデオ相互運用サーバーを構成する
 
**概要:** Skype for Business Server でビデオ相互運用サーバー (VIS) の役割を構成します。
  
 VIS がビデオ トランクに関連付ける設定を構成するには、次のWindows PowerShell。 グローバル スコープを持つビデオ トランク構成は、VIS サービスがインストールされると作成されます。 このビデオ トランク構成は、VIS によって、より具体的なスコープを持つビデオ トランク構成を持たないすべてのトランクに適用されます。 ビデオ トランク構成は、ビデオ トランクに適用可能な設定のコレクションです。
  
## <a name="configure-video-trunk-and-dial-plan"></a>ビデオ トランクとダイヤル プランを構成する

次の Windows PowerShell コマンドを使用して、VIS とすべてのビデオ ゲートウェイの間のトポロジ ドキュメントで定義された新しく定義されたトランクに関連付けられるビデオ トランク構成とダイヤル プランを指定します。 これらの設定はすべて、グローバル、サイト、またはサービス (ビデオ ゲートウェイ) レベルで設定できます。 
  
グローバル スコープを持つダイヤル プランは、Skype for Business Server 展開ごとに作成されます。 このダイヤル プランは、VIS によって、より具体的なスコープを持つダイヤル プランを持たないすべてのトランクに適用されます。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>次のコマンドを使用して VIS をWindows PowerShell

1. 次の Windows PowerShell コマンドレットを使用して、VIS と Cisco Unified Communications Manager (CallManager、または CUCM) の間のトランクで使用する新しいビデオ トランク構成 (設定のコレクション) を作成します。
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    既存のビデオ トランクを変更する必要がある場合は、次のコマンドレットをWindows PowerShellします。
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    特定のビデオ トランク構成に関連付けられている設定を表示するには、次のコマンドレットをWindows PowerShellします。
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    特定のビデオ トランク構成を削除するには、次の Windows PowerShell コマンドレットを使用します (特定のトランクに対して、より具体的にスコープが設定されたビデオ トランク構成が設定されていない場合は、グローバルスコープのビデオ トランク構成が適用されます)。
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 次のコマンドレットを使用して、トランクに関連付けるダイヤル Windows PowerShellします。
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

**Remove-CsVoiceNormalizationRule** コマンドは、想定される VIS および CUCM の操作を妨げる既定のルールを上書きするために必要です。
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) を使用してダイヤル プランを削除できます。
  
要求 URI に E.164 以外の番号が含まれるビデオ ゲートウェイからのビデオ SIP トランク通話の場合、VIS は関連付けられたトランクに関連付けられたダイヤル プランの名前を読み取り、VIS がフロント エンドに送信する招待の要求 URI の電話コンテキスト部分にダイヤル プラン名を含める必要があります。 次に、フロント エンドの変換アプリケーションは、ダイヤル プランに関連付けられている正規化ルールを抽出し、要求 URI に適用します。
## <a name="trunk-configuration-options"></a>トランク構成オプション

前述Windows PowerShellビデオ トランク構成のコマンドレットは、Skype for Business Server 2015 では新しく追加されたコマンドレットです。 ビデオ トランク構成に関連付けられている設定については、簡単な説明が必要です。
  
 **GatewaySendsRtcpForActiveCalls** このパラメーターは、RTCP パケットを VTC からアクティブな呼び出しの VIS に送信するかどうかを決定します。 この文脈でアクティブな通話とは、メディアが少なくとも一方向へのフローを許可されている通話のことです。 GatewaySendsRtcpForActiveCalls が True に設定されている場合、30 秒を超える期間 RTCP パケットを受信しない場合、VIS は呼び出しを終了できます。 既定では **True です** 。
  
 **GatewaySendsRtcpForCallsOnHold** このパラメーターは、保留にされた通話に対して RTCP パケットがトランクを通して送信され続けるかどうか、およびメディア パケットがどちらの方向にもフローしないか決定します。 呼び出しが保留の間に VTC から VIS に流れる RTCP パケットがない場合、VIS は通話を終了できます。 既定では **True です** 。 SIPTransport プロトコルが TCP に設定されている場合、この設定は無視されます。
  
 **EnableMediaEncryptionForSipOverTls** このパラメーターは、SIPTransport プロトコルが TLS に設定されている場合にメディアの SRTP を有効または無効にします。 既定では **True です** 。 SIPTransport プロトコルが TCP に設定されている場合、この設定は無視されます。
  
 **EnableSessionTimer** このパラメーターは、ビデオ SIP トランクに関連付けられた各 SIP ダイアログの VIS 側のセッション タイマーを有効または無効にします。 既定値は **False** です。
  
 **ForwardErrorCorrectionType** このパラメーターは、ビデオ ストリームの前方エラー訂正 (FEC) がビデオ相互運用サーバーとビデオ ゲートウェイの間の脚に適用されるかどうかを判断するために使用します。 ForwardErrorCorrectionType を "None" に設定すると、VIS とビデオ ゲートウェイ/VTC の間の FEC が無効になります。 ForwardErrorCorrectionType を "Cisco" に設定すると、Cisco Unified Communications Manager (CUCM) などの Cisco によるビデオ ゲートウェイと FEC との互換性が有効になります。 既定値は [**なし**] です。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server との相互運用のための CUCM の構成](configure-cucm-for-interoperation.md)
