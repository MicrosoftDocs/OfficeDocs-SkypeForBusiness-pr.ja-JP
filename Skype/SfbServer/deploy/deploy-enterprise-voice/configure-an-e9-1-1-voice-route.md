---
title: E9-1-1 音声ルートを構成Skype for Business Server
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
description: E9-1-1 音声ルートを構成Skype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: a03b93f696d661f989db169bbb1de7cf096c4d9359db1177a25ac2827a424b0f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54287616"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>E9-1-1 音声ルートを構成Skype for Business Server
 
E9-1-1 音声ルートを構成Skype for Business Server エンタープライズ VoIP。 
  
E9-1-1 を展開するには、まず緊急通話用のボイス ルートを構成する必要があります。 音声ルートの作成の詳細については、「[音声](create-or-modify-a-voice-route.md)ルートを作成または変更する」を参照Skype for Business。 展開にプライマリ SIP トランクおよびセカンダリ SIP トランクが含まれている場合などは、複数のルートを定義できます。 
  
> [!NOTE]
> E9-1-1 INVITE に位置情報を含めるには、E9-1-1 サービス プロバイダーに接続する SIP トランクを構成して、ゲートウェイを介して緊急通話をルーティングする必要があります。 これを行うには **、Set-CsTrunkConfiguration** コマンドレットの EnablePIDFLOSupport フラグを True に設定します。 EnablePIDFLOSupport の既定値は False です。 たとえば、代替の公衆交換電話網 (PSTN) ゲートウェイおよび緊急場所識別番号 (ELIN) ゲートウェイの受信場所を有効にする `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` 必要はありません。
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>E9-1-1 のボイス ルートを構成するには

1. RTCUniversalServerAdmins グループのメンバーまたは CsVoiceAdministrator 管理者役割のメンバーであるアカウントを使用してコンピューターにログオンします。
    
2.  管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
3. 次のコマンドレットを実行して、新しい PSTN 使用法レコードを作成します。 
    
    これは、[場所のポリシー] の [**PSTN**] 設定で使用する名前と同じである必要があります。 展開には複数の電話使用法レコードが含まれますが、次の例では、使用可能な PSTN 使用法の現在の一覧に "Emergency Usage" を追加しています。 詳細については、「音声ポリシー [、PSTN 使用法レコード](voice-and-pstn.md)、および音声ルートを構成する」を参照Skype for Business。
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. 次のコマンドレットを実行して、前のステップで作成した PSTN 使用法レコードで新しいボイス ルートを作成します。
    
    この番号パターンは、[場所のポリシー] の[**緊急ダイヤル文字列**] 設定で使用する番号パターンと同じである必要があります。 緊急通話に "+" がSkype for Business"+" 記号が必要です。 "Co1-pstngateway-1" は、E9-1-1 サービス プロバイダーの SIP トランク サービス ID または ELIN ゲートウェイ サービス ID です。 次の例では、ボイス ルートの名前として、"EmergencyRoute" を使用しています。
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. 必要に応じて、SIP トランク接続の場合は、次のコマンドレットを実行して、E9-1-1 サービス プロバイダーの SIP トランクで処理されない呼び出しのローカル ルートを作成することをお勧めします。 このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。 
    
    次の例では、ユーザーの音声ポリシーに "ローカル" 使用法があることを前提としています。
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


