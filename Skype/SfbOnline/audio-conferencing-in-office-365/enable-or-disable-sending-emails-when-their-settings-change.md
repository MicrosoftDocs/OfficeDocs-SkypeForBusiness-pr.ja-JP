---
title: "有効にするか、設定を変更するときに、送信メールを無効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: "有効にするまたは数の変更が pin の変更など、既定の会議の設定は、ユーザーにメールを送信するから Skype を無効にする方法について説明します。 "
ms.openlocfilehash: 3fd5d7c5f12b3e5a88a217eae9a0a86ab0ea9720
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>有効にするか、音声会議の設定を変更するときに、送信メールを無効にします。

ユーザーは、音声会議が有効なときに自動的に電子メールで通知されます。ただし、ビジネスや Microsoft チームのユーザーの Skype に送信されたメールの数を減らすしたい場合があります。このような場合は、電子メールの送信を無効にすることができます。
  
ユーザーが有効になっているか、会議 ID と既定の会議の電話番号と PIN をリセットすると、電話会議を無効になっているときに、電子メールを含む、ユーザーに電話会議のメールに送られません送信メールを無効にした場合.
  
音声会議が有効なときに、ユーザーに送信されるメールの例を示します。
  
![会議のオーディオのメール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>ときは、メールに送信されるユーザーですか。

- 複数のメールに送信された、組織のユーザーが有効な後に電話会議があります。
    
  - **電話会議**のライセンスが割り当てられているとします。
    
  - 手動でをリセットすると、ユーザーの電話会議暗証番号 (pin)。
    
  - ユーザーの会議 ID を手動でリセットする場合
    
  - **電話会議**ライセンスは、それらから削除されます。
    
  - ユーザーの電話会議プロバイダーが変更された場合 Microsoft から別のプロバイダー [**なし]**にします。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>有効にする、またはユーザーに送信されるメールを無効にします。

有効にする、またはユーザーに送信されたメールを無効にするのには、Skype for Business 管理センター」または「Windows PowerShell を使用できます。
  
 **Business 管理センターの Skype を使用します。**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**の場合は、左のナビゲーションで [**電話会議**] をクリックします。
    
3. **Microsoft ブリッジの設定**] ページでオンまたはオフの**場合は、電話会議の設定を変更するユーザーにメールを自動的に送信**します。
    
4. {[**保存**] をクリックします。}
    
    > [!TIP]
    > 送信することもメールをユーザーに電話会議の設定で**電話会議**に移動して > **ユーザー**をユーザーを選択して、**会議情報を電子メールで送信する**] をクリックします。 これを行うをのみが含まれていますが、会議 ID、会議の電話番号、PIN ではないメールが送信されます。 詳細については[、電話会議の情報を持つユーザーにメールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。
  
 **Windows PowerShell を使用します。**
  
- 送信メールを無効にするのには、次を実行します。 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    このコマンドレット ヘルプは、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)を参照してください。
    
## <a name="what-else-should-you-know"></a>他かする必要がありますか。

- 自動メールが無効にするの Skype for Business 管理センターを使った会議 ID と電話番号、メールを送信を手動でトリガーできます。ただし、これを行うには、PIN に含めることはできません。電話会議の PIN をリセットするメールの送信が無効になっている場合は、別の方法でユーザーに送信する必要があります。
    
- 既定ではのメールの送信者が、Office 365 から表示されますが、メール アドレスを変更し、Windows PowerShell を使用して、名前を表示およびも[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用します。
    
    > [!NOTE]
    >  メール アドレスの情報を変更する場合は、環境の受信メール ポリシーがアドレスから指定したユーザー設定のメールを許可するかどうかを確認する必要があります。
  
  - _SendEmailFromAddress_パラメーターには、メール アドレスを入力します。
    
  - _SendEmailFromDisplayName_パラメーターには、メールの表示名を入力します。
    
  - _SendEmailOverride_パラメーターを_True_に設定します。
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- ユーザーにメールを送信することができます無効にする、Skype を Business 管理センターの Windows PowerShell を使用します。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

- これらのコマンドレットを使用して時間を節約したり、自動化したりすることができます。
    
  - [Get CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [削除 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。
  
## <a name="related-topics"></a>関連トピック

[その電話会議の設定を変更するときに、ユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change.md)

[この情報は、電話会議情報を持つユーザーにメールを送信します。](send-an-email-to-a-user-with-their-dial-in-information.md)

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)

