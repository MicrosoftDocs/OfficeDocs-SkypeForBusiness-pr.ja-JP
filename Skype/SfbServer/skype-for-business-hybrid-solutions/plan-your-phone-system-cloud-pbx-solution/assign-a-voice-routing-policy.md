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
description: '概要: このトピックでは、オンプレミスの PSTN 接続を使用する電話システムを使用するユーザーに音声ポリシーを割り当てる方法について説明します。'
ms.openlocfilehash: 5d56d4f88e30b605276296b35cd9f316348342ca
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359323"
---
# <a name="assign-a-voice-routing-policy"></a>音声ルーティング ポリシーの割り当て
 
> [!Important]
> Skype for Business Online は、2021年7月31日に廃止されます。その後、サービスにアクセスできなくなります。  さらに、Skype for Business Server または Cloud Connector Edition と Skype for Business Online のどちらを使用しても、オンプレミス環境との間の PSTN 接続がサポートされなくなります。  [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを Teams に接続する方法について説明します。

**概要:** このトピックでは、オンプレミスの PSTN 接続を備えた電話システムを使用するユーザーに音声ポリシーを割り当てる方法について説明します。 
  
ユーザーが Skype for Business Online を使用していて、オンプレミスの PSTN 接続を備えた電話システムを使用すると、2つの音声ポリシーが適用されます。 1つはオンプレミスで割り当てられる社内音声ルーティングポリシーです。 このポリシーは、グローバルまたはユーザー固有のものであり、ユーザーに関連付けられている PSTN 使用法レコードを定義します。 このトピックでは、このポリシーを割り当てる方法について説明します。
  
その他の音声ポリシーでは、ユーザーが使用できる通話機能を定義します。この音声ポリシーは、Microsoft によって定義されており、オンプレミスの PSTN 接続ユーザーを含むすべての電話システムで同一です。 これは、電話システムのユーザーに自動的に割り当てられます。
  
||**オンプレミスのユーザー**|**オンプレミスの PSTN 接続ユーザーが搭載された電話システム**|
|:-----|:-----|:-----|
|で定義されている通話機能  <br/> |音声ポリシー  <br/> |事前に定義された音声ポリシー。ユーザーが電話システムのライセンスを受けたときに自動的に割り当てられます。  <br/> |
|に関連付けられている PSTN 使用法レコード  <br/> |音声ポリシー  <br/> |音声ルーティングポリシー。ユーザーがまだオンプレミスに所属している間に割り当てられます。  <br/> |
   
次の手順は、オンプレミス展開を使用して実行しますが、ユーザーは引き続き社内展開に所属しています。
  
## <a name="using-a-global-voice-routing-policy"></a>グローバル音声ルーティングポリシーを使用する

オンプレミスの PSTN 接続ユーザーを使用して電話システムにグローバル音声ルーティングポリシーを使用する前に、PSTN 使用法レコードをポリシーに追加する必要があります。
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>PSTN 使用法レコードをグローバル音声ルーティングポリシーに割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを起動します。 [ **スタート**]、[ **すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。
    
3. PSTN 使用法レコードをポリシーに追加します。
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    例:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>新しい音声ルーティングポリシーの作成

### <a name="to-create-a-new-voice-routing-policy"></a>新しい音声ルーティングポリシーを作成するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを起動します。 [ **スタート**]、[ **すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。
    
3. 新しい音声ルーティングポリシーを作成します。
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    例:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

この例では、HybridVoice という名前の新しい音声ルーティングポリシーを作成します。これには、2つの PSTN 使用法が関連付けられています。
  
## <a name="assigning-a-voice-routing-policy"></a>音声ルーティングポリシーの割り当て

グローバル音声ルーティングポリシーまたはユーザー固有のポリシーのどちらを使用するかに関係なく、次の手順を使用して、ポリシーをユーザーに割り当てます。
  
### <a name="to-assign-the-voice-routing-policy"></a>音声ルーティングポリシーを割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを起動します。 [ **スタート**]、[ **すべてのプログラム**]、[ **skype for business 2015**] の順にクリックし、[ **skype for business server 管理シェル**] をクリックします。
    
3. 既存の音声ポリシーをユーザーに割り当てる:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

この例では、Bob 友野という表示名を持つユーザーが、HybridVoice という名前で以前に作成した音声ポリシーに割り当てられます。
  
音声ルーティングポリシーの詳細については、「 [Create or modify a voice policy」および「CONFIGURE PSTN usage records In Skype For business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)」、「 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)」、および「 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)」を参照してください。
  

