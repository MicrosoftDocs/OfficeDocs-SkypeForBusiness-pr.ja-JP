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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Skype for Business Online で電話会議情報を記載した電子メールをユーザーに送信します。
ms.openlocfilehash: cd6c40594c32faa2f8f7d7dc3737b61cb5d2cd82
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890603"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>ビジネス オンラインの Skype で電話会議情報を持つユーザーに電子メールを送信します。

> [!Note]
> Microsoft Teams でユーザーに電話会議情報を送信する方法については、「[電話会議の情報が記載されたメールをユーザーに送信する](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)」をご覧ください。

Skype for Business ユーザーに電話会議情報を送付しなくてはならない場合があります。 **Skype**を使用してクリックして**電子メールを使用して会議情報を送信する**ユーザーのプロパティ] の下で、これを行うことができます。 この電子メールを送信するとき、すべてが含まれますのオーディオ会議の情報を含みます。
  
- ユーザー用の会議の電話番号またはダイヤルイン電話番号。
    
- ユーザーの会議 ID。
    
   
送信されるメールの例を以下に示します。
  
![ダイヤルイン会議のメール](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>オーディオ会議の情報を使用して電子メールをユーザーに送信します。

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**では、左側のナビゲーションで [**電話会議**] をクリックします。
    
3. **ユーザー**] をクリックし、ユーザーを選択します。
    
4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。
    
> [!TIP]
> 送信することも電子メール ユーザーに電話会議の設定を使用してユーザーのプロパティを編集し、[**電話会議**] をクリックして > **メールでの会議の情報を送信**します。 

## <a name="what-else-should-you-know-about-this-email"></a>このようなメールについて知っておくべきその他のこと

- 送信される、組織内のユーザーを有効にした後には、オーディオ会議のいくつかの電子メールがあります。
    
  - **電話会議** のライセンスがユーザーに割り当てられた場合。
    
  - リセットすると手動で電話会議のユーザーの暗証番号 (pin) です。
    
  - ユーザーの会議 ID を手動でリセットした場合。
    
  - **電話会議** のライセンスがユーザーから削除された場合。
    
  - オーディオ会議プロバイダーのユーザーの変更されたとき Microsoft から別のプロバイダーまたは **[なし]** にします。
    
  - マイクロソフトにユーザーの電話会議プロバイダーが変更されたとき。
    
- 既定では、電子メールの送信者は、Office 365 からされますが、メール アドレスの変更し、Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983)コマンドレットを使用して名前を表示できます。 ユーザーに電子メールを送信する電子メール アドレスを変更するには、次の操作を行う必要があります。
    
  - Enter the email display name in the  SendEmailFromDisplayName parameter.
    
  - メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。
    
  - SendEmailFromDisplayName パラメーターでは、電子メールの表示名を入力します。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > メール アドレス情報を変更する場合、設定した独自のメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されることを確認する必要があります。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) コマンドレットを使用できます。
    
    音声会議情報を使用してユーザーに電子メールを送信するのには、次の手順を実行します。
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Lync Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[Office 365 での電話会議を使用または購入する](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
