---
title: ユーザーに発信者番号を設定する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Microsoft 365 および Office 365 の既定の発信者番号 (ユーザーに割り当てられた電話番号) (通話回線 ID とも呼ばれる) について説明します。 ユーザーの発信者番号を変更またはブロックすることができます。
ms.openlocfilehash: 41883e00955cf5f39f4420fb10ead1be2e131a77
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117155"
---
# <a name="set-the-caller-id-for-a-user"></a>ユーザーに発信者番号を設定する
Microsoft 365 および Office 365 の電話システムは、ユーザーに割り当てられた電話番号である既定の発信者番号を提供します。 ユーザーのために発信者番号 (通話回線番号) を変更または禁止することができます。 組織での発信者番号の使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。
  
> [!TIP]
> Skype for Business Online で、着信通話を遮断することは現時点ではできません。 
  
次の設定を変更できます。
  
> [!NOTE]
> これは、Lync または Skype for Business Server を使用するオンプレミスの組織向け **ではありません**
  
- **発信する発信者番号を変更する**: ユーザーの発信者番号は、既定で電話番号になっていますが、別の電話番号に置き換えることができます。たとえば、ユーザーの発信者番号を個人電話番号から会社の代表電話番号に変更したり、ユーザーの通話回線番号を個人電話番号から法務部の代表電話番号に変更したりできます。発信者番号はどのオンライン **サービス** 番号 (有料電話番号または無料電話番号) にでも変更することができます。
    
    > [!NOTE]
    > _Service_ パラメーターを使用する場合は、有効のサービス番号を指定する必要があります。
  
- **発信する発信者番号を禁止する**: ユーザーの発信する PSTN 通話に発信者番号が送信されるのを禁止することができます。このようにすると、呼び出し中の電話に電話番号が表示されるのを禁止することができます。
    
- **着信する発信者番号を禁止する**: あらゆる着信 PSTN 通話でユーザーが発信者番号を受信できないようにします。
    
> [!IMPORTANT]
> 緊急通話では、ユーザーの電話番号 (発信者番号) が常に送信されます。 
  
既定では、これらのすべての発信者番号設定が **オフ** になっています。このため、Skype for Business Online のユーザーが PSTN 電話に通話を発信すると、そのユーザーの電話番号は相手に表示されることになります。
  
これらの設定と使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。
  
## <a name="set-your-caller-id-policy-settings"></a>発信者番号ポリシー設定を設定する

> [!NOTE]
> Skype for Business Online のすべての発信者番号設定では、Windows PowerShell を使用する必要があります。 **Skype for Business 管理センター** を **使用することはできません**。 
  
### <a name="start-powershell"></a>PowerShell を起動する

- コマンド プロンプトWindows PowerShellし、次のコマンドを実行します。

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>組織内のすべての発信者番号のポリシー設定を表示する

- 組織内のすべての発信者番号のポリシー設定を表示するには、次を実行します。

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  [Get-CsCallingLineIdentity](/powershell/module/skype/Get-CsCallingLineIdentity) のその他の例と詳細について確認してください。
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>組織の新しい発信者番号ポリシーを作成します


- 発信者番号を匿名に設定する発信者番号ポリシーを新たに作成するには、次を実行します。
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > すべての場合において、「サービス番号」フィールドに "+" を含めることはできません。

  [New-CsCallingLineIdentity](/powershell/module/skype/New-CsCallingLineIdentity) のその他の例と詳細について確認してください。
    
- Amos Marble に作成した新しいポリシーを適用するには、次を実行します。
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  詳細については、[Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) コマンドレットをご覧ください。
    
既にポリシーを作成している場合は [、Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) コマンドレットを使用して既存のポリシーを変更し [、Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) コマンドレットを使用して設定をユーザーに適用できます。
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>着信する発信者番号を禁止するように設定する

- 着信する発信者番号を禁止するには、次を実行します。
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  [Set-CsCallingLineIdentity](/powershell/module/skype/Set-CsCallingLineIdentity) のその他の例と詳細について確認してください。
    
- 作成したポリシー設定を組織内のユーザーに適用するには、次を実行します。
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    詳細については、[Grant-CsCallingLineIdentity](/powershell/module/skype/Grant-CsCallingLineIdentity) コマンドレットをご覧ください。
    
### <a name="remove-a-caller-id-policy"></a>発信者番号ポリシーを削除する

組織からポリシーを削除するには、次を実行します。
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
ユーザーからポリシーを削除するには、次を実行します。
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 と Skype for Business Online を管理できます。複数のタスクを実行する必要がある場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Microsoft 365 または Windows PowerShell 365 の管理に使用する 6 Office理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShellは、多くのユーザーに対して同時に設定変更を行う場合など、Microsoft 365 管理センターを使用する場合に限って、速度、シンプルさ、生産性の点で多くの利点があります。 次のトピックでこれらの利点について説明します。
    
  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Windows PowerShell による Skype for Business Online の管理](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>関連項目
[電話番号の移行に関するよくある質問](./phone-number-calling-plans/port-order-overview.md)

[通話プランで使用されるさまざまな種類の電話番号](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[組織の電話番号を管理する](/microsoftteams/manage-phone-numbers-for-your-organization)

[発信回線 ID と発信者名の詳細](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[緊急通話の利用条件](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
