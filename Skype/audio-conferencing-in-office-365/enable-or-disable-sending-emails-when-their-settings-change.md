---
title: "電話会議の設定が変更されたときのメールの自動送信を有効または無効にする"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
description: "Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. "
---

# 電話会議の設定が変更されたときのメールの自動送信を有効または無効にする

電話会議は既定で、ユーザーが電話会議で有効であれば、ユーザーにメールを送信します。ただし、場合によっては、Skype for Business および Microsoft Teams のユーザーに送信されるメールの数を減らしたいことがあります。この場合は、メール送信を無効にできます。
  
メール送信を無効にすると、電話会議のすべてのメールはユーザーに送信されなくなります。このようなメールには、ユーザーが電話会議で有効または無効になった場合、ユーザーの PIN がリセットされた場合、会議 ID と既定の電話会議の番号が変更された場合に関するメールが含まれます。
  
次に示しているのは、電話会議が有効になっているユーザーに送信されるメールの例です。
  
![ダイヤルイン会議のメール](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## ユーザーにメールが送信される場合

- 電話会議を有効にした後、組織内のユーザーに対して送信されるメールが複数あります。
    
  - ユーザーに **電話会議**ライセンスが割り当てられている場合。
    
  - ユーザーの電話会議の PIN を手動でリセットした場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - ユーザーの **電話会議**ライセンスが削除された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーに変更されるか、設定が [ **なし**] に変更された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。
    
## ユーザーへのメール送信を有効または無効にする

Skype for Business 管理センターまたは Windows PowerShell を使用すると、ユーザーへのメール送信を有効または無効にすることができます。
  
 **Skype for Business 管理センターを使用する**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動して、左のナビゲーションで [ **電話会議**] をクリックします。
    
3. [ **Microsoft Bridge の設定**] ページで、[ **いずれかの電話会議の構成が変更された場合に自動でユーザーに電子メールを送信する**] をオンまたはオフにします。
    
4. [ **保存**] をクリックします。
    
    > [!TIP]
    > 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーのプロパティ、[ **電話会議**]、[ **電話会議情報をメールで送信**] の順に移動します。 > この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。 > 「[ユーザーにダイヤルイン会議情報が含まれたメールを送信する](send-an-email-to-a-user-with-their-audio-conferencing-information.md)」をご覧ください。 
  
 **Windows PowerShell を使用する**
  
- メールの送信を無効にするために以下を実行します。
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    このコマンドレットについては、「[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)」をご覧ください。
    
## その他の情報

- Skype for Business 管理センターを使用すると、自動メールが無効である場合でも、会議 ID と電話番号が含まれるメールの送信を手動でトリガーすることができます。ただし、この操作を行う場合、PIN は含まれません。電話会議の PIN をリセットする必要があり、メール送信が無効である場合は、別の方法でユーザーに送信する必要があります。
    
- 既定では、メールの差出人は Office 365 ですが、Windows PowerShell と [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) コマンドレットを使って、メール アドレスと表示名を変更できます。
    
    > [!NOTE]
    > メール アドレス情報を変更したい場合は、指定したカスタム送信元アドレスから送信されるメールが、環境の受信メール ポリシーで許可されていることを確認する必要があります。 
  
  -  _SendEmailFromAddress_ パラメーターにメール アドレスを入力する
    
  -  _SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する
    
  -  _SendEmailOverride_ パラメーターを _True_ に設定する
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- Skype for Business 管理センターまたは Windows PowerShell を使用すると、ユーザーへのメール送信を無効にすることができます。
    
## Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするために、以下のコマンドレットを使用することもできます。
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 
  
## 関連項目

#### 

[Office 365 でのダイヤルイン会議](../misctopics/dial-in-conferencing-in-office-365.md)

