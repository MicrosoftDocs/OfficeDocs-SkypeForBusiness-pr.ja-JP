---
title: Skype for Business Online で電話会議の設定が変更されたときにメールの送信を有効または無効にする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Pin が変更された場合や、既定の電話会議番号が変更された場合に、Skype が電子メールをユーザーに送信するのを有効または無効にする方法について説明します。 '
ms.openlocfilehash: ac3f6b94f0ddb4410d89ecd95aef346eb32c9ff1
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494228"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Skype for Business Online で電話会議の設定が変更されたときにメールの送信を有効または無効にする

> [!Note]
> Microsoft Teams でメールの送信を有効または無効にする場合は、「 [Microsoft teams で電話会議の設定が変更されたときにメールの送信を有効または無効](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)にする」を参照してください。

電話会議が有効になっていると、ユーザーにメールで自動的に通知されます。 ただし、Skype for Business ユーザーに送信されるメールの数を少なくする必要がある場合もあります。 その場合は、メールの送信を無効にすることができます。
  
メールの送信を無効にした場合、電話会議のメールはユーザーに送信されません。電話会議でユーザーが有効または無効になっているとき、電話会議の PIN がリセットされたとき、会議 ID と既定の会議の電話番号が変更されたときのメールが含まれます。.
  
次に示すのは、電話会議が有効になっているユーザーに送信されるメールの例です。
  
![電話会議のメール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>ユーザーにメールが送信されるのはいつですか?

- 電話会議を有効にした後、組織内のユーザーに送信されるメールが複数あります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - ユーザーの電話会議の PIN を手動でリセットした場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - **電話会議**ライセンスが削除されたとき。
    
  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたは **[なし**] に変更された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>ユーザーへのメール送信を有効または無効にする

Skype for Business 管理センターまたは Windows PowerShell を使用して、ユーザーに送信されたメールを有効または無効にすることができます。

 
![](../images/sfb-logo-30x30.png) **Skype for business 管理センターを使用し**た skype for business ロゴを示すアイコン
    
1. **Skype For business 管理センター**の左側のナビゲーションで、[**電話会議**] をクリックします。
    
2. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。****
    
3. 電話会議の設定を使用してユーザーにメールを送信することもできます。****
    
    > [!TIP]
    > 電話会議の設定を使用してユーザーにメールを送信することもできます。電話**会議** > の**ユーザー**に移動し、ユーザーを選んで、[**電話会議情報をメールで送信**] をクリックします。  この操作を行うと、会議 ID と電話会議の番号のみを含むメールが送信され、PIN は送信されません。  詳細については、「[電話会議の情報をユーザーに電子メールで送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Windows PowerShell を使用する**
  
- メールの送信を無効にするには、次の操作を実行します。 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    このコマンドレットについては、「 [Set--](https://go.microsoft.com/fwlink/?LinkId=715757)」を参照してください。
    
## <a name="what-else-should-you-know"></a>その他の情報

- 自動メールを無効にしても、Skype for Business 管理センターを使って、会議 ID と電話番号を使ってメールを手動で送信することができます。 ただし、この場合、PIN は含まれません。 電話会議の PIN をリセットして、メールの送信を無効にする場合は、別の方法でユーザーに送信する必要があります。
    
- Skype for Business 管理センターまたは Windows PowerShell を使用して、ユーザーへのメールの送信を無効にすることができます。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- これらのコマンドレットを使用して、時間を節約したり、自動化したりすることができます。
    
  - [Get--](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove--](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get--](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更されたときにユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)


