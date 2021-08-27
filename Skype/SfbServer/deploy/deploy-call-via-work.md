---
title: '[作業を介して通話を展開する] Skype for Business Server'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '概要: ユーザーの一部またはすべてのユーザーに対して、Skype for Business Serverを展開する方法について学習します。'
ms.openlocfilehash: c6113c4447e30d59a262bf2c02b3f7ff2db171f2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624419"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>[作業を介して通話を展開する] Skype for Business Server
 
**概要:** 一部またはすべてのユーザーに対して、Skype for Business Serverを展開する方法について学習します。
  
次の手順を使用して、ユーザーの [作業による通話] を展開します。 計画に関する考慮事項については、「プラン[for Call Via Work in Skype for Business Server.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md) 以前のバージョンの Lync Server リモート呼び出し制御は、ユーザーが Lync Server で PBX 電話を制御できる機能でした。 このSkype for Business Serverは、Call Via Work に置き換えされています。 
  
## <a name="prerequisites-for-call-via-work"></a>仕事による通話の前提条件

Call Via Work では、すべてのフロントエンド サーバーに自動的にインストールされるユニファイド コミュニケーション Web API (UCWA) Skype for Business Server使用します。 ユーザーが [仕事を経由して通話] を有効にするには、次の前提条件も満たす必要があります。 
  
- 仲介サーバーは、フロント エンド サーバーの一部として、またはスタンドアロンの役割として展開されている必要があります。 IP-PBX ゲートウェイも展開する必要があります。
    
- 仕事による通話が有効になるすべてのユーザーは、PBX 電話システムに直接インワード ダイヤル (DID) を持っている必要があります。 
    
- すべての [作業時間を使用して通話] ユーザーを有効にする必要エンタープライズ VoIP。 これを行う場合は、各ユーザー Skype for Business DID 番号を対応する PBX 電話システムの対応する DID 番号に構成する必要があります。 
    
- Call Via Work を使用するすべてのユーザーは、クライアントの [高度な接続] オプションで [自動構成] を選択Skype for Business必要があります。 これにより、クライアントは UCWA URL を検出できます。 **自動構成は** 既定の選択です。
    
- 各通話 Via Work ユーザーに対して、通話転送と同時呼び出しを有効にします。 
    
- [作業時間による通話] ユーザーごとに、ダイヤルイン会議と会議のダイヤルアウトが有効になっているか確認します。 これにより、これらのユーザーは会議に参加し、Skype for Businessできます。
    
- すべての Call Via Work ユーザーに対して委任、チーム通話、および応答グループが無効になっているか確認します。
    
## <a name="deploy-call-via-work"></a>勤務先から通話の展開

前提条件が満たされた後、次の操作を行います。
  
- 展開のグローバル電話番号を作成しSkype for Business通話を行うユーザーの PBX 発信者 ID に表示されます。 
    
- 1 つ以上の通話経由の作業ポリシーを作成する
    
- [作業時間による通話] ポリシーを、作業時間による通話を有効にする各ユーザーに割り当てる
    
### <a name="create-the-call-via-work-global-phone-number"></a>[作業時間による通話] グローバル電話番号の作成

- 次のコマンドレットを入力します。
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    たとえば、次のコマンドレットはグローバル電話番号を 1-555-123-4567 に設定します。
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>作業時間による呼び出しポリシーの作成

- 次のコマンドレットを入力します。
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    たとえば、次のコマンドレットは ContosoUser1CvWP という Call Via Work ポリシーを作成し、ユーザーに管理者コールバック番号を使用する必要があります。そのコールバック番号を 1-555-789-1234 に設定します。
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>[作業時間による通話] ポリシーをユーザーに割り当てる

- 次のコマンドレットを入力します。
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    たとえば、次のコマンドレットは、仕事の呼び出しポリシー "ContosoUser1CvWP" を ContosoUser1 という名前のユーザー **に割り当てします**。
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>関連項目

[[通話の計画] 作業時間内の作業Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

