---
title: ビジネス サーバー用の Skype でビデオの相互運用機能のサーバーを構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: '概要: ビジネス サーバーの Skype でビデオの相互運用機能サーバー (VIS) の役割を構成します。'
ms.openlocfilehash: 68931d9523fba92211295805e2f041869bc3e774
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982532"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>ビジネス サーバー用の Skype でビデオの相互運用機能のサーバーを構成します。
 
**の概要:** ビジネス サーバー用には、Skype でビデオの相互運用機能サーバー (VIS) の役割を構成します。
  
 VIS は Windows PowerShell を使用してビデオのトランクに関連付ける設定を構成します。 グローバル スコープのビデオ トランク構成は、VIS サービスがインストールされると作成されます。 作成されたビデオ トランク構成は、VIS によって、スコープがより具体的なビデオ トランク構成を持たないすべてのトランクに適用されます。 ビデオ トランク構成とは、ビデオ トランクに適用可能な設定のコレクションです。
  
## <a name="configure-video-trunk-and-dial-plan"></a>ビデオ トランクおよびダイヤル プランを構成する

VIS とビデオのすべてのゲートウェイとの間のトポロジ ドキュメントで定義されている、新しく定義した trunk(s) に関連するしようとしているビデオのトランク構成とダイヤルを指定するのには、次の Windows PowerShell コマンドを使用します。 設定はすべて、グローバル、サイト、サービス (ビデオ ゲートウェイ) の各レベルで指定できます。 
  
Skype あたり、ビジネス サーバー展開のグローバル スコープを持つダイヤル プランが作成されます。 作成されたダイヤル プランは、VIS によって、スコープがより具体的ないかなるダイヤル プランもないすべてのトランクに適用されます。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Windows PowerShell を使用して VIS を構成します。

1. VIS と Cisco ユニファイド コミュニケーション マネージャー (CallManager、または CUCM) との間のトランクを使用する新しいビデオのトランク構成 (設定のコレクション) を作成、次の Windows PowerShell コマンドレットを使用します。
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    変更する必要がある既存のビデオ ・ トランクがある場合は、次の Windows PowerShell コマンドレットを使用します。
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    、ビデオの特定のトランク構成に関連付けられている設定を表示するには、次の Windows PowerShell コマンドレットを使用します。
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    ビデオの特定のトランク構成を削除するには、次の Windows PowerShell コマンドレットを使用して (特定のトランクのスコープを設定した具体的にはビデオのトランク構成がない場合にビデオのグローバル スコープのトランク構成が適用されることに注意してください)。
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 次の Windows PowerShell コマンドレットを使用して、トランクに関連付けるダイヤル プランを確立します。
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

VIS と CUCM との予期される相互作用に干渉することになる既定のルールを上書きするには、**Remove-CsVoiceNormalizationRule** コマンドが必要です。
> [!NOTE]
> ダイヤル プランを削除するのには[削除 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)を使用することができます。
  
要求の URI には、E.164 ではない数値が含まれているビデオ ゲートウェイからのビデオ SIP トランク コール、VIS、関連付けられているトランクに関連付けられているダイヤル プランの名前を読み取り、要求 URI への招待を VI での電話のコンテキストの一部で、ダイヤル プラン名が含まれますS は、フロント エンドに送信します。 これによって、フロントエンドの翻訳アプリケーションがそのダイヤル プランに関連付けられている正規化ルールを抽出して要求 URI に適用します。
## <a name="trunk-configuration-options"></a>トランク構成のオプション

記載されているビデオのトランク構成の Windows PowerShell コマンドレットは、新しいビジネス サーバー 2015 の Skype にでした。 ビデオのトランク構成に関連付けられている設定は、簡単な説明を必要とします。
  
 **GatewaySendsRtcpForActiveCalls**このパラメーターは、かどうか RTCP パケット、VTC から用に送信される、VIS アクティブな呼び出しを指定します。 この場合のアクティブな通話とは、メディアが最低でも一方向に流れることのできる通話のことです。 GatewaySendsRtcpForActiveCalls を True に設定すると、30 秒を超える期間に RTCP パケットを受信しない場合、VIS は呼び出しを終了できます。 既定では**True です**。
  
 **GatewaySendsRtcpForCallsOnHold**このパラメーターは、保留状態に設定されている通話のトランクの間で送信される RTCP パケットを続けるし、いずれかの方向にフローするメディアのパケットはないかどうかを決定します。 RTCP パケットが呼び出しが保留中に、VIS に、VTC のフローがない場合、VIS では、呼び出しを終了できます。 既定では**True です**。 SIPTransport プロトコルは、TCP に設定されている場合、この設定は無視されます。
  
 **EnableMediaEncryptionForSipOverTls**このパラメーターは、有効または、SIPTransport プロトコルは TLS に設定されている場合は、メディアの SRTP を無効にします。 既定では**True です**。 SIPTransport プロトコルは、TCP に設定されている場合、この設定は無視されます。
  
 **EnableSessionTimer**このパラメーターは、有効または、ビデオの SIP トランクに関連付けられている各 SIP ダイアログの VIS 側で、セッション タイマーを無効にします。 既定では**False です**。
  
 **ForwardErrorCorrectionType**フォワード エラー訂正 (FEC) ビデオ ストリームのビデオの相互運用機能のサーバーとビデオのゲートウェイとの間の区間に適用されるかどうかを判断するこのパラメーターを使用します。 [なし] に設定 ForwardErrorCorrectionType は、FEC VIS とビデオ ゲートウェイ/VTC の間で無効になります。 "Cisco"に ForwardErrorCorrectionType を設定すると、FEC シスコ、シスコ ユニファイド コミュニケーション マネージャー (CUCM) などによってビデオ ゲートウェイとの互換性が有効になります。 既定では**ないです**。
  
## <a name="see-also"></a>関連項目

[CUCM を Skype ビジネス サーバーの相互運用の構成します。](configure-cucm-for-interoperation.md)