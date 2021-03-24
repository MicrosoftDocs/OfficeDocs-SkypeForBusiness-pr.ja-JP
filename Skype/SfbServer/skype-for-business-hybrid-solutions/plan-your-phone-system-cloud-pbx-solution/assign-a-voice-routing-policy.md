---
title: 音声ルーティング ポリシーの割り当て
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: '概要: このトピックを参照して、オンプレミス PSTN 接続を使用して電話システムを使用するユーザーに音声ポリシーを割り当てる方法について説明します。'
ms.openlocfilehash: 43e2b560cc0886bacd6faaec6c113ee1f237eff7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092965"
---
# <a name="assign-a-voice-routing-policy"></a>音声ルーティング ポリシーの割り当て
 
> [!Important]
> Skype for Business Online は 2021 年 7 月 31 日に廃止され、その後サービスにアクセスできなくなりました。  さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online を介したオンプレミス環境間の PSTN 接続はサポートされなくなりました。  直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。

**概要:** このトピックでは、オンプレミスの PSTN 接続を使用して電話システムを使用するユーザーに音声ポリシーを割り当てる方法について説明します。 
  
ユーザーが Skype for Business Online に接続し、オンプレミスの PSTN 接続で電話システムを使用すると、2 つの音声ポリシーが適用されます。 1 つは、オンプレミスで割り当てるオンプレミスの音声ルーティング ポリシーです。 このポリシーはグローバルまたはユーザー固有で、ユーザーに関連付けられている PSTN 使用法レコードを定義します。 このトピックでは、このポリシーを割り当てる方法について説明します。
  
他の音声ポリシーでは、ユーザーが使用できる通話機能を定義します。この音声ポリシーは Microsoft によって定義され、オンプレミスの PSTN 接続ユーザーを持つすべての電話システムで同じです。 電話システム のユーザーに自動的に割り当てられます。
  
||**オンプレミス ユーザー**|**オンプレミスの PSTN 接続ユーザーを持つ電話システム**|
|:-----|:-----|:-----|
|で定義された機能の呼び出し  <br/> |音声ポリシー  <br/> |ユーザーが電話システムのライセンスを取得するときに自動的に割り当てられる、定義済みの音声ポリシー。  <br/> |
|関連付けられた PSTN 使用法レコード  <br/> |音声ポリシー  <br/> |ユーザーがまだオンプレミスに存在している間に割り当てられた音声ルーティング ポリシー。  <br/> |
   
ユーザーがオンプレミス展開にまだ存在している間、オンプレミス展開を使用して次の手順を実行します。
  
## <a name="using-a-global-voice-routing-policy"></a>グローバル音声ルーティング ポリシーの使用

オンプレミスの PSTN 接続ユーザーと電話システムのグローバル音声ルーティング ポリシーを使用する前に、PSTN 使用法レコードをポリシーに追加する必要があります。
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>PSTN 使用法レコードをグローバル音声ルーティング ポリシーに割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
3. PSTN 使用法レコードをポリシーに追加します。
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    例:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>新しい音声ルーティング ポリシーの作成

### <a name="to-create-a-new-voice-routing-policy"></a>新しい音声ルーティング ポリシーを作成するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
3. 新しい音声ルーティング ポリシーを作成します。
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    例:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

この例では、HybridVoice という新しい音声ルーティング ポリシーを作成します。これには、2 つの PSTN 使用法が関連付けされています。
  
## <a name="assigning-a-voice-routing-policy"></a>音声ルーティング ポリシーの割り当て

グローバル 音声ルーティング ポリシーまたはユーザー固有の音声ルーティング ポリシーを使用するかどうかに関係なく、次の手順を使用してポリシーをユーザーに割り当てる。
  
### <a name="to-assign-the-voice-routing-policy"></a>音声ルーティング ポリシーを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
3. 既存の音声ポリシーをユーザーに割り当てる:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

この例では、表示名 Bob Kelly を持つユーザーが、HybridVoice という名前の以前に作成した音声ポリシーに割り当てられます。
  
音声ルーティング ポリシーの詳細については、「音声ポリシーを作成または変更し[、Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md) [、New-CsVoiceRoutingPolicy、](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)[および Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)で PSTN 使用法レコードを構成する」を参照してください。
