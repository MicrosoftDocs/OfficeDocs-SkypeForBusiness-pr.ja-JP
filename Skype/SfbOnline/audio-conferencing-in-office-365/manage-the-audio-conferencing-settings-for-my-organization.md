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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ユーザーおよびその他のダイヤルイン会議の設定にダイヤルイン会議のライセンスおよび会議 ID を割り当てる手順についてはオンライン ビジネスの Skype を参照してください。 '
ms.openlocfilehash: ed5d2cb2115c47ba84dd91ebc45561aa93e4c023
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229361"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Skype for Business Online で組織の電話会議の設定を管理する

> [!NOTE]
> Teams でこれらの設定を管理する場合は、[Microsoft Teams で組織の電話会議の設定を管理する](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) を参照してください。

簡単に、すべて 1 か所でビジネス用の Skype のオーディオ会議設定の表示がある場合があります。


## <a name="assign-an-audio-conferencing-license"></a>オーディオ会議のライセンスを割り当てる

> [!NOTE]
> You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **ユーザーのライセンスを割り当てるには**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. 次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。****

    > [!NOTE]
    > If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. 操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。

4. On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> ユーザーに会議 ID を割り当てる

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>有効にするか、オーディオ会議のユーザーに送信された電子メールを無効にします。

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. On the **Microsoft bridge settings** page, check or uncheck the  > .********

3. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。****

4. ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。会議 ID と電話会議用の既定の電話番号は会議出席依頼に記載されていますが、PIN は記載されていません。

    ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。

    [電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md) を参照してください。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**

- Windows PowerShell を使用する

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Windows PowerShell を使用して、次を実行することもできます。[](https://go.microsoft.com/fwlink/?LinkId=627285)

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>You can also use the Windows PowerShell and run:

ユーザーに送信されるメール メッセージの、差出人の連絡先情報を変更する[](https://go.microsoft.com/fwlink/?LinkId=627285)

- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.

- メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。__

- メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。____

If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.

```
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

「ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する」を参照してください。

会議 ID をリセットする[](https://go.microsoft.com/fwlink/?LinkId=627285)

職場または学校のアカウントを使用して、Office 365 にサインインします。[](emails-sent-to-users-when-their-settings-change.md)

## <a name="reset-the-meeting-conference-id"></a>Sign in to Office 365 with your work or school account.

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. In the Skype for Business admin centerDial-in conferencing, in the Action page under Conference ID click Reset.**** > ****

3. In the ** Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.************

4. In the ** Reset conference ID?** window, click **Yes**.****

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers.[](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)[](https://go.microsoft.com/fwlink/?LinkID=626047)[](https://www.microsoft.com/en-us/download/details.aspx?id=54079)

[ユーザーの会議 ID のリセット](reset-a-conference-id-for-a-user.md)を参照してください。

## <a name="reset-a-conference-organizers-pin"></a>会議開催者の PIN をリセットする

Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Sign in to Office 365 with your work or school account.**** > ********

3. 管理者は、ユーザーに PIN を手動で送信する必要があります。****

4. PIN をリセットした後、PIN が表示されるのは 1 回だけです。********

リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "*****" が表示されます。

[オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin.md)を参照してください。

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>オーディオ会議の情報を使用して電子メールをユーザーに送信します。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Sign in to Office 365 with your work or school account.**** > ********

3. Go to the Office 365 admin centerSkype for Business and in the left navigation click Dial-in conferencing****

4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。

    > [!NOTE]
    > この操作を行っても、電話会議の PIN はユーザーに送信されません。

[電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md) を参照してください。

## <a name="setting-the-phone-numbers-included-on-invites"></a>携帯電話への招待に含まれている番号を設定します。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Sign in to Office 365 with your work or school account.**** > ****

3. In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.

4. [操作] ウィンドウで、[**有料番号**] を、また許可されている場合は [**無料番号**] も設定することができます。

5. **[保存]** をクリックします。

[携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。


## <a name="choosing-audio-conferencing-bridge-settings"></a>オーディオ会議ブリッジの設定を選択します。

**呼び出し元がミーティングに参加するときは、会議の経験を設定します。**


1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Sign in to Office 365 with your work or school account.**** > ****

3. Go to the **Office 365 admin center****** > .****

4. In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.****

   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.

     ユーザーがビジネス アプリケーションに、Skype を使用して会議に参加し、Skype ミーティングの**オプション**] メニューの [会議の**アナウンスの人を入力するかのままにするとき**の設定を変更するときに会議ごとの単位で設定できます。

   - 「**電話会議ブリッジの設定を変更する**」をご覧ください。

5. Sign in to Office 365 with your work or school account.****
    
Go to the Office 365 admin centerSkype for Business.[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Sign in to Office 365 with your work or school account.**** > ****

3. 既定値は 5 です。******** > ****

4. The PIN can only be from 4 to 12 digits. The default is 5.************

    The PIN can only be from 4 to 12 digits.
    
職場または学校のアカウントを使用して、Office 365 にサインインします。[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Sign in to Office 365 with your work or school account.**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. On the **Microsoft bridge settings** page, check or uncheck the  > .********

3. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。****

4. 電話会議の設定を使用してユーザーにメールを送信することもできます。****

    これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。

    この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。

    [電話会議の情報が記載されたメールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md) を参照してください。

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>参照してくださいし、オーディオ会議ブリッジに (既定値) をプライマリとセカンダリ (代替) の言語を設定します。


1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. Sign in to Office 365 with your work or school account.**** > ****

3. Go to the **Office 365 admin center********Skype for Business**.

4. リストから電話番号を選択し、操作ウィンドウで [ **言語を設定**] をクリックしてから、[ **言語を設定**] ページで [ **第 1 言語**] リストをクリックして、サポートされている言語の完全なリストを表示します。

    Microsoft を電話会議プロバイダーとして選ぶときに、サポートされる第 1 言語と第 2 言語を設定することもできます。発信者に対する言語の表示順は、リストで言語を選んだ順序になります。

You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.[](set-auto-attendant-languages-for-audio-conferencing.md)

## <a name="see-audio-conferencing-dial-in-numbers"></a>You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. 「電話会議のダイヤルイン番号」をご覧ください**** > ****

3. 職場または学校のアカウントを使用して、Office 365 にサインインします。******** > ****

   - 電話会議で使うために Office 365 によって設定された電話番号を表示する。

   - 場所を表示したり、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示したりする。

   - ユーザーが電話会議で有効になっているときに、ユーザーに渡される既定の電話番号を選択します。ただし、電話会議ブリッジの既定の電話番号が変わっても、既存のユーザーの既定の電話番号は変わりません。

You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing. However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.**** > ****

You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.[](see-a-list-of-audio-conferencing-numbers.md)

## <a name="see-a-list-of-users-that-are-enabled"></a>However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。

2. 有効になっているユーザーのリストを表示する**** > ****

3. 職場または学校のアカウントを使用して、Office 365 にサインインします。************

Sign in to Office 365 with your work or school account.[](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

In the Skype for Business admin center, in the left navigation go to Dial-in conferencing> and then Dial-in users.

Windows PowerShell を使用して組織レベルで管理できる複数の設定があります。[](https://go.microsoft.com/fwlink/?LinkId=627324)

このため、簡単にこれらの設定をすべてのユーザーに適用できます。

- **組織レベルの設定を以下に示します。**__
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **There are several settings that you can manage settings at the organization level using Windows PowerShell. This makes it easy to make these settings and have them apply to all of your users. Here are the organization level settings:**__
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **There are several settings that you can manage settings at the organization level using Windows PowerShell.**
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **This makes it easy to make these settings and have them apply to all of your users.**__
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Here are the organization level settings:**__
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。**__
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。**__
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。**__
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell を使い始めるには、次のトピックを参照してください。
- Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)

- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。

  - [Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)

    Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)

## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[ユーザーの電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-a-user.md)


