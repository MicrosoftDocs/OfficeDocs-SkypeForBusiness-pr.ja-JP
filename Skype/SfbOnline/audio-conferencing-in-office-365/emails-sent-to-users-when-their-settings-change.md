---
title: "自分の設定を変更するときに、ユーザーに送信されるメール"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "どのような情報については、自動的にユーザーに電子メールで送信されたのダイヤルイン会議設定を変更するときにについて説明します。 "
ms.openlocfilehash: ccc95e8cee5f4db1729423bc7a1bccecf87ac121
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="emails-sent-to-users-when-their-settings-change"></a>自分の設定を変更するときに、ユーザーに送信されるメール

[電話会議を有効になって](set-up-audio-conferencing.md)いるユーザーに、メールを自動的に送信されます電話会議プロバイダーとして Microsoft を使用します。
  
既定では、音声会議が有効なユーザーに送信されるメールの 4 つの種類があります。ただし、ユーザーに送信されるメールの数を制限する場合は、無効にできます。Office 365 で音声会議は、ユーザーのメールを送信メールで送信する場合。
  
- **または電話会議プロバイダーを Microsoft に変更するときに、電話会議のライセンスが割り当てられます。**
    
     このメールは会議 ID、会議、電話会議でユーザーを手順とリンク ビジネス オンライン会議を更新するツールを使用して既存の会議の更新に、Skype を使用するには、暗証番号 (pin) の既定の会議の電話番号を含む、ユーザー。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)または[電話会議プロバイダーとしての Microsoft の割り当て](assign-microsoft-as-the-audio-conferencing-provider.md)を参照してください。
    
    > [!NOTE]
    > 動的会議 Id の組織を有効にすると、固有の会議 Id のすべてのユーザーの会議をスケジュールするがあります。[組織の動的な Id の電話会議](using-audio-conferencing-dynamic-ids-in-your-organization.md)を設定できます。 
  
    このメールの例を示します。
    
     ![Skype for Business のライセンスを確認します。](../images/audio-conferencing-user-enabled.png)
  
    [Skype for Business や Microsoft チーム アドオンのライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を確認してビジネスのライセンスの Skype に関する詳細情報見つかることができます。
    
- **会議 ID または既定会議の電話番号をユーザーの変更します。**
    
    このメールには、会議 ID、既定の会議の電話番号、および、手順とへのリンク ビジネス オンライン会議を更新するツールのユーザーの既存の会議を更新するための Skype を使ってが含まれています。このメールには、ユーザーの電話会議暗証番号 (pin) が含まれていません。[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)を参照してください。
    
    > [!NOTE]
    > 動的会議 Id の組織を有効にすると、固有の会議 Id のすべてのユーザーの会議をスケジュールするがあります。[組織の動的な Id の電話会議](using-audio-conferencing-dynamic-ids-in-your-organization.md)を設定できます。 
  
    このメールの例を示します。
    
     ![ダイヤルイン会議情報も変更されています。](../images/audio-conferencing-info-change.png)
  
- **電話会議のユーザーの PIN をリセットします。**
    
    このメールには、電話会議の開催者の暗証番号 (pin)、既存の会議 ID、およびユーザーの既定の会議電話番号が含まれています。[ユーザーの音声会議の PIN のリセット](reset-the-audio-conferencing-pin-for-a-user.md)を参照してください。
    
    > [!NOTE]
    > 動的会議 Id の組織を有効にすると、固有の会議 Id のすべてのユーザーの会議をスケジュールするがあります。[組織の動的な Id の電話会議](using-audio-conferencing-dynamic-ids-in-your-organization.md)を設定できます。 
  
    このメールの例を示します。
    
     ![ダイヤルイン会議暗証番号 (pin) を変更します。](../images/audio-conferencing-pin-has-changed.png)
  
- **ユーザーのライセンスを削除または電話会議プロバイダーの他のプロバイダーであるかなし] に変更 Microsoft から時します。**
    
    これは、**電話会議**のライセンスが削除されると、ユーザー、またはユーザーの電話会議プロバイダーを Microsoft からサードパーティ電話会議プロバイダーに変更するときに、 **[なし]**に、プロバイダーを設定するときに発生します。このメールでは、手順と既定の会議電話番号または電話会議 ID などの特定の情報を電話会議を削除するのには、Skype for Business Online Meeting Update Tool を使用するユーザーの情報が含まれています。
    
    [割り当てる一般法人向け Office 365 のライセンスを削除する](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc)、または[電話会議プロバイダーとしてサードパーティ割り当て](assign-a-third-party-as-the-audio-conferencing-provider.md)を参照してください。
    
    このメールの例を示します。
    
     ![ダイヤルイン会議が無効です。](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>送信されたメール メッセージを変更をします。

メール アドレスと*から*の連絡先情報に含まれる表示名を含むユーザーに自動的に送信されるメールは変更できます。既定では、メールの送信者は、Office 365 からは、メール アドレスを変更し、名前を表示することができます Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用します。ユーザーにメールを送信するメール アドレスを変更するには、次の操作を行う必要があります。
  
- _SendEmailFromAddress_パラメーターには、メール アドレスを入力します。
    
- _SendEmailFromDisplayName_パラメーターには、メールの表示名を入力します。
    
- _SendEmailOverride_パラメーターを_True_に設定します。
    
実行してから、メールが送信されたメール アドレスや、メールの表示名など、ユーザーに送信されたメールに変更を行うことができます。
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  メール アドレスの情報を変更する場合は、環境の受信メール ポリシーがアドレスから指定したユーザー設定のメールを許可するかどうかを確認する必要があります。**連絡先情報を上書きする場合は、ユーザーに、電子メールが正しく送信されたことを確認してください。組織内の 1 つのユーザーとこれをテストすることによって、これを行うことができます。
  
メールを含む、組織の他の設定を管理するのには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用できます。
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>場合に送信されるメールをたくないですか。

ユーザーに送信するメールを無効にしたときに、ユーザーにライセンスが割り当てられているを取得している場合でもメールが送信されません。この場合は、会議 ID、既定の会議の電話番号と、さらに、音声、会議の PIN をユーザーに送られません。この場合、別のメールを送信することや、それらを使用してユーザーを指定する必要があります。
  
既定では、メールをユーザーに送信されますが、電話会議用のメールを受信できないようにする場合は、Business 管理センター」または「Windows PowerShell Skype を使用することができます。 
  
 **Business 管理センターの Skype を使用します。**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。
    
4. [ **Microsoft bridge の設定**] ページで、選択または**、電話会議の設定を変更する場合、ユーザーにメールを自動的に送信**をオフにします。 
    
5. {[**保存**] をクリックします。} 
    
 **Windows PowerShell を使用します。**
  
1. 電子メールを送信するすべてのユーザーを無効にするのには、次を実行します。
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

メールを含む、組織の他の設定を管理するのには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用できます。
  
## <a name="what-else-should-you-know-about-this-email"></a>このメールについて他を把握してする必要がありますか。

- 詳細で有効にして、ユーザーにメールを自動的に送信を無効にする][を有効にするか音声会議の設定を変更するときに、送信メールを無効にする](enable-or-disable-sending-emails-when-their-settings-change.md)を参照してください。
    
- ありますユーザーがオーディオの情報を失くしてしに送信するすべてのオーディオ情報にできるようにする必要があります。Business 管理センターの Skype を使用して、ユーザーの電話会議のプロパティ] の [**会議情報を電子メールで送信する**] をクリックして、これを行うことができます。[この情報は、電話会議情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。ただし、この情報には、電話会議 PIN にはが含まれていません。
    
    このに送信されるメールの例を示します。
    
     ![ダイヤルイン会議メール](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- 既定では、メールの送信者は、Office 365 からは、メール アドレスを変更し、名前を表示することができます Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用します。
    
- Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。
  
## <a name="related-topics"></a>関連トピック

[有効にするか、音声会議の設定を変更するときに、送信メールを無効にします。](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[この情報は、電話会議情報を持つユーザーにメールを送信します。](send-an-email-to-a-user-with-their-dial-in-information.md)

