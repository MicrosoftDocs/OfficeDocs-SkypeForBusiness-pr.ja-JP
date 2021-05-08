---
title: Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信します。
ms.openlocfilehash: 4f4590fcfb9233d7ad2d58358de08db58d014ecc
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237033"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Skype for Business Online で電話会議情報をユーザーに送信する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Microsoft Teams でユーザーに電話会議情報を送信する方法については、「[電話会議の情報が記載されたメールをユーザーに送信する](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)」をご覧ください。

Skype for Business ユーザーに電話会議情報を送付しなくてはならない場合があります。 この操作を行うには、Skype for Business **管理** センターを使用し、ユーザーのプロパティの下にある [電子メールで電話会議情報を送信] をクリックします。 このメールを送信すると、次を含むすべての電話会議情報が含まれる。
  
- ユーザー用の会議の電話番号またはダイヤルイン電話番号。
    
- ユーザーの会議 ID。
    
   
送信されるメールの例を次に示します。
  
![ダイヤルイン会議のメール](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議情報を含むメールをユーザーに送信する

1. 左側のナビゲーションで、[**ユーザー**] をクリックしてから、空いているユーザーのリストからユーザーを選択します。

2. ページの上部にある [編集] を **クリックします**。

3. [**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。

1. 仕事用または学校用のアカウントでサインインします。
    
2. 管理センターに移動> Skype for Business **し、** 左側のナビゲーションで [電話会議]**をクリックします**。
    
3. [ **ユーザー]** をクリックし、ユーザーを選択します。
    
4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。
    
> [!TIP]
> ユーザーのプロパティを編集し、[電話会議] をクリックして電話会議の設定を使用して、ユーザーにメールを送信することもできます  >  。 

## <a name="what-else-should-you-know-about-this-email"></a>このようなメールについて知っておくべきその他のこと

- 電話会議を有効にした後、組織内のユーザーに送信されるメールは複数あります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - ユーザーの電話会議 PIN を手動でリセットする場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - **電話会議** のライセンスがユーザーから削除された場合。
    
  - ユーザーの電話会議プロバイダーが Microsoft から別のプロバイダーまたはなし に変更 **された場合**。
    
  - ユーザーの電話会議プロバイダーが Microsoft に変更された場合。
    
- 既定では、メールの送信者は Microsoft 365 または Office 365 から送信されますが、Windows PowerShell コマンドレットと[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)コマンドレットを使用して、メール アドレスと表示名を変更できます。 メールをユーザーに送信するメール アドレスを変更するには、次の条件を実行する必要があります。
    
  - SendEmailFromAddress パラメーターに電子メール アドレスを入力します。
    
  - メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。
    
  - SendEmailFromDisplayName パラメーターに電子メールの表示名を入力します。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > メール アドレス情報を変更する場合、設定した独自のメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されることを確認する必要があります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell での管理方法について

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) コマンドレットを使用できます。
    
    ユーザーに電話会議情報を含むメールを送信するには、次のコマンドを実行します。
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。 このWindows PowerShell、1 つの管理Microsoft 365またはOffice 365を管理し、複数のタスクを実行する場合に毎日の作業を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。
    
  - [PowerShell で使用する必要があるMicrosoft 365またはOffice 365理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [アプリを使用してMicrosoft 365またはOffice 365を管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell多くのユーザーに対して一度に設定を変更する場合など、Microsoft 365 管理センターのみを使用する場合に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[電話会議を試用または購入するには、Microsoft 365またはOffice 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
