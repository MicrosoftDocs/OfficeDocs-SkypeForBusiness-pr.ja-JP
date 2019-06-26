---
title: ユーザーに発信者番号を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Office 365 の電話システムは、ユーザーの割り当てられた電話番号である既定の発信者番号を提供します。ユーザーのために発信者番号 (通話回線番号) を変更または禁止することができます。組織での発信者番号の使用方法の詳細については、組織内での発信者番号の使用方法をご覧ください。
ms.openlocfilehash: 41fe8775ae98828a5c242c21a910906f8f4699eb
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221380"
---
# <a name="set-the-caller-id-for-a-user"></a>ユーザーに発信者番号を設定する
[] Office 365 の電話システムは、ユーザーの割り当てられた電話番号である既定の発信者番号を提供します。ユーザーのために発信者番号 (通話回線番号) を変更または禁止することができます。組織での発信者番号の使用方法の詳細については、[組織内での発信者番号の使用方法](how-can-caller-id-be-used-in-your-organization.md)をご覧ください。
  
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
  
### <a name="verify-and-start-windows-powershell"></a>Windows PowerShell を検証および開始する

- **Windows PowerShell バージョン 3.0 以降を実行していることを確認する**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. [ _Windows PowerShell_] ウィンドウに「 **Get-Host**」と入力して、バージョンを確認します。
    
3. バージョン 3.0 以降を使用していない場合は、Windows PowerShell の更新プログラムをダウンロードおよびインストールする必要があります。 Windows PowerShell をバージョン4.0 にダウンロードして更新するには、「 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 」を参照してください。 メッセージが表示されたら、コンピューターを再起動します。
    
4. Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できるように、Skype for Business Online の Windows PowerShell モジュールもインストールする必要があります。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。メッセージが表示されたら、コンピューターを再起動します。
    
    詳細については、「[単一の Windows PowerShell ウィンドウですべての Office 365 サービスに接続する](https://technet.microsoft.com/EN-US/library/dn568015.aspx)」を参照してください。
    
- **Windows PowerShell セッションを開始する**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. [ **Windows PowerShell**] ウィンドウで、次を実行して、Office 365 の組織に接続します。
    
   > [!NOTE]
   > Skype for Business Online Windows PowerShell モジュールを初めて使用するときに、 **Import-Module** コマンドを実行するだけです。
   > 
   ```
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

Windows PowerShell の起動の詳細については、「[単一の Windows powershell ウィンドウですべての Office 365 サービスに接続](https://technet.microsoft.com/EN-US/library/dn568015.aspx)する」または「 [windows powershell 用のコンピューターをセットアップ](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)する」を参照してください。
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>組織内のすべての発信者番号のポリシー設定を表示する

- 組織内のすべての発信者番号のポリシー設定を表示するには、次を実行します。

  ```
  Get-CsCallingLineIdentity |fl
  ```
  [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx) のその他の例と詳細について確認してください。
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>組織の新しい発信者番号ポリシーを作成します


- 発信者番号を匿名に設定する発信者番号ポリシーを新たに作成するには、次を実行します。
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > すべての場合において、「サービス番号」フィールドに "+" を含めることはできません。

  [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx) のその他の例と詳細について確認してください。
    
- Amos Marble に作成した新しいポリシーを適用するには、次を実行します。
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  詳細については、[Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) コマンドレットをご覧ください。
    
既にポリシーを作成済みの場合は、 [CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)コマンドレットを使用して既存のポリシーに変更を加えることができます。次に、 [CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)コマンドレットを使用して、ユーザーに設定を適用します。
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>着信する発信者番号を禁止するように設定する

- 着信する発信者番号を禁止するには、次を実行します。
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) のその他の例と詳細について確認してください。
    
- 作成したポリシー設定を組織内のユーザーに適用するには、次を実行します。
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    詳細については、[Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) コマンドレットをご覧ください。
    
### <a name="remove-a-caller-id-policy"></a>発信者番号ポリシーを削除する

組織からポリシーを削除するには、次を実行します。
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
ユーザーからポリシーを削除するには、次を実行します。
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

- Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。 Windows PowerShell を利用すると、Office 365 と Skype for Business Online の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell を使用して Office 365 を管理する6つの理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>関連トピック
[電話番号の移行に関するよくある質問](/microsoftteams/transferring-phone-numbers-common-questions)

[通話プランで使用されるさまざまな種類の電話番号](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)

[発信回線 ID と発信者名の詳細](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
