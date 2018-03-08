---
title: "組織用の電話会議の設定を管理します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "ダイヤルイン会議ライセンスと会議 ID をサードパーティ会議プロバイダー、およびその他のダイヤルイン会議設定を設定する、ユーザーに割り当てる手順を参照してください。 "
ms.openlocfilehash: 6fb10654c5845fb5524264219e642cd0a250e860
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>組織用の電話会議の設定を管理します。

簡単にすべての skype for Business と Microsoft チームを 1 か所で電話会議設定を確認する場合があります。 
  
## <a name="assign-an-audio-conferencing-license"></a>音声会議ライセンスを割り当てる

> [!NOTE]
> **Skype for Business 管理センター**を使用してライセンスを割り当てることはできません。Office 365 管理センターを使用する必要があります。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。 
  
 **ユーザーのライセンスを割り当てる**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**の左のナビゲーションでの [**ユーザー**] に移動 > **アクティブなユーザー**の場合は、し利用可能なユーザーの一覧からユーザーを選択します。
    
    > [!NOTE]
    > 場合は、同時に最大 20 人のユーザーにライセンスを割り当てる、**ビューの選択**ドロップダウン リストを使用して、オプションのいずれかを選択し、独自のビューを作成したりできます。**編集**、**次回**2 回] をクリックし、ライセンスを選択し、[**送信**] をクリックします。Windows Powershell を使用して複数のユーザーにライセンスを割り当てることもできます。手順とサンプル PowerShell スクリプト、[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。 
  
3. 操作ウィンドウの [**製品のライセンス**] で、[**編集**] をクリックします。 
    
4. [**製品のライセンス**] ページで**電話会議**を有効にして、[**保存**] をクリックします。ライセンスの詳細は、 [Skype for Business や Microsoft チーム アドオンのライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。
    
> [!NOTE]
> ライセンスを割り当てたら、Microsoft 可能性がありますしない最初にリストに表示、電話会議プロバイダーとしてします。このような場合、Office 365 管理センターからログアウトしするか、ctrl キーを押しながら f5 キーを押してブラウザー ウィンドウを更新します。 
  
## <a name="assign-a-conference-id-for-a-user"></a>ユーザーの会議 ID を割り当てる

会議 ID が自動的に割り当てられているをユーザーに電話会議プロバイダーとして Microsoft を使って電話会議設定している場合。割り当てられている電話会議 ID 静的または動的でき、会議がスケジュールされている場合は、会議の出席依頼の送信します。 
  
静的な Id は、組織内のユーザーをランダムな番号を保存したくない場合に使用します。特定の番号を選択したり、覚えやすいものを選択することができます。動的会議 Id を使用する場合各会議ユーザーのスケジュールが取得割り当て会議の一意の id。割り当てたい動的静的会議 Id ではなく場合、は、[組織内の電話会議を使用して動的な Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)を参照してください。
  
Skype for Business 管理センターは、会議 ID をユーザーに割り当てるには使用できませんが、これを行う Windows PowerShell コマンドレットを使用することができます。
  
ユーザーの会議 ID を設定するには、次のコマンドを実行します。
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> 会議 ID が 7 つの数字を含める必要があり、Skype for Business 管理センター、または Windows PowerShell を使用してで変更することはできません。 
  
コマンドレットの詳細については、[セット CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )を参照してください。
  
> [!IMPORTANT]
>  新しい会議 ID を作成したら、発信者に応答して古い会議 ID を使用できません。既存ように招待状に ID が追加された新しい会議出席依頼を会議のスケジュールを変更するユーザーに通知する必要があります。ユーザーは、Skype for Business 会議の移行ツールを使用して、既存の会議を更新することができます。ダウンロード、インストール、および Business Meeting Update Tool の Skype を実行する方法を参照してください: [skype for Business と Lync Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype for Business Online、会議の移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)、および[Skype for Business Online では、会議移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)します。
  
[表示、変更、およびユーザーに割り当てられている電話会議 ID をリセットする](see-change-and-reset-a-conference-id-assigned-to-a-user.md)を参照してください。
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a>Microsoft からサードパーティ プロバイダーに電話会議プロバイダーを変更します。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **ユーザー**の場合は、電話会議プロバイダーを変更するユーザーを選択し、します。
    
4. 操作ウィンドウで、[**編集**] をクリックします。 
    
5. [**プロパティ**] ページで、[**プロバイダー名**] で、ユーザーの電話会議プロバイダーを選択します。
    
    > [!NOTE]
    > 複数のユーザーを選択した場合は、電話会議プロバイダー、[**なし]**として使用して Microsoft を選ぶだけことができます。
  
6. {[**保存**] をクリックします。} 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>有効にする、または電話会議のユーザーに送信されるメールを無効にします。

有効にする、またはユーザーに送信されたメールを無効にするのには、Skype for Business 管理センター」または「Windows PowerShell を使用できます。
  
 **Business 管理センターの Skype を使用します。**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**し、左のナビゲーションで [**電話会議**] をクリックします。
    
3. **Microsoft ブリッジの設定**] ページでオンまたはオフの**場合は、電話会議の設定を変更するユーザーにメールを自動的に送信**します。
    
4. {[**保存**] をクリックします。}
    
    ユーザーの電話会議のプロパティをクリックして**会議情報を電子メールで送信する**ユーザーに電話会議の設定を含むメールを送信することもできます。会議の出席依頼がない、暗証番号 (pin) では、会議 ID と既定の電話会議の電話番号が含まれます。
    
    [この情報は、電話会議情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。
    
 **Windows PowerShell を使用します。**
  
- Windows PowerShell を使用してもおよび実行できます。 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    メールを含む、組織の他の設定を管理するのには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)を使用できます。
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>ユーザーに送信されたメール メッセージの送信者の連絡先の情報を変更します。

実際のメール アドレスと、その送信者の連絡先情報の表示名を含む、ユーザーに自動的に送信されるメールに変更を加えたことができます。既定では、メールの送信者には、「Office 365 がメール アドレスを変更して名前を表示する Windows PowerShell と[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用します。ユーザーにメールを送信するメール アドレスを変更するには、次の操作を行う必要があります。
  
- _SendEmailFromAddress_パラメーターには、メール アドレスを入力します。
    
- _SendEmailFromDisplayName_パラメーターには、メールの表示名を入力します。
    
- _SendEmailOverride_パラメーターを_True_に設定します。
    
メールが送信されたメール アドレスなどを実行して、メールの表示名のユーザーに送信されたメールに変更を行うことができます。
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

メール アドレスの情報を変更する場合は、組織のメールの受信ポリシーが、ユーザー設定のメール アドレスからメールを許可するかどうかを確認する必要があります。
  
メールを含む、組織の他の設定を管理するのには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)コマンドレットを使用できます。
  
[ユーザーの電話会議の設定を変更するときに自動的に送信されるメール](emails-sent-to-users-when-their-settings-change.md)を参照してください。
  
## <a name="reset-the-meeting-conference-id"></a>会議を再設定する会議 ID

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで [**電話会議**] に移動し、操作ウィンドウの [**電話会議 ID**で、[**リセット**] をクリックします。
    
4. **会議 ID をリセットですか?**ウィンドウで、[**はい**] をクリックします。会議 ID が自動的に作成し、ユーザーに電子メールの送信が有効になっているかどうかは、新しい会議 ID を持つユーザーに電子メールを送信します。既定で有効です。
    
    > [!IMPORTANT]
    >  新しい会議 ID を作成したら、発信者に応答して古い会議 ID を使用できません。既存ように招待状に ID が追加された新しい会議出席依頼を会議のスケジュールを変更するユーザーに通知する必要があります。ユーザーは、Skype for Business 会議の移行ツールを使用して、既存の会議を更新することができます。ダウンロード、インストール、および Business Meeting Update Tool の Skype を実行する方法を参照してください: [skype for Business と Lync Meeting Update Tool] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype for Business Online では、会議の移行ツール (64 ビット)](http://go.microsoft.com/fwlink/?LinkID=626047)、 [Skype for Business Online、会議の移行ツール (32 ビット)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)とします。
  
[ユーザーの会議 ID をリセットする](reset-a-conference-id-for-a-user.md)を参照してください。
  
## <a name="reset-a-conference-organizers-pin"></a>会議の開催者の PIN をリセットします。

静的な Id は、組織内のユーザーをランダムな番号を保存したくない場合に使用します。特定の番号を選択したり、覚えやすいものを使用することができます。動的会議 Id を使用する場合各会議ユーザーのスケジュールが取得割り当て会議の一意の id。場合は、割り当てる静的会議 Id、[組織内の電話会議を使用して動的な Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)ではなく動的します。
  
静的会議 ID が自動的に作成され、ユーザーに割り当てられているがありますとユーザーが使用して、特定の数を設定するまたはユーザーに、会議 ID が喪失したか、思い出せないSkype for Business 管理センターと Windows PowerShell を使用するには、表示、変更、および、会議 ID をリセットするには
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**し、左のナビゲーションで [**電話会議**] をクリックします。
    
3. **ユーザー**] をクリックし、[の PIN をリセットするユーザーを選択します。
    
4. 操作ウィンドウで、**暗証番号 (pin)**、[**リセット**] をクリックします。
    
電話会議の PIN をリセットするときの有効なしているとき、ユーザーは自分の PIN とメールを受信します。自動的に無効にした場合、メールを送信する PIN のリセット メールに送られませんし、手動で PIN をユーザーに送信する必要があります。PIN がのみ後に表示される 1 回が再設定します。ユーザーのプロパティにリセットした後が表示されたら、PIN をなった表示されません。代わりに、。 が表示されます。 
  
[ユーザーの音声会議の PIN のリセット](reset-the-audio-conferencing-pin-for-a-user.md)を参照してください。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>ユーザーに電話会議の情報を含む電子メールを送信します。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**し、左のナビゲーションで [**電話会議**] をクリックします。
    
3. **ユーザー**] をクリックし、[の PIN をリセットするユーザーを選択します。
    
4. 操作ウィンドウで、**会議情報を電子メールで送信する**] をクリックします。
    
    > [!NOTE]
    > これを行うときに電話会議の PIN いない、[ユーザーに送信します。 
  
[この情報は、電話会議情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>会議の開催者の既定の電話会議の電話番号を設定します。

 **電話会議のユーザーを有効にする場合に会議の開催者の既定の電話会議の電話番号を設定するには**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. 左のナビゲーションで**電話会議**に移動 > **ユーザー**。電話会議を有効にユーザーを選択します。
    
4. ユーザーのプロパティ] で、操作ウィンドウで [**編集**] をクリックします。
    
5. [**プロパティ**] ページで、[**プロバイダー名**] でドロップダウン リストを使用して、電話会議プロバイダーを選択します。
    
  - 電話会議プロバイダーとして Microsoft を選択すると、一覧から既定の電話会議の電話番号を選択します。  
    
  - 電話会議プロバイダーとしてサードパーティ ACP を選ぶ場合有料を手動で入力する必要があり、必要に応じて、フリー ダイヤル電話番号です。これらの電話番号を既定の電話番号となります。
    
    ユーザーの既定の電話会議の電話番号は、会議をスケジュールする場合は、会議の出席依頼に表示される数です。
    
6. {[**保存**] をクリックします。} 
    
[携帯電話への招待に含まれる数値の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。
  
 **電話会議のユーザーを有効にした後に会議の開催者の既定の電話会議の電話番号を設定するには**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **ユーザー**の場合は、必要なユーザーを選択し、[アクション] ページで、[**編集**] をクリックします。
    
4. [**プロパティ**] ページで、[**プロバイダー名**] でドロップダウン リストを使用して、電話会議プロバイダーを選択します。
    
  - ユーザーは、電話会議プロバイダーとして Microsoft を使用している場合は、一覧から既定の電話会議の電話番号を選択できます。  
    
  - ユーザーは、電話会議プロバイダーとしてのサードパーティ ACP を使用している場合は、有料に手動で入力する必要があり、フリー ダイヤル電話番号を必要に応じてします。
    
    ユーザーの既定の電話会議の電話番号は、会議をスケジュールする場合は、会議の出席依頼に表示される数です。
    
5. {[**保存**] をクリックします。} 
    
[携帯電話への招待に含まれる数値の設定](set-the-phone-numbers-included-on-invites.md)を参照してください。
  
## <a name="setting-audio-conferencing-bridge-settings"></a>電話会議ブリッジの設定

 **発信者が会議に参加するときに、会議のエクスペリエンスを設定します。**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。
    
4. [**会議参加エクスペリエンス**には、次の操作を選択します。
    
  - **会議のエントリを有効にして終了通知を有効にするには**これが既定で選択されます。このチェック ボックスをオフにする場合は、既定では、会議に参加しているユーザーは入力したり、会議のままに通知されません。
    
    ユーザーが Skype を for Business または Microsoft チームのアプリを使って会議に参加し、[Skype 会議または Microsoft チーム**のオプション**] メニューの [**入ユーザー退室を通知**の設定を変更するときに会議ごとの単位で設定できます、会議します。
    
  - **質問の発信者**これが既定で選択されます。このチェック ボックスをオフにする場合、発信者が、会議に参加する前に、相手の名前を記録するように依頼されません。
    
5. 変更が終了したら、[**保存**] をクリックします。
    
[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。
  
 **会議の PIN の長さを設定します。**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジの設定**します。
    
4. [**セキュリティ**] の**PIN の長さ**] ボックスの一覧で、[PIN の桁数を入力し、[**保存**] をクリックします。
    
    4、12 桁の数字の間、暗証番号 (pin) があります。既定では 5 です。
    
[電話会議ブリッジの設定を変更する](change-the-settings-for-an-audio-conferencing-bridge.md)を参照してください。
  
 **有効にするまたはオーディオのユーザーに送信されるメールを無効にします。**
  
1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**し、左のナビゲーションで [**電話会議**] をクリックします。
    
3. **Microsoft ブリッジの設定**] ページでオンまたはオフの**場合は、電話会議の設定を変更するユーザーにメールを自動的に送信**します。
    
4. {[**保存**] をクリックします。}
    
    ユーザーの電話会議のプロパティをクリックして**会議情報を電子メールで送信する**ユーザーに電話会議の設定] でメールを送信することもできます。
    
    これを行う場合は、メールが送信されますが、会議 ID と、会議の電話番号を含むのみ、PIN を含めることはできません。
    
    [この情報は、電話会議情報を持つユーザーに電子メールを送信](send-an-email-to-a-user-with-their-dial-in-information.md)を参照してください。
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a>表示し、電話会議ブリッジにプライマリおよびセカンダリ言語の設定

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**] で、左のナビゲーションでは、**音声会議**に移動し、[ **Microsoft bridge**] をクリックします。
    
4. 一覧から電話番号を選択、操作ウィンドウ] の [**言語の設定**] をクリックし、[**言語の設定**] ページで、使用、**主言語**] をクリックし、サポートされている言語のリストを表示します。
    
    電話会議プロバイダーとして Microsoft を選ぶときにサポートされているプライマリおよびセカンダリ言語を設定することもできます。リストで選択した順序は、同じ順序の発信者に応答する言語が表示されますです。
    
[電話会議の自動応答の言語を設定する](set-auto-attendant-languages-for-audio-conferencing.md)を参照してください。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>電話会議にダイヤルイン番号が表示されます。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 > **Microsoft ブリッジ**します。ここで次のようなことができます。
    
  - 電話会議のために、Office 365 によって設定されている電話番号を表示します。 
    
  - 場所、および音声会議の自動応答で使用されるプライマリおよびセカンダリ言語を表示します。
    
  - 音声会議が有効なときに、ユーザーに指定される既定の電話番号を選択します。電話会議ブリッジの既定の電話番号を変更する場合は、既存ユーザーに対して既定の電話番号は変更されません。
    
**電話会議**に移動できる > **ユーザー**と既定値を変更するのには、ユーザーのプロパティは、組織で使用できる番号の一覧から新しい番号を選択し、ユーザーの番号を選択します。
  
[電話会議の数値のリストを表示する](see-a-list-of-audio-conferencing-numbers.md)を参照してください。
  
## <a name="see-a-list-of-users-that-are-enabled"></a>有効になっているユーザーの一覧を参照してください。

1. 職場または学校のアカウントで Office 365 にサインインします。
    
2. **Office 365 管理センター**に移動 > **Skype for Business**します。
    
3. **Skype for Business 管理センター**、左のナビゲーションで**電話会議**に移動 >、[**ユーザー**。
    
[電話会議を有効になっているユーザーのリストを表示する](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)を参照してください。
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法を知りたいとしていますか。

Windows PowerShell を使用して組織レベルで管理できるいくつかの設定があります。これにより、簡単にすべてのユーザーに設定を適用します。 
    
各コマンドレットのヘルプを表示する、 [Skype for Business Online のコマンドレット](https://go.microsoft.com/fwlink/?LinkId=627324)を参照してください。

組織レベルの設定を紹介します。 
> 
- **開始/終了通知を設定します。**既定では_$true です_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- **レコーディングの名前を設定します。**既定では_$true です_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **PIN の長さを設定します。**既定では 5 です。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **のみのダイヤルイン会議電話からを設定します。**既定の_$false_します。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **ユーザーにメールを送信するかどうかを設定します。**既定では_$true です_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **別のアカウントからメールを送信するかどうかを設定します。**既定では_$false です_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **ユーザーに送信されるメールの差出人アドレスを設定します。**既定では_$null です_。 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **ユーザーに送信されるメールの表示名を設定します。**既定では_$null です_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細を知りたいです。   
- Windows PowerShell がユーザーを管理するユーザーを許可または使用できません。Windows PowerShell で複数のタスクを実行するがある場合、日常業務を簡素化する管理の 1 つのポイントを使用して Office 365 を管理できます。Windows PowerShell で開始するには、次のトピックを参照してください。
    
  - [Office 365 PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理する最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell では多くの利点速度、わかりやすいように、および生産性でのみ実行しようとする設定の変更、多くのユーザーに一度になど、Office 365 管理センターを使用します。次のトピックでこれらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell を使用して、Skype for Business Online の管理するには](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用して、共通の Skype for Business Online の管理タスクを実行するには](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    Skype for Business Online 用の Windows PowerShell モジュールを使用すると、Skype for Business Online に接続するリモートの Windows PowerShell セッションを作成することができます。このモジュールでは、64 ビット コンピューター以外では、Microsoft ダウンロード センターからダウンロードできます[Skype for Business Online 用の Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)。
    
## <a name="related-topics"></a>関連トピック

[ユーザーの電話会議の設定を管理します。](manage-the-audio-conferencing-settings-for-a-user.md)

[Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。](set-up-audio-conferencing.md)

