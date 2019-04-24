---
title: ビジネス サーバー用の Skype で ~ 9-1-1 のボイス ルートを構成します。
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: ビジネス サーバーのエンタープライズ VoIP の Skype で ~ 9-1-1 ボイス ルートを構成します。
ms.openlocfilehash: 04890782eb9c550428d89c99304c5a7951fc34b7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223705"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>ビジネス サーバー用の Skype で ~ 9-1-1 のボイス ルートを構成します。
 
ビジネス サーバーのエンタープライズ VoIP の Skype で ~ 9-1-1 ボイス ルートを構成します。 
  
E9-1-1 を展開するには、まず緊急通話用のボイス ルートを構成する必要があります。 ボイス ルートを作成する方法についてを参照してください[を作成するまたはビジネス用の Skype でのボイス ルートを変更する](create-or-modify-a-voice-route.md)です。 展開にプライマリ SIP トランクおよびセカンダリ SIP トランクが含まれている場合などは、複数のルートを定義できます。 
  
> [!NOTE]
> ~ 9-1-1、招待の場所に関する情報を含む、ゲートウェイを介して、緊急通話のルーティングを ~ 9-1-1 のサービス プロバイダーに接続する SIP トランクを構成する必要があります。 これを行うには、True に**セット CsTrunkConfiguration**コマンドレットに EnablePIDFLOSupport フラグを設定します。 EnablePIDFLOSupport の既定値は、False です。 例:`Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.`フォールバックの公衆は交換電話網 (PSTN) ゲートウェイと緊急位置識別番号 (ELIN) ゲートウェイの受信場所を有効にする必要はありません。
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>E9-1-1 のボイス ルートを構成するには

1. RTCUniversalServerAdmins グループのメンバーまたは CsVoiceAdministrator 管理者役割のメンバーであるアカウントを使用してコンピューターにログオンします。
    
2.  Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 次のコマンドレットを実行して、新しい PSTN 使用法レコードを作成します。 
    
    これは、[場所のポリシー] の [**PSTN**] 設定で使用する名前と同じである必要があります。 展開には複数の電話使用法レコードが含まれますが、次の例では、使用可能な PSTN 使用法の現在の一覧に "Emergency Usage" を追加しています。 詳細については、[音声ポリシーを構成する、PSTN 使用法レコード、およびビジネスのための Skype でのボイス ルート](voice-and-pstn.md)を参照してください。
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. 次のコマンドレットを実行して、前のステップで作成した PSTN 使用法レコードで新しいボイス ルートを作成します。
    
    この番号パターンは、[場所のポリシー] の [**緊急ダイヤル文字列**] 設定で使用する番号パターンと同じである必要があります。 ビジネス用の Skype が追加されるので「+」緊急電話番号には、「+」記号が必要です。 "Co1-pstngateway-1" は、E9-1-1 サービス プロバイダーの SIP トランク サービス ID または ELIN ゲートウェイ サービス ID です。 次の例では、ボイス ルートの名前として、"EmergencyRoute" を使用しています。
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. 必要に応じて、SIP トランク接続では、お勧め ~ 9-1-1 サービス プロバイダーの SIP トランクによって処理されない通話のローカル ルートを作成するのには次のコマンドレットを実行することです。 このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。 
    
    次の例では、ユーザーの音声ポリシーに "ローカル" 使用法があることを前提としています。
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


