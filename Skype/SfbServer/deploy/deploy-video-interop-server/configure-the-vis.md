---
title: Skype for Business Server でビデオ相互運用機能サーバーを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: '概要: Skype for Business Server のビデオ相互運用機能サーバー (VIS) の役割を構成します。'
ms.openlocfilehash: 2618a7829fde79bd63eb2c3c91dbe921530e3b04
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798064"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Skype for Business Server でビデオ相互運用機能サーバーを構成する
 
**概要:** Skype for Business Server のビデオ相互運用機能サーバー (VIS) の役割を構成します。
  
 Windows PowerShell を使用して、VIS がビデオ trunks と関連付ける設定を構成します。 グローバル スコープのビデオ トランク構成は、VIS サービスがインストールされると作成されます。 作成されたビデオ トランク構成は、VIS によって、スコープがより具体的なビデオ トランク構成を持たないすべてのトランクに適用されます。 ビデオ トランク構成とは、ビデオ トランクに適用可能な設定のコレクションです。
  
## <a name="configure-video-trunk-and-dial-plan"></a>ビデオ トランクおよびダイヤル プランを構成する

次の Windows PowerShell コマンドを使用して、VIS とすべてのビデオゲートウェイの間で、トポロジドキュメントで定義された新規に定義されたトランクに関連付けられるように、ビデオトランクの構成とダイヤルプランを指定します。 設定はすべて、グローバル、サイト、サービス (ビデオ ゲートウェイ) の各レベルで指定できます。 
  
グローバルスコープのダイヤルプランは、Skype for Business Server 展開ごとに作成されます。 作成されたダイヤル プランは、VIS によって、スコープがより具体的ないかなるダイヤル プランもないすべてのトランクに適用されます。 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Windows PowerShell を使用して VIS を構成する

1. 次の Windows PowerShell コマンドレットを使用して、VIS と Cisco ユニファイドコミュニケーションマネージャー (CallManager または CUCM) 間のトランクで使用する新しいビデオトランク構成 (設定のコレクション) を作成します。
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    既存のビデオトランクを変更する必要がある場合は、次の Windows PowerShell コマンドレットを使用します。
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    特定のビデオトランク構成に関連する設定を表示するには、次の Windows PowerShell コマンドレットを使用します。
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    特定のビデオトランクの構成を削除するには、次の Windows PowerShell コマンドレットを使用します (特定のトランクに対して明示的に指定されたビデオトランク構成がない場合は、グローバルにスコープ設定されたビデオトランク構成が適用されることに注意してください)。
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 次の Windows PowerShell コマンドレットを使用して、トランクに関連付けるダイヤルプランを確立します。
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

VIS と CUCM との予期される相互作用に干渉することになる既定のルールを上書きするには、**Remove-CsVoiceNormalizationRule** コマンドが必要です。
> [!NOTE]
> [CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)を使用して、ダイヤルプランを削除することができます。
  
要求 URI に E 以外の番号が含まれているビデオゲートウェイからのビデオ通話トランク呼び出しの場合、VIS は、関連付けられたトランクに関連付けられているダイヤルプランの名前を読み取ります。また、そのダイヤルプラン名は、[Invite] の要求 URI の電話コンテキスト部分に含まれます。S では、フロントエンドに送信します。 これによって、フロントエンドの翻訳アプリケーションがそのダイヤル プランに関連付けられている正規化ルールを抽出して要求 URI に適用します。
## <a name="trunk-configuration-options"></a>トランク構成のオプション

前に説明したビデオトランク構成用の Windows PowerShell コマンドレットは、Skype for Business Server 2015 に新しく追加されました。 ビデオトランク構成に関連する設定については、簡単に説明する必要があります。
  
 **GatewaySendsRtcpForActiveCalls**このパラメーターは、RTCP パケットを VTC から VIS に送信するかどうかを指定します。 この場合のアクティブな通話とは、メディアが最低でも一方向に流れることのできる通話のことです。 GatewaySendsRtcpForActiveCalls が True に設定されている場合、VIS は、30秒を超える期間に対して RTCP パケットを受信しない場合、通話を終了できます。 既定値は**True**です。
  
 **Gatewaysendsrtcpforcallsonhold**このパラメーターは、保留になっている通話に対して、RTCP パケットをトランク経由で送信するかどうかを決定します。どの方向にもメディアパケットが流れません。 VIS は、通話が保留中のときに VTC から VIS に流れるパケットがない場合に、通話を終了することができます。 既定値は**True**です。 SIPTransport プロトコルが TCP に設定されている場合、この設定は無視されます。
  
 **EnableMediaEncryptionForSipOverTls**このパラメーターは、SIPTransport プロトコルが TLS に設定されている場合に、メディアの SRTP を有効または無効にします。 既定値は**True**です。 SIPTransport プロトコルが TCP に設定されている場合、この設定は無視されます。
  
 **Enablesessiontimer**このパラメーターは、ビデオ SIP トランクに関連付けられている各 SIP ダイアログの VIS side のセッションタイマーを有効または無効にします。 既定値は**False**です。
  
 **Forwarderror正しく Tiontype**このパラメーターは、ビデオの相互運用サーバーとビデオゲートウェイの間の区間に、ビデオストリームの転送エラー訂正 (FEC) が適用されるかどうかを判断するために使用されます。 ForwardErrorCorrectionType を "None" に設定すると、VIS とビデオゲートウェイ/VTC の間で FEC がオフになります。 ForwarderrorFEC Type を "Cisco" に設定すると、cisco ユニファイドコミュニケーションマネージャー (CUCM) などの Cisco のビデオゲートウェイとの互換性が可能になります。 既定値は **[なし**] です。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server との相互運用用に CUCM を構成する](configure-cucm-for-interoperation.md)
