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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信します。
ms.openlocfilehash: 7b32608eae4fa5bb0d7f5b1eafbf49825ee937ad
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849977"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信する

> [!Note]
> Microsoft Teams でユーザーに電話会議情報を送信する方法については、「[電話会議の情報が記載されたメールをユーザーに送信する](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)」をご覧ください。

Skype for Business ユーザーに電話会議情報を送付しなくてはならない場合があります。 そのような場合は、**Skype for Business 管理センター**で、ユーザーのプロパティの **[電話会議情報をメールで送信]** をクリックします。 送信する電子メールには、次のような電話会議情報がすべて含まれています。
  
- ユーザー用の会議の電話番号またはダイヤルイン電話番号。
    
- ユーザーの会議 ID。
    
   
以下は送信される電子メールの例です。
  
![ダイヤルイン会議の電子メール](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議の情報が記載された電子メールをユーザーに送信する

1. 左側のナビゲーションで、**[ユーザー]** をクリックして、出席可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2.  **[Office 365 管理センター]**  > **[Skype for Business]** と選び、左側のナビゲーションで [**電話会議**] をクリックします。
    
3. [**ユーザー**] をクリックし、ユーザーを選択します。
    
4. 操作ウィンドウで、[**電話会議情報をメールで送信**] をクリックします。
    
> [!TIP]
> ユーザーのプロパティを編集し、[**電話会議**]  >  「**電話会議情報をメールで送信**」とクリックして、電話会議の設定が記載された電子メールをユーザーに送信することもできます。 

## <a name="what-else-should-you-know-about-this-email"></a>電子メールについてのその他の必須情報

- 組織のユーザーが電話会議を使用できるようになると、以下のような場合に電子メールが送信されます。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - ユーザーの電話会議の PIN を手動でリセットした場合。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - **電話会議** のライセンスがユーザーから削除された場合。
    
  - ユーザーの電話会議プロバイダが Microsoft から別のプロバイダ、または [**なし**] に変更された場合。
    
  - ユーザーの電話会議プロバイダが Microsoft に変更された場合。
    
- 既定では、メールの差出人は Office 365 ですが、Windows PowerShell と [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) コマンドレットを使って、メール アドレスと表示名を変更することができます。 ユーザーへの電子メールの送信元となるメール アドレスに変更を加えるには、以下を実行しなくてはなりません。
    
  - SendEmailFromAddress パラメータにメール アドレスを入力します。
    
  - SendEmailOverride パラメータを True に設定します。
    
  - SendEmailFromDisplayName パラメーターにメールの表示名を入力する
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > メール アドレス情報を変更する場合、設定した独自のメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されることを確認する必要があります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
    ユーザーに電話会議情報が記載されたメールを送信するには、次のコマンドを実行します。
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理する](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Lync Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>関連トピック

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
