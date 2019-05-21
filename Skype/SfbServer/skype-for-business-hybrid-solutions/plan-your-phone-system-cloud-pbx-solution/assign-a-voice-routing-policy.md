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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: '概要: このトピックでは、Office 365 で電話システムを使用して、オンプレミスの PSTN 接続を使用して、ユーザーに対して音声ポリシーを割り当てる方法について説明します。'
ms.openlocfilehash: 0d310378b77c09b427836f0d9bceb60a14982071
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294433"
---
# <a name="assign-a-voice-routing-policy"></a>音声ルーティング ポリシーの割り当て
 
**概要:** このトピックでは、Office 365 の電話システムを使って、オンプレミスの PSTN 接続を使用して、ユーザーに対して音声ポリシーを割り当てる方法について説明します。 
  
ユーザーが Skype for Business Online を使用していて、Office 365 の電話システムをオンプレミスの PSTN 接続と共に使用すると、2つの音声ポリシーが適用されます。 1つはオンプレミスのボイスルーティングポリシーであり、オンプレミスで割り当てることができます。 このポリシーはグローバルまたはユーザー固有のものにすることができ、ユーザーに関連付けられている PSTN 使用状況レコードを定義できます。 このトピックではこのポリシーを割り当てる方法について説明します。
  
その他の音声ポリシーでは、ユーザーが使用できる通話機能を定義します。この音声ポリシーは、Microsoft によって定義され、Office 365 のすべての電話システムで、オンプレミスの PSTN 接続ユーザーとまったく同じです。 Office 365 ユーザーの電話システムに自動的に割り当てられます。
  
||**オンプレミス ユーザー**|**オンプレミスの PSTN 接続ユーザーとの Office 365 の電話システム**|
|:-----|:-----|:-----|
|定義される通話機能  <br/> |音声ポリシー  <br/> |事前に定義された音声ポリシー。ユーザーが Office 365 で電話システムのライセンスを取得したときに自動的に割り当てられます。  <br/> |
|関連付けられる PSTN 使用レコード  <br/> |音声ポリシー  <br/> |音声ルーティングポリシー。ユーザーがまだオンプレミスに所属している間に割り当てられます。  <br/> |
   
次の手順は、オンプレミスの展開を使用して実行しますが、ユーザーはオンプレミスの展開のままになっています。
  
## <a name="using-a-global-voice-routing-policy"></a>グローバル音声ルーティング ポリシーの使用

Office 365 で電話システムのグローバルボイスルーティングポリシーをオンプレミスの PSTN 接続ユーザーと共に使用する前に、PSTN 使用状況レコードをポリシーに追加する必要があります。
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>PSTN 使用レコードをグローバル音声ルーティング ポリシーに割り当てるには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. PSTN 使用状況レコードをポリシーに追加します。
    
   ```
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    次に例を示します。
    
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

    次に例を示します。
    
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
  
音声ルーティングポリシーの詳細については、「Skype for Business 2015、[新規-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)、および[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)[での音声ポリシーの作成と変更」および「PSTN 使用状況レコードの構成](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)」を参照してください。
  

