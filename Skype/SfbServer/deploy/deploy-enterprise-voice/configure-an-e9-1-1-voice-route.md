---
title: Skype for Business Server で E9 のボイスルートを設定する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Skype for Business Server Enterprise Voice で E9 のボイスルーティングを構成します。
ms.openlocfilehash: c835aa2ab2b20f7877aa6a0deeb70c7459bcd8cc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001397"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>Skype for Business Server で E9 のボイスルートを設定する
 
Skype for Business Server Enterprise Voice で E9 のボイスルーティングを構成します。 
  
E9-1-1 を展開するには、まず緊急通話用のボイス ルートを構成する必要があります。 ボイスルートの作成の詳細については、「 [Skype For business での音声ルートの作成または変更](create-or-modify-a-voice-route.md)」を参照してください。 展開にプライマリ SIP トランクおよびセカンダリ SIP トランクが含まれている場合などは、複数のルートを定義できます。 
  
> [!NOTE]
> E9 の招待状に位置情報を含めるには、E9 サービスプロバイダーに接続する SIP トランクをゲートウェイ経由でルーティングするように構成する必要があります。 そのためには、 **set-cstrunkconfiguration**コマンドレットの EnablePIDFLOSupport フラグを True に設定します。 EnablePIDFLOSupport の既定値は False です。 たとえば`Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` 、フォールバック公衆交換電話網 (PSTN) ゲートウェイおよび緊急対応の場所識別番号 (ELIN) ゲートウェイの受信場所を有効にする必要はありません。
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>E9-1-1 のボイス ルートを構成するには

1. RTCUniversalServerAdmins グループのメンバーまたは CsVoiceAdministrator 管理者役割のメンバーであるアカウントを使用してコンピューターにログオンします。
    
2.  Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 次のコマンドレットを実行して、新しい PSTN 使用法レコードを作成します。 
    
    これは、[場所のポリシー] の [**PSTN**] 設定で使用する名前と同じである必要があります。 展開には複数の電話使用法レコードが含まれますが、次の例では、使用可能な PSTN 使用法の現在の一覧に "Emergency Usage" を追加しています。 詳細については、「 [Skype For business で音声ポリシー、PSTN 使用状況レコード、および音声ルーティングを構成する](voice-and-pstn.md)」を参照してください。
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. 次のコマンドレットを実行して、前のステップで作成した PSTN 使用法レコードで新しいボイス ルートを作成します。
    
    この番号パターンは、[場所のポリシー] の [**緊急ダイヤル文字列**] 設定で使用する番号パターンと同じである必要があります。 Skype for Business は緊急電話に「+」を追加するため、「+」記号が必要です。 "Co1-pstngateway-1" は、E9-1-1 サービス プロバイダーの SIP トランク サービス ID または ELIN ゲートウェイ サービス ID です。 次の例では、ボイス ルートの名前として、"EmergencyRoute" を使用しています。
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. 必要に応じて、SIP トランク接続の場合、E9 サービスプロバイダーの SIP トランクで処理されない通話のローカルルートを作成するには、次のコマンドレットを実行することをお勧めします。 このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。 
    
    次の例では、ユーザーの音声ポリシーに "ローカル" 使用法があることを前提としています。
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


