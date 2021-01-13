---
title: Skype for Business Server での [作業から通話] の展開
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '概要: 一部またはすべてのユーザーに対して Skype for Business Server で [通話から作業] を展開する方法について学習します。'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825007"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Skype for Business Server での [作業から通話] の展開
 
**概要:** 一部またはすべてのユーザーに対して Skype for Business Server で [通話から作業] を展開する方法について学習します。
  
以下の手順を使用して、ユーザーに [通話の実行] を展開します。 計画に関する考慮事項については [、「Plan for Call Via Work in Skype for Business Server」を参照してください](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)。 以前のバージョンの Lync Server のリモート通話コントロールは、ユーザーが Lync Server を使用して PBX 電話を制御できる機能でした。 Skype for Business Server では、この機能は [Call Via Work] に置き換えられた機能です。 
  
## <a name="prerequisites-for-call-via-work"></a>[仕事から通話] の前提条件

Call Via Work は、すべての Skype for Business Server フロントエンド サーバーに自動的にインストールされる Unified Communications Web API (UCWA) を使用します。 ユーザーが [仕事から通話] を有効にするには、次の前提条件も満たされている必要があります。 
  
- フロントエンド サーバーの一部として、またはスタンドアロンの役割として、仲介サーバーを展開する必要があります。 IP-PBX ゲートウェイも展開する必要があります。
    
- [仕事から通話] が有効になるすべてのユーザーは、PBX 電話システムに Direct Inward Dialing (DID) が必要です。 
    
- すべての [通話の実行] を有効にする必要エンタープライズ VoIP。 これを行う場合は、各ユーザーの Skype for Business DID 番号を、対応する PBX 電話システムの対応する DID 番号に構成する必要があります。 
    
- [仕事から通話] を使用するユーザーはすべて、Skype for Businessクライアントの [詳細設定接続] オプションで [自動構成] を選択する必要があります。 これにより、クライアントは UCWA URL を検出できます。 **自動構成は** 既定の選択です。
    
- [Call Via Work] ユーザーごとに、通話の転送と同時呼び出しを有効にします。 
    
- [Call Via Work] ユーザーごとに、ダイヤルイン会議と会議ダイヤルアウトが有効になっている必要があります。 これにより、これらのユーザーは Skype for Business 会議に参加および会議から抜け出すできます。
    
- すべての [Call Via Work] ユーザーに対して、委任、チーム通話、および応答グループが無効に設定されている必要があります。
    
## <a name="deploy-call-via-work"></a>勤務先から通話の展開

前提条件が満たされた後、次の手順を実行します。
  
- 展開用のグローバル電話番号を作成します。Skype for Business は、通話を行っているユーザーの PBX 発信者番号に表示されます。 
    
- 1 つ以上の [仕事から通話] ポリシーを作成する
    
- [仕事から通話] ポリシーを、[仕事から通話] が有効になる各ユーザーに割り当てる
    
### <a name="create-the-call-via-work-global-phone-number"></a>[Call Via Work] グローバル電話番号を作成する

- 次のコマンドレットを入力します。
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    たとえば、次のコマンドレットは、グローバル電話番号を 1-555-123-4567 に設定します。
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>[仕事から通話] ポリシーを作成する

- 次のコマンドレットを入力します。
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    たとえば、次のコマンドレットでは、ContosoUser1CvWP という Call Via Work ポリシーを作成し、ユーザーに管理者コールバック番号の使用を要求し、そのコールバック番号を 1-555-789-1234 に設定します。
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>[仕事から通話] ポリシーをユーザーに割り当てる

- 次のコマンドレットを入力します。
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    たとえば、次のコマンドレットは、"ContosoUser1CvWP" という Call Via Work ポリシーを ContosoUser1 という名前のユーザーに割り **当てるとします**。
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>関連項目

[Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

