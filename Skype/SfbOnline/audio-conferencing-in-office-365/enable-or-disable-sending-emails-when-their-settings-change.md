---
title: 有効にするか、オンライン ビジネスの Skype で電話会議の設定を変更すると送信メールを無効にします。
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '有効にするか、暗証番号 (pin) の変更など、既定の会議の設定番号を変更するときに、ユーザーに e メールを送信することから、Skype を無効にする方法を説明します。 '
ms.openlocfilehash: a9100de01fc835916af54d08b84dbd03a06ec1d6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229819"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>有効にするか、オンライン ビジネスの Skype で電話会議の設定を変更すると送信メールを無効にします。

> [!Note]
> 有効にするか、マイクロソフトのチームでの送信メールを無効にする場合は、[有効にするかマイクロソフトのチームでのオーディオ会議設定を変更すると、送信メールを無効にする](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)を参照してください。

ユーザーは、電話会議が有効になっているときに自動的に電子メールで通知されます。 場合があります、ただし、Skype をビジネス ユーザーに送信される電子メールの数を減らしたいとします。 このような場合は、電子メールの送信を無効にできます。
  
オーディオ会議の電子メールをユーザーが有効になっているか、オーディオ会議は、会議 ID と既定の会議の電話番号の変更と、PIN をリセットすると無効にすると、電子メールを含む、ユーザーに送信されません送信メールを無効にした場合.
  
電話会議が有効になっているときに、ユーザーに送信されるメールの例を以下に示します。
  
![オーディオ会議の電子メール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>メール ユーザーに送信するのでしょうか。

- 送信される、組織内のユーザーを有効にした後には、オーディオ会議のいくつかの電子メールがあります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - リセットすると手動で電話会議のユーザーの暗証番号 (pin) です。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - **電話会議**のライセンスは、それらから削除されます。
    
  - オーディオ会議プロバイダーのユーザーの変更されたとき Microsoft から別のプロバイダーまたは **[なし]** にします。
    
  - マイクロソフトにユーザーの電話会議プロバイダーが変更されたとき。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>有効にするか、ユーザーに送信される電子メールを無効にします。

有効にするか、ユーザーに送信される電子メールを無効にするのには、ビジネス管理センターの Skype または Windows PowerShell を使用できます。

 
![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**
    
1. **Skype**ビジネス管理センターは、左側のナビゲーションでは、[**電話会議**] をクリックします。
    
2. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。****
    
3. 電話会議の設定を使用してユーザーにメールを送信することもできます。****
    
    > [!TIP]
    > 送信することも電子メール ユーザーに電話会議の設定を使用して**オーディオ会議**に > の**ユーザー**ユーザーを選択し、**電子メールを使用して会議情報を送信**] をクリックします。  これを行うには、会議 ID と電話会議の番号がない、暗証番号 (pin) のみを含む電子メールが送信されます。  詳細については[、オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**
  
- 送信メールを無効にするのには、次を実行します。 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    このコマンドレットのヘルプを表示するには、[一連の CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)を参照してください。
    
## <a name="what-else-should-you-know"></a>その他の情報

- 自動メールを無効にすると、ビジネス管理センターは、Skype を使用して会議の ID と電話番号と電子メールを送信するを手動でトリガーできます。 ただし、これを行うには、PIN に含めることはできません。 オーディオ会議の暗証番号 (pin) をリセットするし、電子メールの送信が無効になっている、別の方法でユーザーに送信する必要があります。
    
- ユーザーに電子メールを送信を無効にできます、Skype のビジネス管理センターまたは Windows PowerShell の使用します。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- これらのコマンドレットを使用するには時間を保存するか、これを自動化します。
    
  - [Get CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [削除 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell で行うのは、ユーザーを管理し、ユーザーに何を許可して何を禁止するかを管理することです。Windows PowerShell を利用すると、Office 365 の管理を 1 か所で行うことができるので、複数のタスクを担当する管理者の日常業務を単純化できます。Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Lync Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連項目

[オーディオ会議設定を変更するときにユーザーに送信される電子メール](emails-sent-to-users-when-their-settings-change.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)


