---
title: "組織内でのオーディオ会議設定を管理します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "サード パーティ製会議プロバイダー、およびその他のダイヤルイン会議の設定を設定、ユーザーにダイヤルイン会議のライセンスおよび会議 ID を割り当てる手順を参照してください。 "
ms.openlocfilehash: 6bca89f60c5ee4e9b840d2094500077cfa972902
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>組織内でのオーディオ会議設定を管理します。

容易にするすべてのビジネスおよびマイクロソフトのチームで 1 つの場所に Skype の電話会議の設定を表示する場合があります。 
  
## <a name="assign-an-audio-conferencing-license"></a>オーディオ会議のライセンスを割り当てる

> [!NOTE]
> **ビジネス管理センターの Skype**を使用してライセンスを割り当てることはできません。 Office 365 管理センターを使用する必要があります。 [ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。 
  
 **ユーザーのライセンスを割り当てるには**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**の左側のナビゲーションでは、**ユーザー**に移動 > **アクティブなユーザー**の利用可能なユーザーの一覧からユーザーまたはユーザーを選択します。
    
    > [!NOTE]
    > 場合は同時に最大 20 個のユーザーにライセンスを割り当てる場合は、**ビューを選択して**ドロップダウン リストを使用し、オプションのいずれかを選択したり、独自のビューを作成できます。 **編集**、**次へ**2 回クリックし、ライセンスを選択し、[**送信**] をクリックします。 Windows Powershell を使用して複数のユーザーにライセンスを割り当てることもできます。 手順とサンプルの PowerShell スクリプトでは、[ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。 
  
3. 操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。 
    
4. [**製品ライセンス**] ページで、**電話会議**を有効にして、[**保存**] をクリックします。 ライセンスの詳細は、 [Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。
    
> [!NOTE]
> ライセンスを割り当てると、Microsoft が最初に一覧に表示されない、オーディオ会議プロバイダーとして。 このような場合は、Office 365 の管理ページからログアウトするか、CTRL + f5 キーを押してブラウザー ウィンドウを更新します。 
  
## <a name="assign-a-conference-id-for-a-user"></a>ユーザーの会議 ID を割り当てる

会議 ID が自動的に割り当てられているユーザーに電話会議のオーディオ会議プロバイダーとして Microsoft を使用する設定している場合。 会議 ID が割り当てられている静的または動的のどちらかにすることができ、会議がスケジュールされているときに会議出席依頼の送信します。 
  
静的の Id は、組織内のユーザーはランダムな番号を覚えておく必要があるときに使用します。特定の番号を選択したり、覚えやすいものを選択することができます。 動的会議 Id を使用する場合各会議ユーザのスケジュールは割り当てられます会議の一意の id。 割り当てる静的な会議 Id ではなく動的をする場合は、[組織内のオーディオ会議を使用して動的な Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)を参照してください。
  
ビジネス管理センターの Skype は、ユーザーに会議 ID を割り当てるには使用できませんが、Windows PowerShell コマンドレットを使用してこれを行うことができます。
  
ユーザーの会議 ID を設定するのには次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> 会議 ID が 7 桁の数字を含める必要があり、ビジネス管理センターまたは Windows PowerShell を使用して、Skype で変更することはできません。 
  
コマンドレットの詳細については、[設定 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )を参照してください。
  
> [!IMPORTANT]
>  新しい会議 ID が作成されると、呼び出し元が古い会議 ID を使用できません。 ミーティングの招待新しい会議 ID が、招待状に追加されることを確認するのには、既存のスケジュールを変更するのにはユーザーに通知する必要があります。 ユーザーは、ビジネス会議の移行ツールの Skype を使用して、既存の会議を更新します。 ダウンロード、インストール、および、Skype をビジネス会議の更新ツールを実行する方法を参照してください:[ビジネスと Lync の Skype の会議の更新ツール](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype](http://go.microsoft.com/fwlink/?LinkID=626047)、および[のビジネス オンラインでは、Skype 会議移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。
  
[参照してください、変更、およびユーザーに割り当てられている会議 ID のリセット](see-change-and-reset-a-conference-id-assigned-to-a-user.md)を参照してください。
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a>マイクロソフトからサード パーティのプロバイダーに、オーディオ会議プロバイダーを変更します。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **ユーザー**、オーディオ会議プロバイダーを変更するユーザーを選択し、します。
    
4. 操作ウィンドウで、[ **編集**] をクリックします。 
    
5. [**プロパティ**] ページの [**プロバイダー名**] で、ユーザーの電話会議プロバイダーを選択します。
    
    > [!NOTE]
    > のみ、複数のユーザーを選択した場合、Microsoft をオーディオ会議プロバイダー、または**[なし]**として選択できます。
  
6. [ **保存**] をクリックします。 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>有効にするか、オーディオ会議のユーザーに送信された電子メールを無効にします。

有効にするか、ユーザーに送信される電子メールを無効にするのには、ビジネス管理センターの Skype または Windows PowerShell を使用できます。
  
 **ビジネス管理センターに、Skype を使用します。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**の左側のナビゲーションでは、[**電話会議**] をクリックします。
    
3. **Microsoft ブリッジの設定**] ページをオンまたはオフの**オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**する。
    
4. [ **保存**] をクリックします。
    
    電子メールを送信するユーザーに電話会議の設定を使用してユーザーのオーディオ会議のプロパティに移動し、**電子メールを使用して会議情報を送信**] をクリックします。 会議 ID と既定の電話会議の電話番号は、会議出席依頼がない、暗証番号 (pin) に含まれています。
    
    [オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。
    
 **Windows PowerShell を使用します。**
  
- Windows PowerShell を使用して実行します。 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    [セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)を使用すると、メールを含む、組織の他の設定を管理します。
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>ユーザーに送信される電子メール メッセージ内の送信者の連絡先情報を変更します。

実際の電子メール アドレス、送信者の連絡先情報の表示名など、ユーザーに自動的に送信される電子メールの変更を行うことができます。 既定では、電子メールの送信者には、Office 365 は、電子メール アドレスを変更し、名前を表示できます Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用します。 ユーザーに電子メールを送信する電子メール アドレスを変更するには、次の操作を行う必要があります。
  
- _SendEmailFromAddress_パラメーターでは、電子メール アドレスを入力します。
    
- _SendEmailFromDisplayName_ パラメーターにメールの表示名を入力する
    
- _SendEmailOverride_パラメーターを_True_に設定します。
    
電子メールが送信される電子メール アドレス、またはを実行して、電子メールの表示名など、ユーザーに送信された電子メールに変更を行うことができます。
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

電子メール アドレス情報を変更する場合は、組織の受信電子メール ポリシーがカスタムの電子メール アドレスから送信されるメールを許可するかどうかを確認する必要があります。
  
[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用するとメールを含む、組織の他の設定を管理するのにことができます。
  
[ユーザーが電話会議の設定を変更するときに自動的に送信される電子メール](emails-sent-to-users-when-their-settings-change.md)を参照してください。
  
## <a name="reset-the-meeting-conference-id"></a>リセット会議会議 ID

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **Skype**ビジネス管理センターは、左側のナビゲーションでの**オーディオ会議**、および [操作] ウィンドウの [**会議 ID**] を [**リセット**] をクリックします。
    
4. **会議 ID をリセットしますか?** ] ウィンドウで、[**はい**] をクリックします。 会議 ID が自動的に作成され、ユーザーに電子メールを送信することが有効になっているかどうか、新しい会議 ID を使用してユーザーに電子メールを送信します。 既定で有効です。
    
    > [!IMPORTANT]
    >  新しい会議 ID が作成されると、呼び出し元が古い会議 ID を使用できません。 ミーティングの招待新しい会議 ID が、招待状に追加されることを確認するのには、既存のスケジュールを変更するのにはユーザーに通知する必要があります。 ユーザーは、ビジネス会議の移行ツールの Skype を使用して、既存の会議を更新します。 ダウンロード、インストール、および、Skype をビジネス会議の更新ツールを実行する方法を参照してください: [会議のビジネスおよび Lync Skype の更新ツール] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [、ビジネス オンラインの Skype会議の移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)、 [Skype オンライン ビジネスをミーティングの移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)とします。
  
[ユーザーの会議 ID のリセット](reset-a-conference-id-for-a-user.md)を参照してください。
  
## <a name="reset-a-conference-organizers-pin"></a>会議開催者の PIN をリセットする

静的の Id は、組織内のユーザーはランダムな番号を覚えておく必要があるときに使用します。特定の番号を選択したり、覚えやすいものを使用することができます。 動的会議 Id を使用する場合各会議ユーザのスケジュールは割り当てられます会議の一意の id。 場合に割り当てる静的な会議 Id、[組織内のオーディオ会議を使用して動的な Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)ではなく動的です。
  
静的な会議 ID が自動的に作成され、ユーザーに割り当てられているがある場合ユーザーは、この 1 つを使用する場合は、特定の数に設定するとユーザーが覚えられないか、会議 ID が失われています。 ビジネス管理センターの Skype と Windows PowerShell を使用するには表示、変更、および、会議 ID をリセットするには
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**の左側のナビゲーションでは、[**電話会議**] をクリックします。
    
3. **ユーザー**] をクリックし、ユーザーの PIN をリセットするにします。
    
4. [操作] ウィンドウで、**暗証番号 (pin)**、[**リセット**] をクリックします。
    
オーディオ会議や、PIN をリセットする場合は有効にしている場合、ユーザーは PIN をメールに表示されます。 自動的に無効にした場合は、電子メールを送信する PIN リセットの電子メールは送信されません、ユーザーに PIN を手動で送信する必要があります。 暗証番号 (pin) のみが表示されます 1 回リセットされた後。 ユーザーのプロパティのリセットの直後にそれが表示されたら、PIN をもう表示されません。代わりに、。 が表示されます。 
  
[ユーザーのオーディオ会議の PIN のリセット](reset-the-audio-conferencing-pin-for-a-user.md)を参照してください。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>オーディオ会議の情報を使用して電子メールをユーザーに送信します。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**の左側のナビゲーションでは、[**電話会議**] をクリックします。
    
3. **ユーザー**] をクリックし、ユーザーの PIN をリセットするにします。
    
4. 操作ウィンドウで、[ **電話会議情報をメールで送信**] をクリックします。
    
    > [!NOTE]
    > これを行うには、オーディオ会議暗証番号 (pin) はありませんがユーザーに送信します。 
  
[オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>ミーティングの開催者の既定の電話会議の電話番号を設定します。

 **オーディオ会議のユーザーを有効にすると、ミーティングの開催者の既定の電話会議の電話番号を設定するのには**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. 左側のナビゲーションでは、**オーディオ会議**に移動 > **のユーザー**です。 電話会議を有効にするユーザーを選択します。
    
4. [操作] ウィンドウの [ユーザーのプロパティ] で、[**編集**] をクリックします。
    
5. [**プロパティ**] ページで、[**プロバイダー名**] には、オーディオ会議プロバイダーを選択するのに」ドロップ ダウン リストを使用します。
    
  - オーディオ会議プロバイダーとして Microsoft を選択した場合は、ボックスの一覧から既定の電話会議の電話番号を選択できます。  
    
  - オーディオ会議プロバイダーとして、サード パーティ製の ACP を選択した場合、有料の電話を手動で入力する必要が場合は、フリー ダイヤルの電話番号が必要とします。 これらの電話番号は、既定の電話番号になります。
    
    ユーザーの既定の電話会議の電話番号は、会議出席依頼に会議をスケジュールするときに表示されている番号です。
    
6. [ **保存**] をクリックします。 
    
[携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。
  
 **オーディオ会議のユーザーを有効にした後会議の開催者の既定の電話会議の電話番号を設定するのには**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **ユーザー**は、ユーザーを選択し、[アクション] ページで、[**編集**] をクリックします。
    
4. [**プロパティ**] ページで、[**プロバイダー名**] には、オーディオ会議プロバイダーを選択するのに」ドロップ ダウン リストを使用します。
    
  - ユーザーは、オーディオ会議プロバイダーとして、Microsoft を使用する場合は、ボックスの一覧から既定の電話会議の電話番号を選択できます。  
    
  - ユーザーは、オーディオ会議プロバイダーとしてのサード ・ パーティ製の ACP を使用する場合、有料の電話を手動で入力する必要が必要な場合、フリー ダイヤルの電話番号とします。
    
    ユーザーの既定の電話会議の電話番号は、会議出席依頼に会議をスケジュールするときに表示されている番号です。
    
5. [ **保存**] をクリックします。 
    
[携帯電話への招待に含まれている番号の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。
  
## <a name="setting-audio-conferencing-bridge-settings"></a>オーディオ会議ブリッジの設定を設定します。

 **呼び出し元がミーティングに参加するときは、会議の経験を設定します。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。
    
4. [**会議参加の経験**をするには、次の操作を選択します。
    
  - **会議エントリを有効にして終了の通知をオンにする**これがデフォルトで選択されます。 このチェック ボックスをオフにするとデータを入力したり、会議を離れるときに既定では、会議に参加しているユーザーが通知はありません。
    
    ユーザーが、Skype を使用して、アプリケーションのビジネスまたはマイクロソフトのチームの会議に参加し、Skype の会議またはマイクロソフトのチーム**のオプション**メニューでの**アナウンス**設定を変更するときに会議ごとの単位で設定できます、会議。
    
  - **ミーティングに参加する前に自分の名前を記録する呼び出し元を確認**これがデフォルトで選択されます。 このチェック ボックスをオフにすると会議に参加する前に自分の名前を記録するための呼び出し元を求められますされません。
    
5. 変更を行ったら、[**保存**] をクリックします。
    
[オーディオ会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。
  
 **会議の暗証番号 (pin) の長さを設定します。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。
    
4. [**セキュリティ**] の**暗証番号 (pin) の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁数を入力し、し、[**保存**] をクリックします。
    
    暗証番号 (pin) は、4 桁から 12 桁の間である必要があります。 デフォルトは 5 です。
    
[オーディオ会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。
  
 **有効にするか、オーディオのユーザーに送信される電子メールを無効にします。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**の左側のナビゲーションでは、[**電話会議**] をクリックします。
    
3. **Microsoft ブリッジの設定**] ページをオンまたはオフの**オーディオ会議の設定を変更する場合、ユーザーに e メールを自動的に送信**する。
    
4. [ **保存**] をクリックします。
    
    ユーザーのオーディオ会議のプロパティに移動し、**電子メールを使用して会議情報を送信**] をクリックしてユーザーに、電話会議の設定を使用する電子メールを送信することも。
    
    電子メールを送信する場合はこれを行うには、会議 ID と電話会議の番号を含むのみですが、暗証番号 (pin) を含めることはできません。
    
    [オーディオ会議の情報を持つユーザーに電子メールを送信する](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a>参照してくださいし、オーディオ会議ブリッジにプライマリとセカンダリの言語を設定します。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **Skype**ビジネス管理センターは、左側のナビゲーションでは、では、**オーディオ会議**に移動し、 **Microsoft ブリッジ**] をクリックします。
    
4. リストから電話番号を選択して、[操作] ウィンドウで、[**言語の設定**] をクリックし、**言語の設定**] ページで、[使用] をクリックして、サポートされている言語の完全な一覧を表示するのには、**主言語**] ボックスの一覧。
    
    オーディオ会議プロバイダーとして Microsoft を選択した場合にサポートされているプライマリとセカンダリの言語を設定することもできます。 リストで選択した順序は、呼び出し元の言語が表示されます同じ順序です。
    
[オーディオ会議の自動応答の言語設定](set-auto-attendant-languages-for-audio-conferencing.md)を参照してください。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>電話会議にダイヤルイン番号を参照してください。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **マイクロソフトのブリッジ**です。 ここでは次のようなことができます。
    
  - 電話会議に使用する Office 365 によって設定されている電話番号を表示します。 
    
  - 場所、および音声会議自動アテンダントによって使用されるプライマリとセカンダリ言語を表示します。
    
  - 電話会議が有効になっているときに、ユーザーに指定された既定の電話番号を選択します。 オーディオ会議ブリッジの既定の電話番号が変更された場合は、既存のユーザーの既定の電話番号は変更されません。
    
**オーディオ会議**に移動することができます > **ユーザー**およびユーザーのプロパティを既定値を変更するのには、組織で使用可能な番号の一覧から新しい番号を選択することによってユーザーの番号を選択します。
  
[オーディオ会議の番号の一覧を参照してください](see-a-list-of-audio-conferencing-numbers.md)参照してください。
  
## <a name="see-a-list-of-users-that-are-enabled"></a>有効になっているユーザーの一覧を参照してください。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **Skype**ビジネス管理センターは、左側のナビゲーションでは、[**電話会議**に移動 > および**ユーザー**です。
    
[電話会議を有効になっているユーザーの一覧を参照してください](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)参照してください。
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

Windows PowerShell を使用して組織レベルで管理することができますいくつかの設定があります。 これにより、簡単にすべてのユーザー設定を適用します。 
    
各コマンドレットのヘルプを表示する、 [Skype](https://go.microsoft.com/fwlink/?LinkId=627324)を参照してください。

組織レベルの設定を以下に示します。 
> 
- **開始/終了の通知を設定します。**_$True_は、既定では。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- **名の記録を設定します。**_$True_は、既定では。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **暗証番号 (pin) の長さを設定**デフォルトは 5 です。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **のみダイヤルイン会議電話からの設定**既定値の_$false_です。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **ユーザーに電子メールを送信するかどうかを設定**_$True_は、既定では。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **別のアカウントから電子メールを送信するかどうかを設定**既定では_$false_です。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **ユーザーに送信される電子メールの差出人アドレスの設定**_$Null_を既定値には。 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **ユーザーに送信される電子メールの表示名を設定します。**_$Null_を既定値には。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell についてより詳しく知りたいです。   
- Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。 Windows PowerShell を実行する複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 を管理できます。 Windows PowerShell を使い始めるには、以下のトピックを参照してください。
    
  - [Office 365 の PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。 次のトピックで、これらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
    
## <a name="related-topics"></a>関連トピック

[ユーザーの電話会議の設定を管理します。](manage-the-audio-conferencing-settings-for-a-user.md)

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)

