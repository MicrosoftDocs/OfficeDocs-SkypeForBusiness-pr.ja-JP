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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: 通話回線 ID Microsoft 365既定Office 365 (ユーザーに割り当てられた電話番号) の呼び出し元 ID と呼ばれる番号について学習します。 ユーザーの発信者番号を変更またはブロックできます。
ms.openlocfilehash: dbbb48952264d82ca24bdd82dbb45538b0428368
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308336"
---
# <a name="set-the-caller-id-for-a-user"></a>ユーザーに発信者番号を設定する

電話システムではMicrosoft 365、ユーザーに割り当てられた電話番号である既定の発信者番号が提供されます。 ユーザーのために発信者番号 (通話回線番号) を変更または禁止することができます。 組織での発信者番号の使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。
  
既定では、次の発信者番号の設定は **オフになっています**。 つまり、ユーザー Teams PSTN 電話に通話を発信すると、そのユーザーの電話番号が表示されます。 これらの設定は次のように変更できます。
  
- **発信元 ID** ユーザーの発信者番号 (既定では電話番号) を別の電話番号に置き換え可能です。 たとえば、ユーザーの発信者番号を個人電話番号から会社の代表電話番号に変更したり、ユーザーの通話回線番号を個人電話番号から法務部の代表電話番号に変更したりできます。 通話 ID 番号は、任意のオンライン サービス番号 (有料または無料) に変更できます。 また、通話 ID 番号をオンプレミスの電話番号に変更するには、自動応答 または通話キューで使用されるリソース アカウントに割り当てられている直接ルーティングを使用します。
    
  > [!NOTE]
  > Service パラメーターを *使用する場合* は、有効なサービス番号を指定する必要があります。
  
- **発信呼び出し元 ID をブロックします。** 発信発信者 ID がユーザーの発信 PSTN 通話で送信されるのをブロックできます。 このようにすると、呼び出し中の電話に電話番号が表示されるのを禁止することができます。
    
- **着信呼び出し元 ID をブロックします。** ユーザーが着信 PSTN 通話で発信者番号を受け取るのをブロックできます。

- **[通話者名 (CNAM) を設定します。** ユーザーはMicrosoft Teams PSTN 通話で CNAM を送信できます。
    
> [!IMPORTANT]
> 緊急通話では、ユーザーの電話番号 (発信者番号) が常に送信されます。 
  

  
これらの設定とそれらの使い方の詳細については、「組織で発信者番号を使用する方法」 [を参照してください](how-can-caller-id-be-used-in-your-organization.md)。
  
## <a name="set-your-caller-id-policy-settings"></a>発信者番号ポリシー設定を設定する

> [!NOTE]
> 呼び出し元 ID をリソース アカウントの電話番号に設定し、発信者名を設定するには、Teams PowerShell モジュール 2.3.1 以降の PowerShell コマンドレット New-CsCallingLineIdentity または Set-CsCallingLineIdentity を使用します。 (これらのオプションは現在、管理センター Microsoft Teams使用できません)。 

コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。

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
   詳細については [、Get-CsCallingLineIdentity に関するページを参照してください](/powershell/module/skype/Get-CsCallingLineIdentity)。
    
2. 組織の新しい発信者番号ポリシーを作成するには、次のコマンドレットNew-CsCallingIdentityします。
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    すべての場合において、「サービス番号」フィールドに "+" を含めることはできません。

   詳細については [、New-CsCallingLineIdentity に関するページを参照してください](/powershell/module/skype/New-CsCallingLineIdentity)。
    
3. 次のコマンドレットを使用して作成した新しいポリシーGrant-CsCallingIdentityします。 たとえば、次の例では、ユーザー Amos Marble に新しいポリシーを適用します。
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   詳細については [、「Grant-CsCallingLineIdentity コマンドレット」を参照](/powershell/module/skype/Grant-CsCallingLineIdentity) してください。
    

4. 着信呼び出し元 ID をブロックする場合は、次を実行します。
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   詳細については [、Set-CsCallingLineIdentity に関するページを参照してください](/powershell/module/skype/Set-CsCallingLineIdentity)。
    
5. 作成したポリシー設定を組織内のユーザーに適用するには、次を実行します。
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   詳細については [、Grant-CsCallingLineIdentity に関するページを参照してください](/powershell/module/skype/Grant-CsCallingLineIdentity)。

6. 新しい発信者番号ポリシーを作成するには、発信者番号を指定されたリソース アカウントの電話番号に設定し、発信者名を Contoso に設定します。

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

既にポリシーを作成している場合は [、Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) コマンドレットを使用して設定をユーザーに適用できます。
    
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

Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365を使用して管理し、毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
- [Windows PowerShell の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [アプリを使用して管理する 6 Windows PowerShell理由Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性に多くの利点があります。 次のトピックでこれらの利点について説明します。
    
- [アプリを使用してMicrosoft 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- [Windows PowerShell による Skype for Business Online の管理](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>関連トピック
[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[発信回線 ID と発信者名の詳細](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
