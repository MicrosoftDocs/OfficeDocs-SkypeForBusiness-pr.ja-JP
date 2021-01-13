---
title: Skype for Business Server で E9-1-1 ボイス ルートを構成する
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Skype for Business Server 2013 で E9-1-1 ボイス ルートを構成エンタープライズ VoIP。
ms.openlocfilehash: b5f3d12bb586a65fc1c553a021c1a27efb0c7f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804177"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Skype for Business Server で E9-1-1 ボイス ルートを構成する
 
Skype for Business Server サービスで E9-1-1 ボイス ルートを構成エンタープライズ VoIP。 
  
E9-1-1 を展開するには、まず緊急通話用のボイス ルートを構成する必要があります。 ボイス ルートの作成の詳細については、「Skype for Business でボイス ルートを作成または変更する」 [を参照してください](create-or-modify-a-voice-route.md)。 展開にプライマリ SIP トランクおよびセカンダリ SIP トランクが含まれている場合などは、複数のルートを定義できます。 
  
> [!NOTE]
> E9-1-1 INVITE に場所情報を含めるには、E9-1-1 サービス プロバイダーに接続する SIP トランクを構成して、ゲートウェイ経由で緊急通話をルーティングする必要があります。 これを行うには **、Set-CsTrunkConfiguration** コマンドレットの EnablePIDFLOSupport フラグを True に設定します。 EnablePIDFLOSupport の既定値は False です。 たとえば、フォールバック公衆交換電話網 (PSTN) ゲートウェイおよび緊急位置識別番号 (ELIN) ゲートウェイの受信場所を有効にする `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` 必要はありません。
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>E9-1-1 のボイス ルートを構成するには

1. RTCUniversalServerAdmins グループのメンバーまたは CsVoiceAdministrator 管理者役割のメンバーであるアカウントを使用してコンピューターにログオンします。
    
2.  Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。
    
3. 次のコマンドレットを実行して、新しい PSTN 使用法レコードを作成します。 
    
    これは、[場所のポリシー] の [**PSTN**] 設定で使用する名前と同じである必要があります。 展開には複数の電話使用法レコードが含まれますが、次の例では、使用可能な PSTN 使用法の現在の一覧に "Emergency Usage" を追加しています。 詳細については [、「Skype for Business での音声ポリシー、PSTN 使用法レコード、およびボイス ルートの構成」を参照してください](voice-and-pstn.md)。
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. 次のコマンドレットを実行して、前のステップで作成した PSTN 使用法レコードで新しいボイス ルートを作成します。
    
    この番号パターンは、[場所のポリシー] の[**緊急ダイヤル文字列**] 設定で使用する番号パターンと同じである必要があります。 Skype for Business が緊急電話に "+" を追加するために、"+" 記号が必要です。 "Co1-pstngateway-1" は、E9-1-1 サービス プロバイダーの SIP トランク サービス ID または ELIN ゲートウェイ サービス ID です。 次の例では、ボイス ルートの名前として、"EmergencyRoute" を使用しています。
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. 必要に応じて、SIP トランク接続の場合は、次のコマンドレットを実行して、E9-1-1 サービス プロバイダーの SIP トランクで処理されない通話のローカル ルートを作成することをお勧めします。 このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。 
    
    次の例では、ユーザーの音声ポリシーに "ローカル" 使用法があることを前提としています。
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


