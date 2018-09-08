---
title: 音声ルーティング ポリシーの割り当て
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: '概要: Office 365 の電話システムを使用して設置した PSTN 接続を持つユーザーの音声ポリシーを割り当てる方法の詳細については、このトピックを読み取り。'
ms.openlocfilehash: 6acc7188cbb76c101890591a822ac03a686a8246
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886063"
---
# <a name="assign-a-voice-routing-policy"></a>音声ルーティング ポリシーの割り当て
 
**の概要:** Office 365 の電話システムを使用して設置した PSTN 接続を持つユーザーの音声ポリシーを割り当てる方法の詳細については、このトピックを参照してください。 
  
ユーザーは、ビジネス オンラインで設置した PSTN 接続を Office 365 に電話システムを使用するの Skype では後に、2 つのボイス ポリシーが適用されます。 設置型に割り当てる設置型音声ルーティング ポリシーは 1 つです。 このポリシーでは、グローバル、またはユーザー固有にすることができ、どのような PSTN 使用法レコードがユーザーに関連付けを定義します。 このトピックではこのポリシーを割り当てる方法について説明します。
  
ユーザーにどのような呼び出し元の機能を利用、その他の音声ポリシーを定義します。この音声ポリシーは、Microsoft によって定義され、設置の PSTN 接続のユーザーと Office 365 の電話システムのすべてのと同じです。 Office 365 ユーザーの電話システムに自動的に割り当てられます。
  
||**オンプレミス ユーザー**|**設置 PSTN 接続のユーザーと Office 365 の電話システム**|
|:-----|:-----|:-----|
|定義される通話機能  <br/> |音声ポリシー  <br/> |定義済みのボイス ポリシー、ユーザーが Office 365 の電話システムのライセンスを取得すると自動的に割り当てられます。  <br/> |
|関連付けられる PSTN 使用レコード  <br/> |音声ポリシー  <br/> |音声ルーティングポリシー。ユーザーがまだオンプレミスに所属している間に割り当てられます。  <br/> |
   
設置型展開で、ユーザーのホームでも、設置型の展開を使用して次の手順を実行するとします。
  
## <a name="using-a-global-voice-routing-policy"></a>グローバル音声ルーティング ポリシーの使用

設置 PSTN 接続のユーザーと Office 365 の電話システムのグローバルの音声ルーティング ポリシーを使用して、前に、PSTN 使用法レコードをポリシーに追加する必要があります。
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>PSTN 使用レコードをグローバル音声ルーティング ポリシーに割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. PSTN 使用法レコードは、ポリシーに追加します。
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
  ```

    例:
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
  ```

## <a name="creating-a-new-voice-routing-policy"></a>新しい音声ルーティング ポリシーを作成する

### <a name="to-create-a-new-voice-routing-policy"></a>新しい音声ルーティング ポリシーを作成するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 新しい音声ルーティング ポリシーを作成します。
    
  ```
  New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
  ```

    例:
    
  ```
  New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
  ```

この例では、HybridVoice という新しい音声ルーティング ポリシーを作成します。このポリシーには 2 つの PSTN 使用レコードが関連付けられています。
  
## <a name="assigning-a-voice-routing-policy"></a>音声ルーティング ポリシーを割り当てる

グローバル音声ルーティング ポリシーまたはユーザー固有のポリシーのどちらを使用する場合でも、次の手順を使用してポリシーをユーザーに割り当てます。
  
### <a name="to-assign-the-voice-routing-policy"></a>音声ルーティング ポリシーを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 既存の音声ポリシーをユーザーに割り当てます。
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
  ```

    例:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
  ```

次の例では、表示名 Bob Kelly のユーザーを、以前に作成した HybridVoice という名前の音声ポリシーに割り当てます。
  
音声ルーティング ポリシーの詳細についてを参照してください[を作成する音声ポリシーを変更してビジネス 2015年の Skype の PSTN 使用法レコードを構成する](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)、[新しい CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)、および[許可-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)です。
  

