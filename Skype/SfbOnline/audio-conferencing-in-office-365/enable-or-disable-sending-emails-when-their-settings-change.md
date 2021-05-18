---
title: Skype for Business Online で電話会議の設定が変更された場合にメールの送信を有効または無効にする
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
description: 'PIN の変更や既定の会議Skypeなどの設定が変更された場合に、ユーザーにメールを送信する機能を有効または無効にする方法について説明します。 '
ms.openlocfilehash: f6596e3e5c52dd82f4f61ad176ae4d656a5f146c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237323"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Skype for Business Online で電話会議の設定が変更された場合にメールの送信を有効または無効にする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Microsoft Teams でメールの送信を有効または無効にする場合は、「Microsoft Teams で電話会議の設定が変更された場合にメールの送信を有効または無効にする」[をMicrosoft Teams。](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)

電話会議が有効になると、ユーザーに電子メールで自動的に通知されます。 ただし、ユーザーに送信されるメールの数を減らしたい場合Skype for Businessがあります。 このような場合は、メールの送信を無効にできます。
  
メールの送信を無効にした場合、電話会議メールはユーザーに送信されません。たとえば、ユーザーが電話会議に対して有効または無効になっているとき、PIN がリセットされた場合、電話会議 ID と既定の会議電話番号が変更された場合のメールも含めて送信されません。
  
電話会議が有効になっているユーザーに送信されるメールの例を次に示します。
  
![電話会議の電子メール](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>メールがユーザーに送信されるのは、いつですか?

- 電話会議を有効にした後、組織内のユーザーに送信されるメールは複数あります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - ユーザーの電話会議 PIN を手動でリセットする場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - 電話会議 **ライセンスが** 削除された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたはなし に変更 **された場合**。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>メールがユーザーに送信されるのを有効または無効にする

管理者センターまたは Skype for Businessを使用してWindows PowerShellに送信されたメールを有効または無効にできます。

 
![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**
    
1. [Skype for Business **センター] の左側** のナビゲーションで、[電話会議]**をクリックします**。
    
2. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。
    
3. 電話会議の設定を使用してユーザーにメールを送信することもできます。
    
    > [!TIP]
    > [電話会議ユーザー] に移動し、ユーザーを選択し、[電子メールで電話会議情報を送信] をクリックして、電話会議の設定を使用してユーザーにメール  >  **を送信することもできます**。  この操作を行う場合、PIN ではなく、会議 ID と電話会議の電話番号のみを含むメールが送信されます。  詳細 [については、「電話会議情報を使用してユーザーに電子メールを送信する」](send-an-email-to-a-user-with-their-dial-in-information.md) を参照してください。
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Windows PowerShell を使用する**
  
- 次のコマンドを実行して、メールの送信を無効にします。 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    このコマンドレットのヘルプについては [、「Set-CsOnlineDialInConferencingTenantSettings」を参照してください](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)。
    
## <a name="what-else-should-you-know"></a>その他の情報

- 自動メールを無効にした場合でも、管理者センターの管理センターで会議 ID と電話番号を含む電子メールの送信Skype for Businessトリガーできます。 ただし、この操作を行った場合、PIN は含まれません。 電話会議 PIN をリセットし、メールの送信が無効になっている場合は、別の方法でユーザーに送信する必要があります。
    
- ユーザーにメールを送信するには、管理者センターまたは管理者Skype for Businessを使用Windows PowerShell。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- これらのコマンドレットを使用すると、時間を節約したり、自動化することができます。
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- Windows PowerShellは、ユーザーの管理と、ユーザーが許可または許可されていない操作についてすべて行います。 このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターのみを使用する場合に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連項目

[電話会議の設定が変更された場合にユーザーに送信されるメール](emails-sent-to-users-when-their-settings-change.md)

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)
