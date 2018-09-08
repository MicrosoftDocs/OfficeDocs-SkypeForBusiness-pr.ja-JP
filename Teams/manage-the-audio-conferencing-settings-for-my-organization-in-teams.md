---
title: マイクロソフトのチームで、組織内でのオーディオ会議設定を管理します。
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'ユーザーおよびその他のダイヤルイン会議の設定に、ダイヤルイン会議のライセンスおよび会議 ID を割り当てるには、マイクロソフトのチームの手順を参照してください。 '
ms.openlocfilehash: 7af89da74b0b83872954444a847d40f0d7851087
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884706"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>マイクロソフトのチームで、組織内でのオーディオ会議設定を管理します。

マイクロソフト チームの 1 つの場所で電話会議の設定をすべて表示することが容易になりますがある場合があります。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>電話会議のライセンスを割り当てる

> [!NOTE]
> チームを使用してライセンスを割り当てることはできません。 職場または学校のアカウントを使用して、Office 365 にサインインします。 In the left navigation of the Office 365 admin center, go to UsersActive users > and then select the user or users from the list of available users. 
  
 最大 20 人までのライセンスを同時に割り当てている場合は、[ ビューの選択] ボックスを使用していずれかのオプションを選択するか、独自のビューを作成することができます。次に [ 編集]、[ 次へ] を 2 回クリックし、ライセンスを選択して、[ 送信] をクリックします。また、Windows Powershell を使用してライセンスを複数のユーザーに割り当てることもできます。操作手順と PowerShell のサンプル スクリプトについては、「Skype for Business と Microsoft Teams のライセンスを割り当てる」をご覧ください。
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. 次に [ **編集**]、[ **次へ**] を 2 回クリックし、ライセンスを選択して、[  > ] をクリックします。****
    
    > [!NOTE]
    > 操作手順と PowerShell のサンプル スクリプトについては、「**Skype for Business と Microsoft Teams のライセンスを割り当てる**」をご覧ください。 操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。****  
  
3. ライセンスの詳細については、「**Skype for Business と Microsoft Teams のアドオン ライセンス**」をご覧ください。 
    
4. ライセンスを割り当てると、電話会議プロバイダーのリストに Microsoft が表示されなくなることがあります。この場合は、Office 365 管理センターからログアウトするか、CTRL キーを押しながら F5 キーを押してブラウザーのウィンドウを更新します。
    
> [!NOTE]
> ユーザーに会議 ID を割り当てる 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Skype for Business 管理センターまたは Windows PowerShell を使用すると、ユーザーへのメール送信を有効または無効にすることができます。

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウで、有効または、**ユーザーのダイヤルインの設定を変更する場合に e メールを自動的に送信**を無効にします。

4. [ **保存**] をクリックします。

    
**The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.**
  
詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>You can also use the Windows PowerShell and run:

Change the senders contact information of email messages sent to users 既定では、Office 365 は、電子メールの送信者が電子メール アドレスを変更し、Windows PowerShell を使用して名前を表示できます。 詳細については[マイクロソフト チームの PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)を参照してください。
  
## <a name="reset-the-meeting-conference-id"></a>Sign in to Office 365 with your work or school account.

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**オーディオ会議**、**会議 ID のリセット**をクリックします。  

4. **会議 ID をリセットしますか?** ] ウィンドウで、[**リセット**] をクリックします。 It's enabled by default. After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and LyncSkype for Business Online, Meeting Migration Tool (64-bit)Skype for Business Online, Meeting Migration Tool (32-bit)

[](reset-a-conference-id-for-a-user-in-teams.md)Reset a conference organizer's PIN
  
## <a name="reset-a-conference-organizers-pin"></a>静的会議 ID は自動的に作成されユーザーに割り当てられますが、ユーザーがそれを使いたくないため特定の番号に設定しようと考える場合や、ユーザーが会議 ID を覚えられない、または紛失してしまう場合があります。Skype for Business 管理センターおよび Windows PowerShell を使用すると、ユーザーの会議 ID を表示、変更、リセットすることができます。

ユーザーをスケジュールする会議ごとに固有の会議 ID が割り当てられますを取得 会議 ID が自動的に作成され、ユーザーに割り当てられているがあります、ユーザーは、この 1 つを使用する場合は、特定の数に設定するとユーザーが覚えられないか、会議 ID が失われています。 

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. **オーディオ会議**では、[ **PIN のリセット**] をクリックし、[**リセット**] をクリックします。 
  
    
リセットの直後に 1 回表示された後は、ユーザーのプロパティには PIN に代わって "*****" が表示されます。 
  
[オーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin-in-teams.md)を参照してください。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>電話会議の情報が記載されたメールをユーザーに送信する

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. ページの上部で、[**編集**] をクリックします。

3. [**電話会議**] の [**電話会議情報をメールで送信**] をクリックします。 

    > [!NOTE]
    > この操作を行っても、電話会議の PIN はユーザーに送信されません。 

  
When you do this, the dial-in conferencing PIN isn't sent to the user.
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>携帯電話への招待に含まれている番号を設定します。

1. 左側のナビゲーションでは、**ユーザー**] をクリックしてで使用可能なユーザーの一覧からユーザーを選択します。

2. **オーディオ会議**の横にある [**編集**] をクリックします。
 
3. **オーディオ会議**のウィンドウで**電話番号**を設定でき、許可された場合、**フリー ダイヤルの番号**です。

4. The default dial-in conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.
    
「[出席依頼に含まれている会議の開催者のために電話会議の電話番号を設定する](set-the-phone-numbers-included-on-invites-in-teams.md)」をご覧ください。
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>オーディオ会議ブリッジの設定を選択します。

**** Setting dial-in conferencing bridge settings


1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウを有効にするまたは**ミーティングのエントリと終了の通知**を無効にします。

    これは既定で有効になります。 このオプションを無効にした場合データを入力したり、会議を離れるときに既定では、会議に参加しているユーザーが通知されません。

4. **開始/終了のお知らせの種類**、[**トーン**] または [**名前または電話番号**を選択します。 

    **名前や電話番号**を選択する場合を有効にするまたは、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**を無効にすることもできます。 

5. [ **保存**] をクリックします。

    
Go to the Office 365 admin centerSkype for Business.[](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.**

1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウで、 **PIN の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁の番号を入力し、し、[**保存**] をクリックします。

    The PIN can only be from 4 to 12 digits.

    
職場または学校のアカウントを使用して、Office 365 にサインインします。[](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **Sign in to Office 365 with your work or school account.**


1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウを有効にするか **、オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**を無効にします。

4. [ **保存**] をクリックします。 
 
    ユーザーのオーディオ会議のプロパティに移動し、**電子メールで会議の情報を送信**] をクリックしてユーザーに、電話会議の設定を使用する電子メールを送信することも。
    
    この操作を行うと、会議 ID と電話会議の番号のみが含まれるメールが送信されますが、そのメールに PIN は含まれません。

If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>参照してくださいし、オーディオ会議ブリッジに (既定値) をプライマリとセカンダリ (代替) の言語を設定します。

1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. リストから電話番号を選択し、[**編集**] をクリックします。

3. [**既定の言語**および **(省略可能) 別の言語**の言語を選択してください。


You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider. The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.[](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.


1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. リストから電話番号を選択し、[**編集**] をクリックします。 Go to the Office 365 admin centerSkype for Business.
    
  - 電話会議で使うために Office 365 によって設定された電話番号を表示する。 
    
  - 場所、およびオーディオ会議自動アテンダントによって使用される主言語を表示します。

  
You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.[](see-a-list-of-audio-conferencing-numbers-in-teams.md)
  

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、[マイクロソフト チームの PowerShell の参照](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)の詳細についてを参照してください。
  
    
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

See also


