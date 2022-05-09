---
title: ユーザーに発信者番号を設定する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 既定の発信者番号 (ユーザーの割り当てられた電話番号) Microsoft 365とOffice 365について説明します。通話回線 ID とも呼ばれます。 ユーザーの発信者番号を変更またはブロックできます。
ms.openlocfilehash: 9a69cf864cbf57d7ebf82ae079f88a888d3fc9f0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613586"
---
# <a name="set-the-caller-id-for-a-user"></a>ユーザーに発信者番号を設定する

Microsoft 365の電話システムは、ユーザーの割り当てられた電話番号である既定の発信者番号を提供します。 ユーザーのために発信者番号 (通話回線番号) を変更または禁止することができます。 組織での発信者番号の使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。
  
既定では、次の呼び出し元 ID 設定は **オフになっています**。 つまり、Teams ユーザーの電話番号は、そのユーザーが PSTN 電話を呼び出したときに表示されます。 これらの設定は次のように変更できます。
  
- **発信呼び出し元 ID** ユーザーの発信者番号 (既定では電話番号) を別の電話番号に置き換えることができます。 たとえば、ユーザーの発信者番号を自分の電話番号から会社の主要な電話番号に変更したり、法務部門のメイン電話番号に変更したりできます。 また、通話 ID 番号は、自動応答または通話キューで使用されるリソース アカウントに割り当てられたダイレクト ルーティングを使用して、任意のオンライン サービス番号 (有料または無料) またはオンプレミスの電話番号に設定できます。
    
  > [!NOTE]
  > *Service* パラメーターを使用する場合は、有効なサービス番号を指定する必要があります。
  > リソース アカウント番号がドロップダウンに表示されない場合は、powerShell モジュール 2.3.1 以降で PowerShell コマンドレット TeamsNew-CsCallingLineIdentityまたはSet-CsCallingLineIdentityを使用する必要があります。
  
- **発信呼び出し元 ID をブロックします。** 発信発信者番号がユーザーの発信 PSTN 通話で送信されないようにブロックできます。 このようにすると、呼び出し中の電話に電話番号が表示されるのを禁止することができます。
    
- **着信呼び出し元 ID をブロックします。** ユーザーが着信 PSTN 通話で発信者番号を受信できないようにブロックできます。

- **呼び出し元の名前 (CNAM) を設定します。** Microsoft Teams ユーザーの場合は、発信 PSTN 通話で CNAM を送信できます。
    
> [!IMPORTANT]
> 緊急通話では、ユーザーの電話番号 (発信者番号) が常に送信されます。 
  

  
これらの設定とその使用方法の詳細については、「 [組織内で発信者番号を使用する方法](how-can-caller-id-be-used-in-your-organization.md)」を参照してください。
  
## <a name="set-your-caller-id-policy-settings"></a>発信者番号ポリシー設定を設定する

> [!NOTE]
> 呼び出し元 ID をリソース アカウントの電話番号に設定し、発信側の名前を設定するには、Teams PowerShell モジュール 2.3.1 以降の PowerShell コマンドレットNew-CsCallingLineIdentityまたはSet-CsCallingLineIdentityを使用します。 (これらのオプションは現在、Microsoft Teams管理センターでは使用できません。 

Windows PowerShellコマンド プロンプトを開き、次のコマンドを実行します。

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a>ポリシー設定を表示、作成、適用する

1. 組織内のすべての発信者番号のポリシー設定を表示するには、次を実行します。

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   詳細については、「 [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity)」を参照してください。
    
2. 組織の新しい発信者番号ポリシーを作成するには、New-CsCallingIdentity コマンドレットを使用します。
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    すべての場合において、「サービス番号」フィールドに "+" を含めることはできません。

   詳細については、「 [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity)」を参照してください。
    
3. Grant-CsCallingIdentity コマンドレットを使用して作成した新しいポリシーを適用します。 たとえば、次の例では、ユーザー Amos Marble に新しいポリシーを適用します。
    
     ```PowerShell
     Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   詳細については、「 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) コマンドレット」を参照してください。
    

4. 着信呼び出し元 ID をブロックする場合は、次を実行します。
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   詳細については、「 [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity)」を参照してください。
    
5. 作成したポリシー設定を組織内のユーザーに適用するには、次を実行します。
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   詳細については、「 [Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity)」を参照してください。

6. 発信者番号を指定したリソース アカウントの電話番号に設定し、発信者名を Contoso に設定する新しい発信者番号ポリシーを作成するには、

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

ポリシーを既に作成している場合は、 [Set-CsCallingLineIdentity コマンドレットを](/powershell/module/skype/Set-CsCallingLineIdentity) 使用して既存のポリシーを変更し、 [Grant-CsCallingLineIdentity コマンドレットを](/powershell/module/skype/Grant-CsCallingLineIdentity) 使用して設定をユーザーに適用できます。
    
### <a name="remove-a-policy-setting"></a>ポリシー設定を削除する

組織からポリシーを削除するには、次を実行します。
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
ユーザーからポリシーを削除するには、次を実行します。
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShellはすべて、ユーザーの管理と、ユーザーの許可または許可されていない操作です。 Windows PowerShellを使用すると、毎日の作業を簡略化できる単一の管理ポイントを使用して、Microsoft 365を管理できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
- [Windows PowerShellの概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Windows PowerShellを使用してMicrosoft 365を管理する 6 つの理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShellには、多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターのみを使用するよりも、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。
    
- [Windows PowerShellを使用してMicrosoft 365を管理する最適な方法](/previous-versions//dn568025(v=technet.10))
    
- [Windows PowerShell による Skype for Business Online の管理](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>関連項目
[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[発信回線 ID と発信者名の詳細](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
