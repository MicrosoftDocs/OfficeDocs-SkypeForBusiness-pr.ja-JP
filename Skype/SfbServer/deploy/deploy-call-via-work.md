---
title: Skype for Business Server 2015 での "勤務先から通話" の展開
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '概要: は、ユーザーの一部またはすべてのビジネス サーバー 2015 の Skype の呼び出しを使用して作業を配置する方法を説明します。'
ms.openlocfilehash: e101cf39daedb8d94879b6cf99cd0c7b4ae00e8d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-via-work-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での "勤務先から通話" の展開
 
**の概要:** ビジネス サーバー 2015 の一部またはすべてのユーザーの Skype の呼び出しを使用して作業を配置する方法について説明します。
  
ユーザーの作業を使用して呼び出しを配置するのにには、次の手順を使用します。 [ビジネス サーバー 2015 の Skype の呼び出しを使用して作業を計画](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)の計画に関する考慮事項が説明します。 Lync Server のリモート呼び出しの以前のバージョンでは、コントロールは、Lync Server は PBX 電話を制御するユーザーを有効にする機能でした。 ビジネス サーバーの Skype は、この機能は作業時間を使用して呼び出しを交換済み。 
  
## <a name="prerequisites-for-call-via-work"></a>作業を使用して呼び出すのための前提条件

作業による呼び出しは、ユニファイド コミュニケーション Web API (UCWA)、ビジネス サーバーのフロント エンド サーバーのすべての Skype で自動的にインストールされるを使用します。 作業による呼び出しでユーザーを有効にするのにも必要次の前提条件の場所でです。 
  
- サーバーをフロント エンド サーバーの一部として、またはスタンドアロンの役割として展開するには、仲介サーバーが必要です。 また、IP-PBX ゲートウェイの展開も必要です。
    
- 作業を使用して呼び出しを有効化するすべてのユーザーには、PBX 電話システムに直接内側ダイヤル (DID) 必要があります。 
    
- エンタープライズ VoIP のすべての作業の呼び出しを使用してユーザーを有効にする必要があります。 これを行うと、対応する PBX 電話システムの対応する DID 番号を各ユーザーの数のビジネスでしたの Skype を構成しなければなりません。 
    
- 作業を使用して呼び出しを使用するすべてのユーザーには、ビジネス クライアント用の Skype では、その**接続の高度な**オプションで選択されている**自動構成**が必要です。 これにより、クライアントが UCWA の Url を検出します。 [**自動構成**] は既定で選択されています。
    
- 作業の呼び出しを使用してユーザーごとに、着信の転送および同時呼び出しを有効にします。 
    
- 作業の呼び出しを使用して、ユーザーごとにダイヤルイン会議および会議のダイヤル ・ アウトが有効になっていることを確認します。 これにより、これらのユーザーにビジネス会議のために、Skype を取得します。
    
- 作業を使用して呼び出しのすべてのユーザーの委任、チーム呼び出し、および応答グループが無効になっていることを確認します。
    
## <a name="deploy-call-via-work"></a>"勤務先から通話" の展開

前提条件が満たされたら、次の操作を行います。
  
- ビジネス用の Skype を作業の呼び出しを使用して呼び出しを行うユーザーの PBX の呼び出し元 ID の表示を展開するためのグローバル電話番号を作成します。 
    
- 1 つまたは複数の作業の呼び出しを使用してポリシーを作成します。
    
- 作業を使用して呼び出しを有効化する各ユーザーに作業を使用して呼び出すポリシーを割り当てる
    
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
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber
    <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

  ```

    などの次のコマンドレット ContosoUser1CvWP と呼ばれる作業の呼び出しを使用してポリシーを作成、管理のコールバック番号を使用するユーザーが必要で、コールバック番号を 1-555-789-1234 に設定。
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>作業の呼び出しを使用してポリシーをユーザーに割り当てる

- 次のコマンドレットを入力します。
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    たとえば、次のコマンドレットでは、 **ContosoUser1**をという名前のユーザーに作業の呼び出しを使用してポリシーの"ContosoUser1CvWP"が割り当てられます。
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>関連項目

#### 

[Skype ビジネス サーバー 2015 の作業時間を使用して呼び出すのための計画](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

