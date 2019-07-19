---
title: Skype for Business Online の設定が変更されたときにユーザーに送信されたメール
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Skype for Business Online でダイヤルイン会議の設定が変更されたときに、メールで自動的に送信される情報について説明します。 '
ms.openlocfilehash: 4f1916778985012754cc436f37e76f0097dd49e9
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792437"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Skype for Business Online の設定が変更されたときにユーザーに送信されたメール

> [!Note]
> Microsoft Teams で自動メール情報を探している場合は、「 [Microsoft teams で設定が変更されたときにユーザーに送信されるメール](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)」を参照してください。

Microsoft を電話会議プロバイダーとして使用する電話[会議用に有効になっ](set-up-audio-conferencing.md)ているユーザーには、メールが自動的に送信されます。
  
既定では、電話会議が有効になっているユーザーに送信されるメールには4種類のメールが用意されています。 ただし、ユーザーに送信されるメールの数を制限する場合は、オフにすることができます。 Office 365 の電話会議では、次の場合にユーザーのメールにメールが送信されます。
  
- **電話会議ライセンスが割り当てられているか、電話会議プロバイダーを Microsoft に変更する場合。**
    
     このメールには、会議 ID、会議用の既定の会議電話番号、ユーザーの電話会議の PIN、ユーザーの既存の会議を更新するために使用される Skype for Business Online 会議更新ツールを使用するための手順とリンクが含まれています。ユーザーズ. 「 [Skype For business ライセンスの割り当て](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」または「 [Microsoft の電話会議プロバイダーとしての割り当て](assign-microsoft-as-the-audio-conferencing-provider.md)」を参照してください。
    
    > [!NOTE]
    > 組織で動的会議 Id が有効になっている場合、スケジュールされているすべてのユーザーの会議には、固有の会議 Id が割り当てられます。 [組織内の電話会議の動的 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)を設定することができます。 
  
    このメールの例を次に示します。
    
     ![Skype for Business のライセンスを確認する](../images/audio-conferencing-user-enabled.png)
  
    Skype for business のライセンスの詳細については、「 [skype For business アドオンライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。
    
- **会議 ID またはユーザーの既定の会議の電話番号が変更されます。**
    
    このメールには、会議 ID、既定の会議電話番号、およびユーザーの既存の会議を更新するために使用される Skype for Business Online Meeting 更新ツールを使用するための手順とリンクが含まれています。 ただし、このメールには、ユーザーの電話会議の PIN は含まれていません。 「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user.md)」を参照してください。
    
    > [!NOTE]
    > 組織で動的会議 Id が有効になっている場合、スケジュールされているすべてのユーザーの会議には、固有の会議 Id が割り当てられます。 [組織内の電話会議の動的 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)を設定することができます。 
  
    このメールの例を次に示します。
    
     ![ダイヤルイン会議情報が変更されました。](../images/audio-conferencing-info-change.png)
  
- **ユーザーの電話会議の PIN がリセットされます。**
    
    このメールには、開催者の電話会議の PIN、既存の会議 ID、ユーザー用の既定の会議電話番号が含まれています。 「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin.md)」を参照してください。
    
    > [!NOTE]
    > 組織で動的会議 Id が有効になっている場合、スケジュールされているすべてのユーザーの会議には、固有の会議 Id が割り当てられます。 [組織内の電話会議の動的 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)を設定することができます。 
  
    このメールの例を次に示します。
    
     ![ダイヤルイン会議の PIN が変更されました。](../images/audio-conferencing-pin-has-changed.png)
  
- **ユーザーのライセンスが削除されるか、電話会議プロバイダーが Microsoft から別のプロバイダーまたは [なし] に変更されたとき。**
    
    この問題は、**電話会議**のライセンスがユーザーから削除された場合、またはユーザーの電話会議プロバイダーを Microsoft からサードパーティの電話会議プロバイダーに変更した場合、またはプロバイダーを **[なし**] に設定した場合に発生します。 このメールには、Skype for Business Online Meeting Update ツールを使用して、既定の会議電話番号や会議 ID などの電話会議固有の情報を削除するための手順と情報が含まれています。
    
    「[一般法人向け Office 365 ライセンスの割り当てまたは解除方法](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc)」をご覧ください。
    
    このメールの例を次に示します。
    
     ![ダイヤルイン会議が無効になっています。](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>送信されたメールメッセージに変更を加える

メールアドレス、および*差出人*の連絡先情報に含まれている表示名など、ユーザーに自動的に送信されるメールを変更できます。 既定では、メールの送信者は Office 365 から送信されますが、Windows PowerShell と[-](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用してメールアドレスと表示名を変更することができます。 ユーザーにメールを送信するメールアドレスを変更するには、次のことを行う必要があります。
  
- _SendEmailFromAddress_ パラメーターにメール アドレスを入力する
    
- _SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する
    
- _SendEmailOverride_パラメーターを_True_に設定します。
    
次のように実行して、メールの送信元のメールアドレスやメールの表示名など、ユーザーに送信されるメールの変更を行うことができます。
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  メールアドレス情報を変更する場合は、カスタム指定の差出人アドレスから送信されるメールが、環境の受信メールポリシーで許可されていることを確認する必要があります。 *差出人*の連絡先情報を上書きする場合は、ユーザーにメールが正しく送信されていることを確認する必要があります。 これは、組織内の1人のユーザーとテストすることで実現できます。
  
会議 ID をリセットする[](https://go.microsoft.com/fwlink/?LinkId=627285)
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>メールを送信したくない場合はどうすればよいですか?

ユーザーへのメールの送信を無効にすると、ユーザーにライセンスが割り当てられてもメールは送信されません。 この場合、会議 ID、既定の会議電話番号、さらに重要なのは、電話会議の PIN はユーザーに送信されません。 この問題が発生した場合は、個別のメールを送信するか、または電話をかけて、ユーザーに通知する必要があります。
  
既定では、メールはユーザーに送信されますが、電話会議のメールを受信しないようにするには、Skype for Business 管理センターまたは Windows PowerShell を使用します。 
 
![](../images/sfb-logo-30x30.png)**Skype for business 管理センターを使用し**た skype for business ロゴを示すアイコン  
    
1. **Skype for Business 管理センター**の左側のナビゲーション ウィンドウで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に移動します。
    
2. [ **Microsoft bridge の設定**] ページで、[**電話会議の設定が変更された場合にユーザーに電子メールを自動的に送信する**] をオンまたはオフにします。 
    
3. **[保存]** をクリックします。 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Windows PowerShell を使用する**
  
1. すべてのユーザーメールの送信を無効にするには、次の操作を実行します。
    
   ```
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

会議 ID をリセットする[](https://go.microsoft.com/fwlink/?LinkId=627285)
  
## <a name="what-else-should-you-know-about-this-email"></a>このようなメールについて知っておくべきその他のこと

- ユーザーへのメールの自動送信を有効または無効にする方法について詳しくは、「[電話会議の設定が変更されたときにメールを送信する](enable-or-disable-sending-emails-when-their-settings-change.md)」を参照してください。
    
- ユーザーの音声情報が失われたり、それらの音声情報をすべて送信したりできるようにする必要があります。 これを行うには、Skype for Business 管理センターを使って、ユーザーの電話会議のプロパティの下にある [**電話会議情報をメールで送信**] をクリックします。 「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。 ただし、この情報には電話会議の PIN は含まれていません。
    
    このメールの例を次に示します。
    
     ![ダイヤルイン会議のメール](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 既定では、メールの送信者は Office 365 から送信されますが、Windows PowerShell と[-](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用してメールアドレスと表示名を変更することができます。
    
- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を向上させるための多くの利点があります。たとえば、複数のユーザーに対して同時に設定を変更する場合です。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[電話会議の設定が変更されたときのメールの自動送信を有効または無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)
