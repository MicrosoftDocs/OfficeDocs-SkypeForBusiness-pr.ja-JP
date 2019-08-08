---
title: Skype for Business Server での作業による通話の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '概要: 一部またはすべてのユーザーに対して、Skype for Business Server で作業を通じて通話を展開する方法について説明します。'
ms.openlocfilehash: d1c55e44cae944664a51eaddb2ad54e758d4f52c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234255"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Skype for Business Server での作業による通話の展開
 
**概要:** 一部またはすべてのユーザーに対して、Skype for Business Server で作業を通じて通話を展開する方法について説明します。
  
次の手順を使用して、ユーザーの勤務先で通話を展開します。 計画の考慮事項については、「 [Skype For Business Server での作業による通話の計画](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)」をご紹介します。 以前のバージョンの Lync Server リモート通話コントロールは、ユーザーが Lync Server を使って PBX 電話を制御できるようにする機能です。 Skype for Business Server では、この機能は勤務先からの通話に置き換えられました。 
  
## <a name="prerequisites-for-call-via-work"></a>勤務先での通話の前提条件

勤務先での通話ユニファイドコミュニケーション Web API (UCWA) は、すべての Skype for Business Server フロントエンドサーバーに自動的にインストールされます。 勤務先のユーザーによる通話を有効にするには、次の前提条件が設定されている必要があります。 
  
- フロントエンドサーバーの一部として、またはスタンドアロンの役割として、仲介サーバーが展開されている必要があります。 また、IP-PBX ゲートウェイの展開も必要です。
    
- 職場経由で通話を有効にするすべてのユーザーは、PBX 電話システムで、直接の内側ダイヤル (DID) を使用する必要があります。 
    
- エンタープライズ Voip の勤務先ユーザーから、すべての通話を有効にする必要があります。 この操作を行う場合、各ユーザーの Skype for Business の電話番号を、対応する PBX 電話システムの対応する DID 番号に設定する必要があります。 
    
- 勤務先で通話を使用するすべてのユーザーは、Skype for Business クライアントの **[Advanced Connections** ] オプションで**自動構成**を選択する必要があります。 これにより、クライアントは UCWA Url を検出できるようになります。 [**自動構成**] は既定で選択されています。
    
- 職場ユーザーからの通話ごとに、着信の転送と同時呼び出しを有効にします。 
    
- 職場ユーザーからの通話ごとに、ダイヤルイン会議と会議のダイヤルアウトが有効になっていることを確認します。 こうすることで、これらのユーザーは Skype for Business 会議にアクセスできます。
    
- すべての通話について、[委任]、[チーム呼び出し]、[応答] グループが [すべて] で無効になっていることを確認します。
    
## <a name="deploy-call-via-work"></a>"勤務先から通話" の展開

前提条件が満たされたら、次の操作を行います。
  
- 展開用のグローバル電話番号を作成します。 Skype for Business では、勤務先から通話を発信しているユーザーの PBX の発信者番号認識が表示されます。 
    
- 勤務先ポリシーを使用して1つ以上の通話を作成する
    
- 勤務先ポリシー経由で通話を有効にする各ユーザーに、職場ポリシー経由で通話を割り当てます。
    
### <a name="create-the-call-via-work-global-phone-number"></a>"勤務先から通話" グローバル電話番号の作成

- 次のコマンドレットを入力します。
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    たとえば、次のコマンドレットではグローバル電話番号が 1-555-123-4567 に設定されます。
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>"勤務先から通話" ポリシーの作成

- 次のコマンドレットを入力します。
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    たとえば、次のコマンドレットでは、ContosoUser1CvWP という勤務ポリシーを使って通話を作成し、管理者のコールバック番号を使用するようにユーザーに要求し、そのコールバック番号を1-555-789-1234 に設定します。
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>勤務ポリシーを使ってユーザーに通話を割り当てる

- 次のコマンドレットを入力します。
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    たとえば、次のコマンドレットは、Work policy "ContosoUser1CvWP" を使って呼び出しを、 **ContosoUser1**という名前のユーザーに割り当てます。
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>関連項目

[Skype for Business Server での勤務先での通話の計画](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

