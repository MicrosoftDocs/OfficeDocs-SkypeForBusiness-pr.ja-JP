---
title: "ユーザーにダイヤルイン会議情報が含まれたメールを送信する"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
description: "Send your users an email with their dial-in conferencing information."
---

# ユーザーにダイヤルイン会議情報が含まれたメールを送信する

ユーザーにダイヤルイン会議の情報を送信することが必要になる場合があります。 そのような場合は、Skype for Business 管理センターで、ユーザーのダイヤルイン プロパティの [ **電話会議情報をメールで送信**] をクリックします。 送信するメールには、次のようなすべてのダイヤルイン情報が含まれています。
  
- ユーザー用の会議の電話番号またはダイヤルイン電話番号。
    
- ユーザーの会議 ID。
    
    > [!NOTE]
    > 静的 ID は、組織内のユーザーがランダムな番号を覚えるのを望まないときや、ユーザーが特定の番号を選択できる場合や、覚えやすい番号を取得している場合に好んで使用されます。 動的会議 ID が使用される場合、ユーザーがスケジュールするそれぞれの会議に一意の会議 ID が割り当てられます。 静的電話会議 ID ではなく、動的電話会議 ID を割り当てる場合は、[組織での電話会議の動的 ID の使用](using-audio-conferencing-dynamic-ids-in-your-organization.md)をご覧ください。 
  
以下に、送信されるこのメールの例を示します。
  
![ダイヤルイン会議のメール](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## ダイヤルイン会議情報が記載されたメールをユーザーに送信する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動して、左のナビゲーションで [ **ダイヤルイン会議**] をクリックします。
    
3. [ **ダイヤルイン ユーザー**] をクリックして、ユーザーを選びます。
    
4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。
    
> [!TIP]
> ダイヤルイン会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーのプロパティ、[ **ダイヤルイン会議**]、[ **電話会議情報をメールで送信**] の順に移動します。 
  
## このようなメールについて知っておくべきその他のこと

- ダイヤルイン会議を有効にした後、組織内のユーザーに対して送信されるメールが複数あります。
    
  - ユーザーに **Skype for Business PSTN 会議**ライセンスが割り当てられている場合。
    
  - ユーザーのダイヤルイン会議の PIN を手動でリセットした場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - ユーザーの **Skype for Business PSTN 会議**ライセンスが削除された場合。
    
  - ユーザーのダイヤルイン会議プロバイダーが Microsoft から別のプロバイダー、または [ **なし**] に変更された場合。
    
  - ユーザーのダイヤルイン会議プロバイダーが Microsoft に変更された場合。
    
- 既定では、メールの差出人は Office 365 ですが、Windows PowerShell と [Set-CsOnlineDialInConferencingTenantSettings](http://go.microsoft.com/fwlink/?LinkId=708983) コマンドレットを使って、メール アドレスと表示名を変更できます。 ユーザーにメールを送信するためのメール アドレスを変更するには、次の操作を実行する必要があります。
    
    > [!NOTE]
    > メール アドレス情報を変更する場合、設定した独自のメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されることを確認する必要があります。 
  
  -  _SendEmailFromAddress_ パラメーターにメール アドレスを入力する
    
  -  _SendEmailOverride_ パラメーターを _True_ に設定する
    
  -  _SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
## Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
    ユーザーにダイヤルイン会議情報が記載されたメールを送信するには、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理する 6 つの理由](http://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](http://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Lync Online の概要](http://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Lync Online の管理](http://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](http://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。 このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](http://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 
  

