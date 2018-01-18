---
title: "有効にするかの設定を変更すると、送信メールを無効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "有効にするか、暗証番号 (pin) の変更など、既定の会議の設定番号を変更するときに、ユーザーに e メールを送信することから、Skype を無効にする方法を説明します。 "
ms.openlocfilehash: 4efabf42f7253d89b37282103a3046cf7b2b0d26
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>有効にするか、オーディオ会議の設定を変更すると、送信メールを無効にします。

ユーザーは、電話会議が有効になっているときに自動的に電子メールで通知されます。 ただし、Skype のビジネスおよびマイクロソフトのチームのユーザーに送信される電子メールの数を削減したい場合があります。 このような場合は、電子メールの送信を無効にできます。
  
オーディオ会議の電子メールをユーザーが有効になっているか、オーディオ会議は、会議 ID と既定の会議の電話番号の変更と、PIN をリセットすると無効にすると、電子メールを含む、ユーザーに送信されません送信メールを無効にした場合.
  
電話会議が有効になっているときに、ユーザーに送信されるメールの例を以下に示します。
  
![オーディオ会議の電子メール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>メール ユーザーに送信するのでしょうか。

- 送信される、組織内のユーザーを有効にした後には、オーディオ会議のいくつかの電子メールがあります。
    
  - ときに、**オーディオ会議**のライセンスが割り当てられます。
    
  - リセットすると手動で電話会議のユーザーの暗証番号 (pin) です。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - **電話会議**のライセンスは、それらから削除されます。
    
  - オーディオ会議プロバイダーのユーザーの変更されたとき Microsoft から別のプロバイダーまたは**[なし]**にします。
    
  - マイクロソフトにユーザーの電話会議プロバイダーが変更されたとき。
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>有効にするか、ユーザーに送信される電子メールを無効にします。

有効にするか、ユーザーに送信される電子メールを無効にするのには、ビジネス管理センターの Skype または Windows PowerShell を使用できます。
  
 **ビジネス管理センターに、Skype を使用します。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**では、左側のナビゲーションで [**電話会議**] をクリックします。
    
3. **Microsoft ブリッジの設定**] ページをオンまたはオフの**オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**する。
    
4. [ **保存**] をクリックします。
    
    > [!TIP]
    > 送信することも電子メール ユーザーに電話会議の設定を使用して**オーディオ会議**に > の**ユーザー**ユーザーを選択し、**電子メールを使用して会議情報を送信**] をクリックします。  これを行うには、会議 ID と電話会議の番号がない、暗証番号 (pin) のみを含む電子メールが送信されます。  詳細については[、オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。
  
 **Windows PowerShell を使用します。**
  
- 送信メールを無効にするのには、次を実行します。 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    このコマンドレットのヘルプを表示するには、[一連の CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)を参照してください。
    
## <a name="what-else-should-you-know"></a>その他の情報

- 自動メールを無効にすると、ビジネス管理センターは、Skype を使用して会議の ID と電話番号と電子メールを送信するを手動でトリガーできます。 ただし、これを行うには、PIN に含めることはできません。 オーディオ会議の暗証番号 (pin) をリセットするし、電子メールの送信が無効になっている、別の方法でユーザーに送信する必要があります。
    
- 既定では、電子メールの送信者は、Office 365 からなりますが、電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示して[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用しても。
    
    > [!NOTE]
    >  電子メール アドレス情報を変更する場合は、環境内の受信電子メール ポリシーが、アドレスから指定されたユーザーから送信される電子メールを許可するかどうかを確認する必要があります。
  
  - _SendEmailFromAddress_ パラメーターにメール アドレスを入力する
    
  - _SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する
    
  - _SendEmailOverride_パラメーターを_True_に設定します。
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- ユーザーに電子メールを送信を無効にできます、Skype のビジネス管理センターまたは Windows PowerShell の使用します。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- これらのコマンドレットを使用するには時間を保存するか、これを自動化します。
    
  - [Get CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [削除 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。 Windows PowerShell を実行する複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 を管理できます。 Windows PowerShell を使い始めるには、以下のトピックを参照してください。
    
  - [Office 365 の PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。 次のトピックで、これらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[オーディオ会議設定を変更するときにユーザーに送信される電子メール](emails-sent-to-users-when-their-settings-change.md)

[オーディオ会議の情報を持つユーザーに電子メールを送信します。](send-an-email-to-a-user-with-their-dial-in-information.md)

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)

