---
title: 組織の電話会議の設定を管理する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: db355e71ff90a43c46900ad2b95b9e8593a9094d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>組織の電話会議の設定を管理する

[] 1 つの場所で Skype for Business と Microsoft Teams のすべての電話会議設定を確認することが、より簡単になります。 
  
## <a name="assign-an-audio-conferencing-license"></a>電話会議のライセンスを割り当てる

> [!NOTE]
> You can't assign licenses using the **Skype for Business admin center**, you must use the Office 365 admin center. 
  
 最大 20 人までのライセンスを同時に割り当てている場合は、[ **ビューの選択**] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。次に [ 編集]、[ 次へ] を 2 回クリックし、ライセンスを選択して、[ 送信] をクリックします。また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。操作手順と PowerShell のサンプル スクリプトについては、「Skype for Business と Microsoft Teams のライセンスを割り当てる」をご覧ください。
  
1. 最大 20 人までのライセンスを同時に割り当てている場合は、[ ビューの選択] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。
    
2. 次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。
    
    > [!NOTE]
    > また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。 
  
3. ライセンスの詳細については、「**Skype for Business と Microsoft Teams のアドオン ライセンス**」をご覧ください。 
    
4. ライセンスを割り当てると、電話会議プロバイダーのリストに Microsoft が表示されなくなることがあります。この場合は、Office 365 管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーのウィンドウを更新します。
    
> [!NOTE]
> ユーザーに会議 ID を割り当てる 
  
## <a name="assign-a-conference-id-for-a-user"></a>割り当てられた 会議 ID は、静的または動的 ID で、会議がスケジュール設定されると会議出席依頼で送信されます。

A conference ID is automatically assigned to a user when they are set up for dial-in conferencing using Microsoft as the dial-in conferencing provider. 会議がスケジュールされているとき、会議出席依頼に会議 ID が送信されます。 ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得
  
Skype for Business 管理センターにおいて、または Windows PowerShell を使用して、この情報を変更することはできません。
  
A conference ID must contain 7 digits and you can't change it in the Skype for Business admin center or using Windows PowerShell.
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> See Set-CsOnlineDialInConferencingUser to learn more about the cmdlet. 
  
After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and LyncSkype for Business Online, Meeting Migration Tool (64-bit)Skype for Business Online, Meeting Migration Tool (32-bit)
  
> [!IMPORTANT]
>  After a new conference ID is created, the old conference ID can't be used by callers.
  
[](see-change-and-reset-a-conference-id-assigned-to-a-user.md)職場または学校のアカウントを使用して、Office 365 にサインインします。
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a>Sign in to Office 365 with your work or school account.

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. In the Skype for Business admin center, in the left navigation go to Dial-in conferencingDial-in users and then and select the user you want to change the dial-in conferencing provider for.
    
3. In the Action pane, click **Edit**.
    
4. In the Skype for Business admin center, in the left navigation go to Dial-in conferencing > Provider name drop-down, and then select the dial-in conferencing provider for the user. 
    
5. [ **保存**] をクリックします。
    
    > [!NOTE]
    > 「 **ユーザーのダイヤルイン会議プロバイダーを変更する**」をご覧ください。
  
6. 電話会議ユーザーへのメール送信を有効または無効にする 
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Skype for Business 管理センターまたは Windows PowerShell を使用すると、ユーザーへのメール送信を有効または無効にすることができます。

![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウで、有効または、**ユーザーのダイヤルインの設定を変更する場合に e メールを自動的に送信**を無効にします。

4. [ **保存**] をクリックします。

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. On the **Microsoft bridge settings** page, check or uncheck the  > .
    
3. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。
    
4. ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。会議 ID と電話会議用の既定の電話番号は会議出席依頼に記載されていますが、PIN は記載されていません。
    
    ユーザーの電話会議プロパティに移動し、[ **電話会議情報をメールで送信**] をクリックすると、電話会議の設定が含まれるメールをユーザーに送信することもできます。
    
    You can also send emails to the user with the dial-in conferencing settings, by going to the user's properties > Dial-in conferencingSend conference info via email.
    
 The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.
  
- Windows PowerShell を使用する 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    [](https://go.microsoft.com/fwlink/?LinkId=627285)Windows PowerShell を使用して、次を実行することもできます。
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>You can also use the Windows PowerShell and run:

ユーザーに送信されるメール メッセージの、差出人の連絡先情報を変更する
  
- Enter the email display name in the  _SendEmailFromDisplayName_ parameter.
    
- メールの差出人のメール アドレスやメールの表示名など、ユーザーに送信したメールの内容を変更するには、次のコマンドを実行します。
    
- メール アドレス情報を変更したい場合は、カスタムのメール アドレスから送信されるメールが、組織の受信メール ポリシーで許可されていることを確認する必要があります。
    
If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

「ダイヤルイン会議の設定が変更されたユーザーにメールを自動的に送信する」を参照してください。
  
会議 ID をリセットする
  
[](emails-sent-to-users-when-their-settings-change.md)職場または学校のアカウントを使用して、Office 365 にサインインします。
  
## <a name="reset-the-meeting-conference-id"></a>Sign in to Office 365 with your work or school account.

![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**オーディオ会議**、**会議 ID のリセット**をクリックします。  

4. **会議 ID をリセットしますか?** ] ウィンドウで、[**リセット**] をクリックします。 It's enabled by default. After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and LyncSkype for Business Online, Meeting Migration Tool (64-bit)Skype for Business Online, Meeting Migration Tool (32-bit)

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**  

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. In the Skype for Business admin centerDial-in conferencing, in the Action page under Conference ID click Reset.
    
3. In the ** Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.
    
4. In the ** Reset conference ID?** window, click **Yes**.
    
    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers.
  
[](reset-a-conference-id-for-a-user.md)Reset a conference organizer's PIN
  
## <a name="reset-a-conference-organizers-pin"></a>静的会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合や、ユーザーが会議 ID を覚えられない、または紛失してしまう場合があります。Skype for Business 管理センターおよび Windows PowerShell を使用すると、ユーザーの会議 ID を表示、変更、リセットすることができます。

ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得 会議 ID が自動的に作成され、ユーザーに割り当てられているがあります、ユーザーは、この 1 つを使用する場合は、特定の数に設定するとユーザーが覚えられないか、会議 ID が失われています。 ユーザーが電話会議で有効になるか、PIN がリセットされた場合、ユーザーは自分の PIN が含まれるメールを受信します。ただし、メールの自動送信を無効にしても、PIN リセットのメールは送信されません。管理者は、ユーザーに PIN を手動で送信する必要があります。PIN をリセットした後、PIN が表示されるのは 1 回だけです。リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "*****" が表示されます。

![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. **オーディオ会議**では、[ **PIN のリセット**] をクリックし、[**リセット**] をクリックします。 
  
![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。** 

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Sign in to Office 365 with your work or school account.
    
3. 管理者は、ユーザーに PIN を手動で送信する必要があります。
    
4. PIN をリセットした後、PIN が表示されるのは 1 回だけです。
    
リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "*****" が表示されます。 
  
[オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin.md)を参照してください。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議の情報が記載されたメールをユーザーに送信する

![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**オーディオ会議****電子メールで会議の情報を送信**をクリックします。 

    > [!NOTE]
    > この操作を行っても、電話会議の PIN はユーザーに送信されません。 

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**  

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Sign in to Office 365 with your work or school account.
    
3. Go to the Office 365 admin centerSkype for Business and in the left navigation click Dial-in conferencing
    
4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。
    
    > [!NOTE]
    > この操作を行っても、電話会議の PIN はユーザーに送信されません。 
  
When you do this, the dial-in conferencing PIN isn't sent to the user.
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>会議開催者に対して電話会議用の既定の電話番号を設定する

 **** Setting the default dial-in conferencing phone number for meeting organizers
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Sign in to Office 365 with your work or school account.
    
3. Go to the **Office 365 admin center** > **Skype for Business**.
    
4. Select the user that you want to enable for dial-in conferencing.
    
5. In the Action pane, in the user's properties click **Edit**.
    
  - 電話会議プロバイダーに Microsoft を選ぶ場合は、電話会議の既定の電話番号を一覧から選ぶことができます。  
    
  - 電話会議プロバイダーにサードパーティーの ACP を選ぶ場合は、有料の電話番号 (または必要に応じてフリーダイヤルの電話番号) を手動で入力する必要があります。これらの電話番号は、既定の電話番号に設定されます。
    
    ユーザーの電話会議用の既定の電話番号は、ユーザーが会議をスケジュールしたときに会議出席依頼に表示される番号です。
    
6. The default dial-in conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting. 
    
「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」をご覧ください。
  
 **電話会議のユーザーを有効にした後に、会議開催者に対して電話会議用の既定の電話番号を設定するには**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Sign in to Office 365 with your work or school account.
    
3. Go to the **Office 365 admin center****** > .
    
4. In the Skype for Business admin center, in the left navigation go to Dial-in conferencingDial-in users, select the user you want and in the Action page, click Edit.
    
  - ユーザーが電話会議プロバイダーとして Microsoft を使用する場合は、電話会議の既定の電話番号を一覧から選ぶことができます。  
    
  - 電話会議プロバイダーにサードパーティーの ACP を使う場合は、有料の電話番号 (または必要に応じてフリーダイヤルの電話番号) を手動で入力する必要があります。
    
    ユーザーの電話会議用の既定の電話番号は、ユーザーが会議をスケジュールしたときに会議出席依頼に表示される番号です。
    
5. The default dial-in conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting. 
    
「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites.md)」をご覧ください。
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>オーディオ会議ブリッジの設定を選択します。

**** Setting dial-in conferencing bridge settings

 ![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウを有効にするまたは**ミーティングのエントリと終了の通知**を無効にします。

    これは既定で有効になります。 このオプションを無効にした場合データを入力したり、会議を離れるときに既定では、会議に参加しているユーザーが通知されません。

4. **開始/終了のお知らせの種類**、[**トーン**] または [**名前または電話番号**を選択します。 

    **名前や電話番号**を選択する場合を有効にするまたは、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**を無効にすることもできます。 

1. [ **保存**] をクリックします。

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。** 
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Sign in to Office 365 with your work or school account.
    
3. Go to the **Office 365 admin center****** > .
    
4. In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.
    
  - **Enable meeting entry and exit notifications to be turned on** This is selected by default. However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.
    
    変更したら [ **保存**] をクリックします。
    
  - 「**電話会議ブリッジの設定を変更する**」をご覧ください。
    
5. Sign in to Office 365 with your work or school account.
    
Go to the Office 365 admin centerSkype for Business.
  
 In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.

 ![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウで、 **PIN の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁の番号を入力し、し、[**保存**] をクリックします。

    The PIN can only be from 4 to 12 digits.

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。** 
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Sign in to Office 365 with your work or school account.
    
3. 既定値は 5 です。
    
4. The PIN can only be from 4 to 12 digits. The default is 5.
    
    The PIN can only be from 4 to 12 digits.
    
[](change-the-settings-for-an-audio-conferencing-bridge.md)職場または学校のアカウントを使用して、Office 365 にサインインします。
  
 Sign in to Office 365 with your work or school account.

 ![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウを有効にするか**、オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**を無効にします。

4. [ **保存**] をクリックします。 
 
    ユーザーのオーディオ会議のプロパティに移動し、**電子メールで会議の情報を送信**] をクリックしてユーザーに、電話会議の設定を使用する電子メールを送信することも。
    
    この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。** 
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. On the **Microsoft bridge settings** page, check or uncheck the  > .
    
3. 電話会議の設定を使用してユーザーにメールを送信することもできます。これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。
    
4. 電話会議の設定を使用してユーザーにメールを送信することもできます。
    
    これには、ユーザーの電話会議プロパティに移動して、[ **電話会議情報をメールで送信**] をクリックします。
    
    この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。
    
    If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>参照してくださいし、オーディオ会議ブリッジに (既定値) をプライマリとセカンダリ (代替) の言語を設定します。

 ![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. リストから電話番号を選択し、[**編集**] をクリックします。

3. [**既定の言語**および **(省略可能) 別の言語**の言語を選択してください。

![デバイスのロゴ-30x30.png](../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。** 

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Sign in to Office 365 with your work or school account.
    
3. Go to the **Office 365 admin center********Skype for Business**.
    
4. リストから電話番号を選択し、操作ウィンドウで [ **言語を設定**] をクリックしてから、[ **言語を設定**] ページで [ **第 1 言語**] リストをクリックして、サポートされている言語の完全なリストを表示します。
    
    Microsoft を電話会議プロバイダーとして選ぶときに、サポートされる第 1 言語と第 2 言語を設定することもできます。発信者に対する言語の表示順は、リストで言語を選んだ順序になります。
    
You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--see-audio-conferencing-dial-in-numbers"></a>![デバイス ・ ロゴ ・ 30x30.png](../images/sfb-logo-30x30.png)  You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.

1. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.
    
2. 「電話会議のダイヤルイン番号」をご覧ください
    
3. **** 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
  - 電話会議で使うために Office 365 によって設定された電話番号を表示する。 
    
  - 場所を表示したり、電話会議の自動応答で使用する第 1 言語と第 2 言語を表示したりする。
    
  - ユーザーが電話会議で有効になっているときに、ユーザーに渡される既定の電話番号を選択します。ただし、電話会議ブリッジの既定の電話番号が変わっても、既存のユーザーの既定の電話番号は変わりません。
    
You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing. However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.
  
You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![デバイス ・ ロゴ ・ 30x30.png](../images/sfb-logo-30x30.png) However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.

1. You can go to Dial-in conferencingDial-in users and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.
    
2. 有効になっているユーザーのリストを表示する
    
3. **** 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
Sign in to Office 365 with your work or school account.
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

In the Skype for Business admin center, in the left navigation go to Dial-in conferencing> and then Dial-in users. 
    
[](https://go.microsoft.com/fwlink/?LinkId=627324)Windows PowerShell を使用して組織レベルで管理できる複数の設定があります。

このため、簡単にこれらの設定をすべてのユーザーに適用できます。 
> 
- 組織レベルの設定を以下に示します。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- There are several settings that you can manage settings at the organization level using Windows PowerShell. This makes it easy to make these settings and have them apply to all of your users. Here are the organization level settings:
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- There are several settings that you can manage settings at the organization level using Windows PowerShell.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- This makes it easy to make these settings and have them apply to all of your users.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- Here are the organization level settings:
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- Windows PowerShell の場合、ユーザーの管理と、ユーザーに許可する操作や許可しない操作の管理に使います。 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell を使い始めるには、次のトピックを参照してください。   
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 
    
  - Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time.
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)
    
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

See also


