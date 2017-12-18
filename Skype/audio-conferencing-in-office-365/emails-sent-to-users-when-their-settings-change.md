---
title: "ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
description: "Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. "
---

# ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「免責事項」をお読みください。 
  
ダイヤルイン会議プロバイダーとして Microsoft を使用する[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)になっているユーザーに対して、電子メールが自動送信されます。 
  
既定では、ダイヤルイン会議に対応しているユーザーに 4 種類のメールが送信されます。ただし、ユーザーに送信されるメールの数を制限したい場合は、この機能をオフにできます。Skype for Business Online のダイヤルイン会議からユーザーにメールが送信されるのは、以下の場合です。
  
- ** **Skype for Business PSTN 会議**ライセンスがユーザーに割り当てられているか、ダイヤルイン会議プロバイダーを Microsoft に変更した場合**
    
     この場合のメールには、会議 ID、会議の既定の電話番号、ユーザーのダイヤルイン会議 PIN、ユーザーが既存の会議の更新に使用する Skype for Business Online Meeting Update Tool の使用方法とリンクが含まれています。詳細については、「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」または「[Microsoft を電話会議プロバイダーとして割り当てる](assign-microsoft-as-the-audio-conferencing-provider.md)」をご覧ください。
    
    > [!NOTE]
    > 組織が動的電話会議 ID に対応している場合、ユーザーが予約したすべての会議には一意の電話会議 ID が割り当てられます。 [組織での電話会議の動的 ID の使用](using-audio-conferencing-dynamic-ids-in-your-organization.md)を設定することができます。 
  
    以下にメールの例を示します。
    
     ![Skype for Business のライセンス検証](../images/17913e03-8b4a-4563-b58d-2f09b65fbcaa.png)
  
    Skype for Business ライセンスの詳細については、「[Skype for Business と Microsoft Teams のアドオン ライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。
    
- **会議 ID またはユーザーの既定の会議の電話番号が変更された場合**
    
    この場合のメールには、会議 ID、既定の会議電話番号、ユーザーが既存の会議の更新に使用する Skype for Business Online Meeting Update Tool の使用方法とリンクが含まれています。ただし、このメールにはユーザーのダイヤルイン会議の PIN は含まれていません。詳細については、「[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)」を参照してください。
    
    > [!NOTE]
    > 組織が動的電話会議 ID に対応している場合、ユーザーが予約したすべての会議には一意の電話会議 ID が割り当てられます。 [組織での電話会議の動的 ID の使用](using-audio-conferencing-dynamic-ids-in-your-organization.md)を設定することができます。 
  
    以下にメールの例を示します。
    
     ![ダイヤルイン会議情報が変更されました。](../images/d6d3e028-d9fb-48c4-97c0-a73d6ade5ea3.png)
  
- **ユーザーのダイヤルイン会議の PIN がリセットされた場合**
    
    このメールには、開催者のダイヤルイン会議の PIN、既存の会議 ID、ユーザーの既定の会議電話番号が含まれます。「[ユーザーのダイヤルイン会議の PIN をリセットする](reset-the-audio-conferencing-pin-for-a-user.md)」をご覧ください。 
    
    > [!NOTE]
    > 組織が動的電話会議 ID に対応している場合、ユーザーが予約したすべての会議には一意の電話会議 ID が割り当てられます。 [組織での電話会議の動的 ID の使用](using-audio-conferencing-dynamic-ids-in-your-organization.md)を設定することができます。 
  
    以下にメールの例を示します。
    
     ![ダイヤルイン会議 PIN が変更されました。](../images/df8df4f8-d11f-41b8-9187-99e66a88831b.png)
  
- **ユーザーのライセンスが削除されたか、またはダイヤルイン会議プロバイダーが Microsoft から別のプロバイダーまたは [なし] に変更された場合**
    
    これは、 **Skype for Business PSTN 会議**ライセンスがユーザーから削除された場合、ユーザーのダイヤルイン会議プロバイダーが Microsoft からサードパーティの電話会議プロバイダーに変更された場合、またはプロバイダーが [ **なし**] に設定された場合に該当します。 この場合のメールには、ユーザーが Skype for Business Online Meeting Update Tool を使って、既定の会議電話番号や会議 ID などのダイヤルイン会議に固有の情報を削除するための手順と情報が含まれています。
    
    [一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)または[サードパーティを電話会議プロバイダーとして割り当てる](assign-a-third-party-as-the-audio-conferencing-provider.md)を参照してください。
    
    以下にメールの例を示します。
    
     ![ダイヤルイン会議が無効になっています。](../images/4ebc8ae6-b516-452e-8d27-6177e145daba.png)
  
## ユーザーに送信されたメール メッセージの内容を変更する

メール アドレスと *から*  の連絡先情報に含まれる表示名を含む、ユーザーに自動的に送信されるメールは変更できます。既定では、メールの送信者は Office 365 からは、メール アドレスを変更し、名前を表示することができます Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用します。電子メールを送信するメール アドレスを変更するには、ユーザーする必要があります。
  
-  _SendEmailFromAddress_ パラメーターにメール アドレスを入力する
    
-  _SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する
    
-  _SendEmailOverride_ パラメーターを _True_ に設定する
    
メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
> メール アドレス情報を変更したい場合は、指定したカスタム送信元アドレスから送信されるメールが、環境の受信メール ポリシーで許可されていることを確認する必要があります。 > [ *差出人*  ] 連絡先情報を上書きする場合は、メールがユーザーに正しく送信されることを確認する必要があります。 確認するには、組織内の 1 人のユーザーに対してテストします。
  
メールなど、組織内の他の設定を管理するのには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用できます。
  
## ユーザーにメールを送信したくない場合

ユーザーへのメールの送信を無効にした場合は、ユーザーがライセンスを割り当てられたときでもメールは送信されません。 この場合は、会議 ID、既定の会議電話番号、そしてより重要なことですが、ダイヤルイン会議の PIN がユーザーに送信されません。 この場合、別にメールを送信するか、または電話でユーザーに伝達する必要があります。
  
既定では、ユーザーにメールが送信されますが、ダイヤルイン会議のメールをユーザーが受信しないようにするには、Skype for Business 管理センターまたは Windows PowerShell を使用します。 
  
### Skype for Business 管理センターを使用する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**、[ **Skype for Business**] の順に移動します。
    
3. [ **Skype for Business 管理センター**]の左のナビゲーションで、[ **ダイヤルイン会議**]、[ **Microsoft Bridge の設定**] の順に移動します。
    
4. [ **Microsoft Bridge の設定**] ページで、[ **ユーザーの PSTN ダイヤルイン構成が変更されると、メールがユーザーに自動送信されます**] をオンまたはオフにします。
    
5. [ **保存**] をクリックします。
    
### Windows PowerShell を使用する

- すべてのユーザー メールの送信を無効にするには、以下を実行します。
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

メールなど、組織内の他の設定を管理するのに[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)を使用することができます。
  
## このようなメールについて知っておくべきその他のこと

- ユーザーへのメールの自動送信の有効化と無効化の詳細については、「[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)」を参照してください。
    
- ユーザーがダイヤルイン情報を失くしてしまった場合や、ダイヤルイン情報のすべてをユーザーに送信する必要がある場合があります。そのような場合は、Skype for Business 管理センターで、ユーザーのダイヤルイン プロパティの [ **電話会議情報をメールで送信**] をクリックします。「[ユーザーにダイヤルイン会議情報が含まれたメールを送信する](send-an-email-to-a-user-with-their-audio-conferencing-information.md)」を参照してください。ただし、この情報にはダイヤルイン会議の PIN が含まれません。
    
    以下に、送信されるこのメールの例を示します。
    
     ![ダイヤルイン会議のメール](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Windows PowerShell で管理する方法

- 既定では、メールの送信者は Office 365 からは、メール アドレスを変更し、名前を表示することができます Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用します。
    
- Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。次のトピックで、これらの利点を説明します。
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  
## 関連項目
<a name="MT_Footer"> </a>

#### 

[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)
  
[ユーザーにダイヤルイン会議情報が含まれたメールを送信する](send-an-email-to-a-user-with-their-audio-conferencing-information.md)

