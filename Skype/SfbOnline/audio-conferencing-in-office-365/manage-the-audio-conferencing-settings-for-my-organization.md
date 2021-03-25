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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'ユーザーにダイヤルイン会議ライセンスと会議 ID を割り当てる手順については、Skype for Business Online の手順と、その他の多くのダイヤルイン会議設定を参照してください。 '
ms.openlocfilehash: eb0212bcd7c03fac619efa2749a8308097f75505
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114233"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Skype for Business Online で組織の電話会議の設定を管理する

> [!NOTE]
> Teams でこれらの設定を管理する場合は、[Microsoft Teams で組織の電話会議の設定を管理する](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) を参照してください。

Skype for Business のすべての電話会議設定を 1 か所で表示する方が簡単な場合があります。


## <a name="assign-an-audio-conferencing-license"></a>電話会議のライセンスを割り当てる

> [!NOTE]
> To assign a license for a user Microsoft 365 管理センターを使用する必要があります。 「Skype [for Business ライセンスを割り当てる」を参照してください](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

 **ユーザーにライセンスを割り当てる**

1. 仕事用または学校用のアカウントでサインインします。

2. 管理センターの左側のナビゲーションで、[アクティブなユーザー ] に移動し、使用可能なユーザーの一覧からユーザー  >  を選択します。

    > [!NOTE]
    > 操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。 操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。 また、Windows PowerShell を使用して複数のユーザーにライセンスを割り当てできます。 手順とサンプルの PowerShell スクリプトについては、「Skype for Business ライセンスを割り当 [てる」を参照してください](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

3. [操作] ウィンドウの [**製品ライセンス**] で [**編集**] をクリックします。

4. [製品ライセンス **] ページで** 電話会議を **有効** にし、[保存] をクリック **します**。 ライセンスの詳細については、「Skype for Business アドオン のライセンス [」を参照してください](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

> [!NOTE]
> ライセンスを割り当てると、Microsoft が電話会議プロバイダーとして最初にリストに表示されない場合があります。 この場合は、管理センターからログアウトするか、Ctrl キーを押しながら F5 キーを押してブラウザー ウィンドウを更新します。

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>電話会議ユーザーに送信されたメールを有効または無効にする

![Skype for Business のロゴを表示したアイコン](../images/sfb-logo-30x30.png) **Skype for Business 管理センターの使用**

1. 仕事用または学校用のアカウントでサインインします。

2. **Skype for Business** の管理センター>移動し、左側のナビゲーションで [電話会議]**をクリックします**。

3. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。

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

    Windows PowerShell を使用して、次を実行することもできます。[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>You can also use the Windows PowerShell and run:

実際のメール アドレスや送信者の連絡先情報の表示名など、ユーザーに自動的に送信されるメールを変更できます。 既定では、メールの送信者は Microsoft 365 または Office 365 ですが、Windows PowerShell と [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットを使用してメール アドレスと表示名を変更できます。 ユーザーにメールを送信するメール アドレスを変更するには、次の必要があります。

- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.

- メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。

- メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。

If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

「ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する」を参照してください。

会議 ID をリセットする[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)

職場または学校のアカウントを使用して、Office 365 にサインインします。[](emails-sent-to-users-when-their-settings-change.md)

## <a name="reset-the-meeting-conference-id"></a>Sign in to Office 365 with your work or school account.

1. 仕事用または学校用のアカウントでサインインします。

2. Skype for Business の管理> **に移動します**。

3. In the ** Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

4. In the ** Reset conference ID?** window, click **Yes**.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers.[](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)[](https://go.microsoft.com/fwlink/?LinkID=626047)[](https://www.microsoft.com/download/details.aspx?id=54079)

「[ユーザーの会議通話 ID をリセットする](reset-a-conference-id-for-a-user.md)」を参照してください。

## <a name="reset-a-conference-organizers-pin"></a>会議通話の開催者の PIN をリセットする

ユーザーがスケジュール設定した各会議には、一意の会議通話 ID が割り当てられます。 会議通話 ID は自動的に作成されユーザーに割り当てられますが、ユーザーは使わないため特定の番号に設定しようと考える場合や、ユーザーが会議通話 ID を覚えられない、または紛失してしまう場合があります。 Skype for Business 管理センターを使用して、Windows PowerShell ID の表示、変更、リセットを行えます。


1. 仕事用または学校用のアカウントでサインインします。

2. **Skype for Business** の管理センター>移動し、左側のナビゲーションで [電話会議]**をクリックします**。

3. 管理者は、ユーザーに PIN を手動で送信する必要があります。

4. PIN をリセットした後、PIN が表示されるのは 1 回だけです。

リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "*****" が表示されます。

「[電話会議の PIN をリセットする](reset-the-audio-conferencing-pin.md)」を参照してください。

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議の情報が記載された電子メールをユーザーに送信する

1. 仕事用または学校用のアカウントでサインインします。

2. **Skype for Business** の管理センター>移動し、左側のナビゲーションで [電話会議]**をクリックします**。

3. Go to the Office 365 admin centerSkype for Business and in the left navigation click Dial-in conferencing

4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。

    > [!NOTE]
    > この操作を行っても、電話会議の PIN はユーザーに送信されません。

「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。

## <a name="setting-the-phone-numbers-included-on-invites"></a>招待に含まれる電話番号を設定する

1. 仕事用または学校用のアカウントでサインインします。

2. Skype for Business の管理> **に移動します**。

3. 左側のナビゲーションで、[電話会議ユーザー **] に移動**  >  **します**。 電話会議を有効にするユーザーを選択します。

4. [操作] ウィンドウで、[**有料番号**] を、また許可されている場合は [**無料番号**] も設定することができます。

5. [**保存**] をクリックします。

「[招待状に含まれている電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」を参照してください。


## <a name="choosing-audio-conferencing-bridge-settings"></a>電話会議ブリッジの設定の選択

**発信者が会議に参加するときの会議エクスペリエンスを設定する**


1. 仕事用または学校用のアカウントでサインインします。

2. Skype for Business の管理> **に移動します**。

3. Go to the **Office 365 admin center** > .

4. In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.

   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.

     これは、ユーザーが Skype for Business アプリを使用して会議に参加し、ユーザーが会議の [Skype 会議オプション] メニューの [入退出時にアナウンス] 設定を変更するときに、会議単位で設定できます。

   - 「**電話会議ブリッジの設定を変更する**」をご覧ください。

5. Sign in to Office 365 with your work or school account.
    
Go to the Office 365 admin centerSkype for Business.[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **会議の PIN の長さを設定する**

1. 仕事用または学校用のアカウントでサインインします。

2. Skype for Business の管理> **に移動します**。

3. 既定値は 5 です。 > 

4. The PIN can only be from 4 to 12 digits. The default is 5.

    The PIN can only be from 4 to 12 digits.
    
職場または学校のアカウントを使用して、Office 365 にサインインします。[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **電話会議 ユーザーに送信されているメールを有効または無効にする**

1. 仕事用または学校用のアカウントでサインインします。

2. **Skype for Business** の管理センター>移動し、左側のナビゲーションで [電話会議]**をクリックします**。

3. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。

4. 電話会議の設定を使用してユーザーにメールを送信することもできます。

    これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。

    この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。

    「[電話会議の情報が記載された電子メールをユーザーに送信する](send-an-email-to-a-user-with-their-dial-in-information.md)」を参照してください。

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>電話会議ブリッジの第 1 (既定) 言語と第 2 (代替) 言語を表示、設定する


1. 仕事用または学校用のアカウントでサインインします。

2. Skype for Business の管理> **に移動します**。

3. Go to the **Office 365 admin center****Skype for Business**.

4. リストから電話番号を選択し、操作ウィンドウで [ **言語を設定**] をクリックしてから、[ **言語を設定**] ページで [ **第 1 言語**] リストをクリックして、サポートされている言語の完全なリストを表示します。

    Microsoft を電話会議プロバイダーとして選ぶときに、サポートされる第 1 言語と第 2 言語を設定することもできます。発信者に対する言語の表示順は、リストで言語を選んだ順序になります。

You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.[](set-auto-attendant-languages-for-audio-conferencing.md)

## <a name="see-audio-conferencing-dial-in-numbers"></a>電話会議のダイヤルイン番号を確認する

1. 仕事用または学校用のアカウントでサインインします。

2. Skype for Business の管理> **に移動します**。
 
3. Skype **for Business 管理センターの** 左側のナビゲーションで、電話会議 Microsoft Bridge **に**  >  **移動します**。 ここでは、

   - 電話会議に使用する Microsoft 365 または Office 365 によって設定された電話番号を表示します。

   - 場所を表示したり、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示したりする。

   - ユーザーが電話会議で有効になっているときに、ユーザーに渡される既定の電話番号を選択します。ただし、電話会議ブリッジの既定の電話番号が変わっても、既存のユーザーの既定の電話番号は変わりません。

You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing. However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change. > 

You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.[](see-a-list-of-audio-conferencing-numbers.md)

## <a name="see-a-list-of-users-that-are-enabled"></a>However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.

1. 仕事用または学校用のアカウントでサインインします。

2. Skype for Business の管理> **に移動します**。

3. 職場または学校のアカウントを使用して、Office 365 にサインインします。

Sign in to Office 365 with your work or school account.[](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

In the Skype for Business admin center, in the left navigation go to Dial-in conferencing> and then Dial-in users.

Windows PowerShell を使用して組織レベルで管理できる複数の設定があります。[](/previous-versions//mt228132(v=technet.10))

このため、簡単にこれらの設定をすべてのユーザーに適用できます。

- **組織レベルの設定を以下に示します。**
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **There are several settings that you can manage settings at the organization level using Windows PowerShell. This makes it easy to make these settings and have them apply to all of your users. Here are the organization level settings:**
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **There are several settings that you can manage settings at the organization level using Windows PowerShell.**
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **This makes it easy to make these settings and have them apply to all of your users.**
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Here are the organization level settings:**
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。**
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。**
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。**
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell を使い始めるには、次のトピックを参照してください。
- Windows PowerShellは、ユーザーの管理と、ユーザーに許可する操作と許可しない操作の管理に使います。 Windows PowerShell を使用すると、単一の管理ポイントを使用して Microsoft 365 または Office 365 を管理し、複数のタスクを実行する必要があるときに日常業務を簡略化できます。 Windows PowerShell の使用を開始するには、次のトピックを参照してください。

  - [Microsoft 365 または Office 365 PowerShell を使用する必要がある理由](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Microsoft 365 または Office 365 を管理するための最適Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShellは、一度に多くのユーザーに設定を変更する場合など、管理センターのみを使用する場合と同様に、速度、シンプルさ、生産性に多くの利点があります。 次のトピックで、これらの利点を説明します。

  - [Windows PowerShell と Skype for Business Online の概要](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Windows PowerShell による Skype for Business Online の管理](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    Skype for Business Online 用の Windows PowerShell モジュールがあれば、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成できます。このモジュールは、64 ビット版のコンピューターでのみサポートされており、「[Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)」の Microsoft ダウンロード センターからダウンロードできます。

## <a name="related-topics"></a>関連トピック

[ユーザーの電話会議の設定を管理する](manage-the-audio-conferencing-settings-for-a-user.md)