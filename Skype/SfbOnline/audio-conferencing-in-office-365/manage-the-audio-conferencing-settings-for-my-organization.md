---
title: Skype for Business Online で組織の電話会議の設定を管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: 'ダイヤルイン会議ライセンスと会議 ID をユーザーとその他のさまざまなダイヤルイン会議設定に割り当てる方法については、「Skype for Business Online の手順」を参照してください。 '
ms.openlocfilehash: f5597ae2b857569b7890d81577e4fd4252da5106
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962705"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Skype for Business Online で組織の電話会議の設定を管理する

> [!NOTE]
> Teams でこれらの設定を管理する場合は、[Microsoft Teams で組織の電話会議の設定を管理する](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) を参照してください。

Skype for Business のすべての電話会議の設定を1か所で表示した方が簡単な場合があります。


## <a name="assign-an-audio-conferencing-license"></a>電話会議のライセンスを割り当てる

> [!NOTE]
> To assign a license for a user**** Microsoft 365 管理センターを使用する必要があります。 「 [Skype For business ライセンスの割り当て](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」を参照してください。

 **ユーザーにライセンスを割り当てる**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. 管理センターの左側のナビゲーションで、[**ユーザー** > の**アクティブな**ユーザー] に移動し、利用可能なユーザーのリストからユーザー (複数可) を選びます。

    > [!NOTE]
    > 操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。 操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。**** Windows Powershell を使用して、複数のユーザーにライセンスを割り当てることもできます。 手順とサンプル PowerShell スクリプトについては、「 [Skype For business ライセンスの割り当て](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」を参照してください。

3. [操作] ウィンドウの [**製品ライセンス**] で [**編集**] をクリックします。

4. [**製品ライセンス**] ページで、[**電話会議**] をオンにし、[**保存**] をクリックします。 ライセンスの詳細については、「 [Skype For business アドオンライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」を参照してください。

> [!NOTE]
> ライセンスを割り当てた後は、リストの最初の電話会議プロバイダーとして Microsoft が表示されない可能性があります。 この問題が発生した場合は、管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーウィンドウを更新してください。

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>電話会議ユーザーに送信されたメールを有効または無効にする

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business** > 管理センターに移動し、左側のナビゲーションで [**電話会議**] をクリックします。

3. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。****

4. ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。会議 ID と電話会議用の既定の電話番号は会議出席依頼に記載されていますが、PIN は記載されていません。

    ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。

    [電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md) を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**

- Windows PowerShell を使用する

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Windows PowerShell を使用して、次を実行することもできます。[](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>You can also use the Windows PowerShell and run:

ユーザーに送信されるメール メッセージの、差出人の連絡先情報を変更する[](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)

- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.

- メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。__

- メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。____

If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

「ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する」を参照してください。

会議 ID をリセットする[](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)

職場または学校のアカウントを使用して、Office 365 にサインインします。[](emails-sent-to-users-when-their-settings-change.md)

## <a name="reset-the-meeting-conference-id"></a>Sign in to Office 365 with your work or school account.

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business**> 管理センターに移動します。

3. In the ** Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.************

4. In the ** Reset conference ID?** window, click **Yes**.****

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers.[](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)[](https://go.microsoft.com/fwlink/?LinkID=626047)[](https://www.microsoft.com/en-us/download/details.aspx?id=54079)

「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user.md)」を参照してください。

## <a name="reset-a-conference-organizers-pin"></a>会議通話の開催者の PIN をリセットする

ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。 会議通話 ID は自動的に作成されユーザーに割り当てられますが、ユーザーは使わないため特定の番号に設定しようと考える場合や、ユーザーが会議通話 ID を覚えられない、または紛失してしまう場合があります。 Skype for Business 管理センターと Windows PowerShell を使用して、会議 ID を表示、変更、リセットすることができます。


1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business** > 管理センターに移動し、左側のナビゲーションで [**電話会議**] をクリックします。

3. 管理者は、ユーザーに PIN を手動で送信する必要があります。****

4. PIN をリセットした後、PIN が表示されるのは 1 回だけです。********

リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "*****" が表示されます。

「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin.md)」を参照してください。

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議の情報が記載された電子メールをユーザーに送信する

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business** > 管理センターに移動し、左側のナビゲーションで [**電話会議**] をクリックします。

3. Go to the Office 365 admin centerSkype for Business and in the left navigation click Dial-in conferencing****

4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。

    > [!NOTE]
    > この操作を行っても、電話会議の PIN はユーザーに送信されません。

「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。

## <a name="setting-the-phone-numbers-included-on-invites"></a>招待に含まれる電話番号の設定

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business**> 管理センターに移動します。

3. 左側のナビゲーションで、[**電話会議** > **ユーザー**] に移動します。 電話会議用に有効にするユーザーを選びます。

4. [操作] ウィンドウで、[**有料番号**] を、また許可されている場合は [**無料番号**] も設定することができます。

5. [**保存**] をクリックします。

「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」を参照してください。


## <a name="choosing-audio-conferencing-bridge-settings"></a>電話会議ブリッジの設定を選ぶ

**発信者が会議に参加するときの会議エクスペリエンスを設定する**


1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business**> 管理センターに移動します。

3. Go to the **Office 365 admin center****** > .****

4. In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.****

   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.

     これは、ユーザーが Skype for Business アプリを使用して会議に参加し、会議の [Skype 会議のオプション] メニューで [**ユーザーが入力または退席したとき**の通知 **]** を変更したときに、会議ごとに設定することができます。

   - 「**電話会議ブリッジの設定を変更する**」をご覧ください。

5. Sign in to Office 365 with your work or school account.****
    
Go to the Office 365 admin centerSkype for Business.[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **会議の PIN の長さを設定する**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business**> 管理センターに移動します。

3. 既定値は 5 です。******** > ****

4. The PIN can only be from 4 to 12 digits. The default is 5.************

    The PIN can only be from 4 to 12 digits.
    
職場または学校のアカウントを使用して、Office 365 にサインインします。[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Sign in to Office 365 with your work or school account.**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business** > 管理センターに移動し、左側のナビゲーションで [**電話会議**] をクリックします。

3. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。****

4. 電話会議の設定を使用してユーザーにメールを送信することもできます。****

    これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。

    この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。

    「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示、設定する


1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business**> 管理センターに移動します。

3. Go to the **Office 365 admin center********Skype for Business**.

4. リストから電話番号を選択し、操作ウィンドウで [ **言語を設定**] をクリックしてから、[ **言語を設定**] ページで [ **第 1 言語**] リストをクリックして、サポートされている言語の完全なリストを表示します。

    Microsoft を電話会議プロバイダーとして選ぶときに、サポートされる第 1 言語と第 2 言語を設定することもできます。発信者に対する言語の表示順は、リストで言語を選んだ順序になります。

You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.[](set-auto-attendant-languages-for-audio-conferencing.md)

## <a name="see-audio-conferencing-dial-in-numbers"></a>You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business**> 管理センターに移動します。

3. 職場または学校のアカウントを使用して、Office 365 にサインインします。******** > ****

   - 電話会議で使うために Office 365 によって設定された電話番号を表示する。

   - 場所を表示したり、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示したりする。

   - ユーザーが電話会議で有効になっているときに、ユーザーに渡される既定の電話番号を選択します。ただし、電話会議ブリッジの既定の電話番号が変わっても、既存のユーザーの既定の電話番号は変わりません。

You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing. However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.**** > ****

You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.[](see-a-list-of-audio-conferencing-numbers.md)

## <a name="see-a-list-of-users-that-are-enabled"></a>However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. **Skype For business**> 管理センターに移動します。

3. 職場または学校のアカウントを使用して、Office 365 にサインインします。************

Sign in to Office 365 with your work or school account.[](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

In the Skype for Business admin center, in the left navigation go to Dial-in conferencing> and then Dial-in users.

Windows PowerShell を使用して組織レベルで管理できる複数の設定があります。[](https://go.microsoft.com/fwlink/?LinkId=627324)

このため、簡単にこれらの設定をすべてのユーザーに適用できます。

- **組織レベルの設定を以下に示します。**__
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **There are several settings that you can manage settings at the organization level using Windows PowerShell. This makes it easy to make these settings and have them apply to all of your users. Here are the organization level settings:**__
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **There are several settings that you can manage settings at the organization level using Windows PowerShell.**
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **This makes it easy to make these settings and have them apply to all of your users.**__
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Here are the organization level settings:**__
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。**__
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。**__
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。**__
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell を使い始めるには、次のトピックを参照してください。
- Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。

  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell には、管理センターを使用する場合にのみ、速度、シンプルさ、生産性の向上という利点があります。たとえば、多くのユーザーの設定を一度に変更する場合です。 次のトピックで、これらの利点を説明します。

  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

    Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。

## <a name="related-topics"></a>関連トピック

[ユーザーの電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-a-user.md)


