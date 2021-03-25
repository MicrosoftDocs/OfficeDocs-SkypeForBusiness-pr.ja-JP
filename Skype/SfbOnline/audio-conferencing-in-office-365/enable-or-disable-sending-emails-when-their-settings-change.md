---
title: Skype for Business Online で電話会議の設定が変更された場合のメールの送信を有効または無効にする
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'ピン留めなどの設定が変更された場合や、既定の会議番号が変更された場合に、Skype がユーザーにメールを送信する機能を有効または無効にする方法について説明します。 '
ms.openlocfilehash: 6b9e67d8c87b023409b7934a944f298487f91289
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114253"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Skype for Business Online で電話会議の設定が変更された場合のメールの送信を有効または無効にする

> [!Note]
> Microsoft Teams でメールの送信を有効または無効にする場合は [、「Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)で電話会議の設定が変更された場合のメールの送信を有効または無効にする」を参照してください。

電話会議が有効になると、ユーザーにメールで自動的に通知されます。 ただし、Skype for Business ユーザーに送信されるメールの数を減らしたい場合があります。 このような場合は、メールの送信を無効にできます。
  
メールの送信を無効にした場合、ユーザーが電話会議で有効または無効になっている場合、PIN がリセットされた場合、会議 ID と既定の会議の電話番号が変更された場合のメールなど、電話会議のメールはユーザーに送信されません。
  
電話会議が有効になっているユーザーに送信されるメールの例を次に示します。
  
![電話会議のメール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>ユーザーにメールが送信されるのは、いつですか?

- 電話会議を有効にすると、組織内のユーザーに送信されるメールが複数あります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - ユーザーの電話会議の PIN を手動でリセットする場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - 電話会議 **ライセンスが** 削除された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたはなしに変更 **された場合**。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>メールがユーザーに送信されるのを有効または無効にする

Skype for Business 管理センターまたは Skype for Business Windows PowerShellを使用して、ユーザーに送信されたメールを有効または無効にできます。

 
![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**
    
1. Skype **for Business 管理センターの** 左側のナビゲーションで、[電話会議 **] をクリックします**。
    
2. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。
    
3. 電話会議の設定を使用してユーザーにメールを送信することもできます。
    
    > [!TIP]
    > 電話会議の設定を使ってユーザーにメールを送信するには、[電話会議ユーザー ] に移動し、ユーザーを選び、[電話会議情報をメールで送信] を  >  **クリックします**。  この操作を行う場合、PIN は含めではなく、会議 ID と電話会議の電話番号のみを含むメールが送信されます。  詳細 [については、「電話会議の情報を含むメールを](send-an-email-to-a-user-with-their-dial-in-information.md) ユーザーに送信する」を参照してください。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Windows PowerShell を使用する**
  
- 次のコマンドを実行して、メールの送信を無効にします。 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    このコマンドレットのヘルプについては [、「Set-CsOnlineDialInConferencingTenantSettings」を参照してください](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)。
    
## <a name="what-else-should-you-know"></a>その他の情報

- 自動メールが無効になっている場合でも、Skype for Business 管理センターを使用して、会議 ID と電話番号を含むメールの送信を手動でトリガーできます。 ただし、この操作を行った場合、PIN は含まれません。 電話会議の PIN をリセットし、メールの送信が無効になっている場合は、別の方法でユーザーに送信する必要があります。
    
- ユーザーへのメールの送信は、Skype for Business 管理センターまたは組織のアカウントを使用してWindows PowerShell。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- これらのコマンドレットを使用すると、時間を節約したり、自動化することができます。
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理し、複数のタスクを実行する必要があるときに日常業務を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Microsoft 365 または Office 365 を他のユーザーとWindows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShellは、多くのユーザーに対して一度に設定変更を行う場合など、Microsoft 365 管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連項目

[ユーザーの電話会議の設定が変更された場合にユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)